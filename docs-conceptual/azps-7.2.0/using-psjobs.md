---
description: Pelajari cara menjalankan cmdlet Azure PowerShell secara paralel atau sebagai tugas latar belakang, menggunakan -AsJob dan Start-Job.
ms.custom: devx-track-azurepowershell
ms.date: 02/08/2022
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
title: Jalankan cmdlet Azure PowerShell di Pekerjaan PowerShell
ms.openlocfilehash: 8f600a15cfe17c5c42fdccbb01ef78e51aa295a2
ms.sourcegitcommit: cdca0d3199eb118c98aafb63ffcacc3dd080f0d4
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/16/2022
ms.locfileid: "138854955"
---
# <a name="run-azure-powershell-cmdlets-in-powershell-jobs"></a>Jalankan cmdlet Azure PowerShell di Pekerjaan PowerShell

Azure PowerShell bergantung pada koneksi ke cloud Azure dan menunggu tanggapan, sehingga sebagian besar cmdlet ini memblokir sesi PowerShell Anda sampai mereka mendapatkan respons dari cloud. PowerShell Jobs memungkinkan Anda menjalankan cmdlet di latar belakang atau melakukan beberapa tugas di Azure sekaligus, dari dalam satu sesi PowerShell.

Artikel ini adalah gambaran singkat tentang cara menjalankan cmdlet Azure PowerShell sebagai PowerShell Jobs dan periksa penyelesaiannya. Menjalankan perintah dalam Azure PowerShell memerlukan penggunaan konteks Azure PowerShell, yang tercakup secara rinci dalam [konteks Azure dan kredensial masuk](context-persistence.md). Untuk mempelajari selengkapnya tentang Lowongan PowerShell, lihat [Tentang Pekerjaan PowerShell](/powershell/module/microsoft.powershell.core/about/about_jobs).

## <a name="azure-contexts-with-powershell-jobs"></a>Konteks Azure dengan pekerjaan PowerShell

PowerShell Jobs dijalankan sebagai proses terpisah tanpa sesi PowerShell terlampir, sehingga kredensial Azure Anda harus dibagikan dengan mereka. Kredensial diteruskan sebagai objek konteks Azure, menggunakan salah satu metode berikut:

* Kegigihan konteks otomatis. Persistensi konteks diaktifkan secara default dan mempertahankan informasi masuk Anda di beberapa sesi. Dengan persistensi konteks diaktifkan, konteks Azure saat ini diteruskan ke proses baru:

  ```azurepowershell-interactive
  Enable-AzContextAutosave # Enables context autosave if not already on
  $creds = Get-Credential
  $job = Start-Job { param($vmadmin) New-AzVM -Name MyVm -Credential $vmadmin } -ArgumentList $creds
  ```

* `-AzContext` Gunakan parameter dengan cmdlet Azure PowerShell apa pun untuk menyediakan objek konteks Azure:

  ```azurepowershell-interactive
  $context = Get-AzContext -Name 'mycontext' # Get an Azure context object
  $creds = Get-Credential
  $job = Start-Job { param($context, $vmadmin) New-AzVM -Name MyVm -AzContext $context -Credential $vmadmin} -ArgumentList $context,$creds }
  ```

  Jika kegigihan konteks dinonaktifkan, argumen diperlukan `-AzContext` .

* Gunakan sakelar yang `-AsJob` disediakan oleh beberapa cmdlet Azure PowerShell. Sakelar ini secara otomatis memulai cmdlet sebagai PowerShell Job, menggunakan konteks Azure yang saat ini aktif:

  ```azurepowershell-interactive
  $creds = Get-Credential
  $job = New-AzVM -Name MyVm -Credential $creds -AsJob
  ```

  Untuk melihat apakah cmdlet mendukung `-AsJob`, periksa dokumentasi referensinya. Sakelar `-AsJob` tidak memerlukan pengenavean otomatis konteks untuk diaktifkan.

Anda dapat memeriksa status pekerjaan berjalan dengan cmdlet [Get-Job](/powershell/module/microsoft.powershell.core/get-job) . Untuk mendapatkan output dari pekerjaan sejauh ini, gunakan cmdlet [Receive-Job](/powershell/module/microsoft.powershell.core/receive-job) .

Untuk memeriksa kemajuan operasi dari jarak jauh di Azure, gunakan `Get-` cmdlet yang terkait dengan jenis sumber daya yang dimodifikasi oleh pekerjaan:

```azurepowershell-interactive
$creds = Get-Credential
$context = Get-AzContext -Name 'mycontext'
$vmName = "MyVm"

$job = Start-Job { param($context, $vmName, $vmadmin) New-AzVM -Name $vmName -AzContext $context -Credential $vmadmin} -ArgumentList $context,$vmName,$creds }

Get-Job $job
Get-AzVM -Name $vmName
```

## <a name="see-also"></a>Lihat juga

* [konteks Azure PowerShell](context-persistence.md)
* [Tentang PowerShell Jobs](/powershell/module/microsoft.powershell.core/about/about_jobs)
* [Referensi Dapatkan Pekerjaan](/powershell/module/microsoft.powershell.core/get-job)
* [Referensi Terima-Pekerjaan](/powershell/module/microsoft.powershell.core/receive-job)
