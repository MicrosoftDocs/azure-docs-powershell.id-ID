---
title: Menjalankan cmdlet Azure PowerShell di Pekerjaan PowerShell
description: Pelajari cara menjalankan cmdlet Azure PowerShell secara paralel atau sebagai tugas latar belakang, menggunakan -AsJob dan Start-Job.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 09/27/2021
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
ms.openlocfilehash: bae35b1369f42630574f4eda46d044bc5dd309df
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "132429461"
---
# <a name="run-azure-powershell-cmdlets-in-powershell-jobs"></a>Menjalankan cmdlet Azure PowerShell di Pekerjaan PowerShell

Azure PowerShell bergantung pada koneksi ke cloud Azure dan menunggu responsnya, sehingga sebagian besar cmdlet ini memblokir sesi PowerShell Anda hingga cmdlet mendapatkan respons dari cloud. Pekerjaan PowerShell memungkinkan Anda menjalankan cmdlet di latar belakang atau melakukan beberapa tugas di Azure sekaligus, dari dalam satu sesi PowerShell.

Artikel ini adalah ringkasan gambaran umum tentang cara menjalankan cmdlet Azure PowerShell sebagai Pekerjaan PowerShell dan memeriksa penyelesaiannya. Menjalankan perintah di Azure PowerShell memerlukan penggunaan konteks Azure PowerShell, yang tercakup secara mendetail di [konteks Azure dan informasi masuk](context-persistence.md). Untuk mempelajari selengkapnya tentang Pekerjaan PowerShell, lihat [Tentang Pekerjaan PowerShell](/powershell/module/microsoft.powershell.core/about/about_jobs).

## <a name="azure-contexts-with-powershell-jobs"></a>Konteks Azure dengan pekerjaan PowerShell

Pekerjaan PowerShell dijalankan sebagai proses terpisah tanpa sesi PowerShell terlampir, sehingga informasi masuk Azure Anda harus dibagikan dengan Pekerjaan. Informasi masuk diteruskan sebagai objek konteks Azure, menggunakan metode ini:

* Persistensi konteks otomatis. Persistensi konteks diaktifkan secara default dan mempertahankan informasi masuk di beberapa sesi. Dengan persistensi konteks yang diaktifkan, konteks Azure saat ini diteruskan ke proses baru:

  ```azurepowershell-interactive
  Enable-AzContextAutosave # Enables context autosave if not already on
  $creds = Get-Credential
  $job = Start-Job { param($vmadmin) New-AzVM -Name MyVm -Credential $vmadmin } -ArgumentList $creds
  ```

* Gunakan parameter `-AzContext` dengan cmdlet Azure PowerShell untuk menyediakan objek konteks Azure:

  ```azurepowershell-interactive
  $context = Get-AzContext -Name 'mycontext' # Get an Azure context object
  $creds = Get-Credential
  $job = Start-Job { param($context, $vmadmin) New-AzVM -Name MyVm -AzContext $context -Credential $vmadmin} -ArgumentList $context,$creds }
  ```

  Jika persistensi konteks dinonaktifkan, argumen `-AzContext` diperlukan.

* Gunakan sakelar `-AsJob` yang disediakan oleh beberapa cmdlet Azure PowerShell. Peralihan ini memulai secara otomatis cmdlet sebagai Pekerjaan PowerShell, menggunakan konteks Azure yang aktif saat ini:

  ```azurepowershell-interactive
  $creds = Get-Credential
  $job = New-AzVM -Name MyVm -Credential $creds -AsJob
  ```

  Untuk melihat apakah cmdlet mendukung `-AsJob`, periksa dokumentasi referensinya. Sakelar `-AsJob` tidak memerlukan simpan-otomatis konteks untuk diaktifkan.

Anda dapat memeriksa status pekerjaan yang sedang berjalan dengan cmdlet [Get-Job](/powershell/module/microsoft.powershell.core/get-job). Untuk mendapatkan output dari pekerjaan sejauh ini, gunakan cmdlet [Receive-Job](/powershell/module/microsoft.powershell.core/receive-job).

Untuk memeriksa kemajuan operasi dari jarak jauh di Azure, gunakan cmdlet `Get-` yang berkaitan dengan jenis sumber daya yang dimodifikasi oleh pekerjaan:

```azurepowershell-interactive
$creds = Get-Credential
$context = Get-AzContext -Name 'mycontext'
$vmName = "MyVm"

$job = Start-Job { param($context, $vmName, $vmadmin) New-AzVM -Name $vmName -AzContext $context -Credential $vmadmin} -ArgumentList $context,$vmName,$creds }

Get-Job $job
Get-AzVM -Name $vmName
```

## <a name="see-also"></a>Lihat juga

* [Konteks Azure PowerShell](context-persistence.md)
* [Tentang Pekerjaan PowerShell](/powershell/module/microsoft.powershell.core/about/about_jobs)
* [Referensi Get-Job](/powershell/module/microsoft.powershell.core/get-job)
* [Referensi Receive-Job](/powershell/module/microsoft.powershell.core/receive-job)
