---
description: Pelajari cara menjalankan cmdlet Azure PowerShell secara paralel atau sebagai tugas latar belakang, menggunakan -AsJob dan Start-Job.
ms.custom: devx-track-azurepowershell
ms.date: 02/18/2022
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
title: Jalankan cmdlet Azure PowerShell di Pekerjaan PowerShell
ms.openlocfilehash: dfd091455caaa163c3d3b7a4c33e568fab2f14c1
ms.sourcegitcommit: b29dc53214e2018b30326c37fe98585658629e62
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/19/2022
ms.locfileid: "139129183"
---
# <a name="run-azure-powershell-cmdlets-in-powershell-jobs"></a>Jalankan cmdlet Azure PowerShell di Pekerjaan PowerShell

Azure PowerShell bergantung pada koneksi ke cloud Azure dan menunggu tanggapan, sehingga sebagian besar cmdlet ini memblokir sesi PowerShell Anda sampai mereka mendapatkan respons dari cloud. PowerShell Jobs memungkinkan Anda menjalankan cmdlet di latar belakang atau melakukan beberapa tugas di Azure sekaligus, dari dalam satu sesi PowerShell.

Artikel ini adalah gambaran singkat tentang cara menjalankan cmdlet Azure PowerShell sebagai PowerShell Jobs dan periksa penyelesaiannya. Menjalankan perintah dalam Azure PowerShell memerlukan penggunaan konteks Azure PowerShell, yang tercakup secara rinci dalam [konteks Azure dan kredensial masuk](context-persistence.md). Untuk mempelajari selengkapnya tentang Lowongan PowerShell, lihat [Tentang Pekerjaan PowerShell](/powershell/module/microsoft.powershell.core/about/about_jobs).

## <a name="azure-contexts-with-powershell-jobs"></a>Konteks Azure dengan pekerjaan PowerShell

PowerShell Jobs dijalankan sebagai proses terpisah tanpa sesi PowerShell terlampir, sehingga kredensial Azure Anda harus dibagikan dengan mereka. Kredensial diteruskan sebagai objek konteks Azure, menggunakan salah satu metode berikut:

- Kegigihan konteks otomatis. Persistensi konteks diaktifkan secara default dan mempertahankan informasi masuk Anda di beberapa sesi. Dengan persistensi konteks diaktifkan, konteks Azure saat ini diteruskan ke proses baru:

  ```azurepowershell-interactive
  Enable-AzContextAutosave # Enables context autosave if not already on
  $vmadmin = Get-Credential

  Start-Job {
    New-AzVM -Name MyVm -Credential $Using:vmadmin
  }
  ```

- `AzContext` Gunakan parameter dengan cmdlet Azure PowerShell apa pun untuk menyediakan objek konteks Azure:

  ```azurepowershell-interactive
  $context = Get-AzContext -Name 'mycontext' # Get an Azure context object
  $vmadmin = Get-Credential

  $job = Start-Job {
    New-AzVM -Name MyVm -AzContext $Using:context -Credential $Using:vmadmin
  }
  ```

  Jika persistensi konteks dinonaktifkan, `AzContext` parameter diperlukan.

- Gunakan parameter yang `AsJob` disediakan oleh beberapa cmdlet Azure PowerShell. Sakelar ini secara otomatis memulai cmdlet sebagai PowerShell Job, menggunakan konteks Azure aktif:

  ```azurepowershell-interactive
  $vmadmin = Get-Credential
  $job = New-AzVM -Name MyVm -Credential $vmadmin -AsJob
  ```

  Untuk melihat apakah cmdlet mendukung `AsJob`, periksa dokumentasi referensinya. Parameter `AsJob` tidak memerlukan autosave konteks untuk diaktifkan.

Anda dapat memeriksa status pekerjaan berjalan dengan cmdlet [Get-Job](/powershell/module/microsoft.powershell.core/get-job) . Untuk mendapatkan output dari pekerjaan sejauh ini, gunakan cmdlet [Receive-Job](/powershell/module/microsoft.powershell.core/receive-job) .

Untuk memeriksa kemajuan operasi dari jarak jauh di Azure, gunakan `Get` cmdlet yang terkait dengan jenis sumber daya yang dimodifikasi oleh pekerjaan:

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

- [konteks Azure PowerShell](context-persistence.md)
- [Tentang PowerShell Jobs](/powershell/module/microsoft.powershell.core/about/about_jobs)
- [Dapatkan Pekerjaan](/powershell/module/microsoft.powershell.core/get-job)
- [Menerima-Job](/powershell/module/microsoft.powershell.core/receive-job)
- [Pengubah `Using:` ruang lingkup](/powershell/module/microsoft.powershell.core/about/about_scopes#the-using-scope-modifier)
