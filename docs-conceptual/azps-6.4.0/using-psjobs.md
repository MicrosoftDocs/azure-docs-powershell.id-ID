---
title: Menjalankan Azure PowerShell cmdlet dalam Pekerjaan PowerShell
description: Pelajari cara menjalankan cmdlet Azure PowerShell tugas paralel atau sebagai latar belakang, menggunakan -AsJob dan Start-Job.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 09/27/2021
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
ms.openlocfilehash: bae35b1369f42630574f4eda46d044bc5dd309df
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "132429461"
---
# <a name="run-azure-powershell-cmdlets-in-powershell-jobs"></a>Menjalankan Azure PowerShell cmdlet dalam Pekerjaan PowerShell

Azure PowerShell bergantung pada sambungan ke awan Azure dan menunggu respons, sehingga sebagian besar cmdlets tersebut memblokir sesi PowerShell Anda hingga mereka mendapatkan respons dari awan. PowerShell Jobs memungkinkan Anda menjalankan cmdlet di latar belakang atau melakukan beberapa tugas di Azure sekaligus, dari dalam satu sesi PowerShell.

Artikel ini adalah gambaran umum singkat tentang cara menjalankan cmdlet Azure PowerShell cmdlet sebagai PowerShell Jobs dan memeriksa penyelesaian. Menjalankan perintah Azure PowerShell memerlukan penggunaan Azure PowerShell konteks, yang dibahas secara detail dalam konteks Azure dan [kredensial masuk.](context-persistence.md) Untuk mempelajari selengkapnya tentang Pekerjaan PowerShell, lihat [Tentang Pekerjaan PowerShell](/powershell/module/microsoft.powershell.core/about/about_jobs).

## <a name="azure-contexts-with-powershell-jobs"></a>Konteks Azure dengan pekerjaan PowerShell

PowerShell Jobs dijalankan sebagai proses terpisah tanpa sesi PowerShell yang dilampirkan, jadi kredensial Azure Anda harus dibagikan dengan mereka. Kredensial akan diberikan sebagai objek konteks Azure, menggunakan salah satu metode berikut:

* Persistensi konteks otomatis. Persistensi konteks diaktifkan secara default dan mempertahankan informasi masuk Anda di beberapa sesi. Dengan diaktifkannya persistensi konteks, konteks Azure saat ini akan disampaikan ke proses baru:

  ```azurepowershell-interactive
  Enable-AzContextAutosave # Enables context autosave if not already on
  $creds = Get-Credential
  $job = Start-Job { param($vmadmin) New-AzVM -Name MyVm -Credential $vmadmin } -ArgumentList $creds
  ```

* Gunakan `-AzContext` parameter dengan cmdlet Azure PowerShell cmdlets untuk menyediakan objek konteks Azure:

  ```azurepowershell-interactive
  $context = Get-AzContext -Name 'mycontext' # Get an Azure context object
  $creds = Get-Credential
  $job = Start-Job { param($context, $vmadmin) New-AzVM -Name MyVm -AzContext $context -Credential $vmadmin} -ArgumentList $context,$creds }
  ```

  Jika persistensi konteks dinonaktifkan, `-AzContext` argumen diperlukan.

* Gunakan `-AsJob` sakelar yang disediakan oleh Azure PowerShell cmdlets. Sakelar ini memulai cmdlet secara otomatis sebagai Pekerjaan PowerShell, menggunakan konteks Azure yang saat ini aktif:

  ```azurepowershell-interactive
  $creds = Get-Credential
  $job = New-AzVM -Name MyVm -Credential $creds -AsJob
  ```

  Untuk melihat apakah cmdlet mendukung `-AsJob` , periksa dokumentasi referensinya. Sakelar `-AsJob` ini tidak memerlukan simpan otomatis konteks diaktifkan.

Anda dapat memeriksa status pekerjaan yang sedang berjalan dengan cmdlet [Get-Job.](/powershell/module/microsoft.powershell.core/get-job) Untuk mendapatkan output dari pekerjaan selama ini, gunakan cmdlet [Receive-Job.](/powershell/module/microsoft.powershell.core/receive-job)

Untuk memeriksa kemajuan operasi dari jarak jauh di Azure, gunakan cmdlet yang terkait dengan tipe `Get-` sumber daya yang dimodifikasi oleh pekerjaan:

```azurepowershell-interactive
$creds = Get-Credential
$context = Get-AzContext -Name 'mycontext'
$vmName = "MyVm"

$job = Start-Job { param($context, $vmName, $vmadmin) New-AzVM -Name $vmName -AzContext $context -Credential $vmadmin} -ArgumentList $context,$vmName,$creds }

Get-Job $job
Get-AzVM -Name $vmName
```

## <a name="see-also"></a>Lihat Juga

* [Azure PowerShell konteks](context-persistence.md)
* [Tentang Pekerjaan PowerShell](/powershell/module/microsoft.powershell.core/about/about_jobs)
* [Referensi Get-Job](/powershell/module/microsoft.powershell.core/get-job)
* [Referensi Terima-Pekerjaan](/powershell/module/microsoft.powershell.core/receive-job)
