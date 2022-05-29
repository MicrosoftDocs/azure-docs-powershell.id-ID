---
description: Pelajari cara menjalankan cmdlet Azure PowerShell secara paralel atau sebagai tugas latar belakang, menggunakan -AsJob dan Start-Job.
ms.custom: devx-track-azurepowershell
ms.date: 05/24/2022
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
title: Menjalankan cmdlet Azure PowerShell di Pekerjaan PowerShell
ms.openlocfilehash: 4454ffbb57c5445614413a0c8028c855d859f18f
ms.sourcegitcommit: 321c644cf2161807a71e1af318fc5c5311d22e25
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/25/2022
ms.locfileid: "145819084"
---
# <a name="run-azure-powershell-cmdlets-in-powershell-jobs"></a>Menjalankan cmdlet Azure PowerShell di Pekerjaan PowerShell

Azure PowerShell bergantung pada koneksi ke cloud Azure dan menunggu responsnya, sehingga sebagian besar cmdlet ini memblokir sesi PowerShell Anda hingga cmdlet mendapatkan respons dari cloud. Pekerjaan PowerShell memungkinkan Anda menjalankan cmdlet di latar belakang atau melakukan beberapa tugas di Azure sekaligus, dari dalam satu sesi PowerShell.

Artikel ini adalah ringkasan gambaran umum tentang cara menjalankan cmdlet Azure PowerShell sebagai Pekerjaan PowerShell dan memeriksa penyelesaiannya. Menjalankan perintah di Azure PowerShell memerlukan penggunaan konteks Azure PowerShell, yang tercakup secara mendetail di [konteks Azure dan informasi masuk](context-persistence.md). Untuk mempelajari selengkapnya tentang Pekerjaan PowerShell, lihat [Tentang Pekerjaan PowerShell](/powershell/module/microsoft.powershell.core/about/about_jobs).

## <a name="azure-contexts-with-powershell-jobs"></a>Konteks Azure dengan pekerjaan PowerShell

Pekerjaan PowerShell dijalankan sebagai proses terpisah tanpa sesi PowerShell terlampir, sehingga informasi masuk Azure Anda harus dibagikan dengan Pekerjaan. Informasi masuk diteruskan sebagai objek konteks Azure, menggunakan metode ini:

- Persistensi konteks otomatis. Persistensi konteks diaktifkan secara default dan mempertahankan informasi masuk di beberapa sesi. Dengan persistensi konteks yang diaktifkan, konteks Azure saat ini diteruskan ke proses baru:

  ```azurepowershell-interactive
  Enable-AzContextAutosave # Enables context autosave if not already on
  $vmadmin = Get-Credential

  Start-Job {
    New-AzVM -Name MyVm -Credential $Using:vmadmin
  }
  ```

- Gunakan parameter `AzContext` dengan cmdlet Azure PowerShell untuk menyediakan objek konteks Azure:

  ```azurepowershell-interactive
  $context = Get-AzContext -Name 'mycontext' # Get an Azure context object
  $vmadmin = Get-Credential

  $job = Start-Job {
    New-AzVM -Name MyVm -AzContext $Using:context -Credential $Using:vmadmin
  }
  ```

  Jika persistensi konteks dinonaktifkan, parameter `AzContext` diperlukan.

- Gunakan parameter `AsJob` yang disediakan oleh beberapa cmdlet Azure PowerShell. Peralihan ini memulai secara otomatis cmdlet sebagai Pekerjaan PowerShell, menggunakan konteks Azure aktif:

  ```azurepowershell-interactive
  $vmadmin = Get-Credential
  $job = New-AzVM -Name MyVm -Credential $vmadmin -AsJob
  ```

  Untuk melihat apakah cmdlet mendukung `AsJob`, periksa dokumentasi referensinya. Parameter `AsJob` tidak memerlukan simpan-otomatis konteks untuk diaktifkan.

Anda dapat memeriksa status pekerjaan yang sedang berjalan dengan cmdlet [Get-Job](/powershell/module/microsoft.powershell.core/get-job). Untuk mendapatkan output dari pekerjaan sejauh ini, gunakan cmdlet [Receive-Job](/powershell/module/microsoft.powershell.core/receive-job).

Untuk memeriksa kemajuan operasi dari jarak jauh di Azure, gunakan cmdlet `Get` yang berkaitan dengan jenis sumber daya yang dimodifikasi oleh pekerjaan:

```azurepowershell-interactive
$vmadmin = Get-Credential
$context = Get-AzContext -Name 'mycontext'
$vmName = 'MyVm'

$job = Start-Job {
  New-AzVM -Name $Using:vmName -AzContext $Using:context -Credential $Using:vmadmin
}

Get-Job -Id $job.Id
Get-AzVM -Name $vmName
```

## <a name="see-also"></a>Lihat juga

- [Konteks Azure PowerShell](context-persistence.md)
- [Tentang Pekerjaan PowerShell](/powershell/module/microsoft.powershell.core/about/about_jobs)
- [Get-Job](/powershell/module/microsoft.powershell.core/get-job)
- [Receive-Job](/powershell/module/microsoft.powershell.core/receive-job)
- [Pengubah cakupan `Using:`](/powershell/module/microsoft.powershell.core/about/about_scopes#the-using-scope-modifier)
