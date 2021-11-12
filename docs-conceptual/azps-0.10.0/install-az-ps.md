---
title: Menginstal Azure PowerShell dengan PowerShellGet
description: Cara menginstal Azure PowerShell dengan PowerShellGet
ms.devlang: powershell
ms.topic: conceptual
ms.date: 02/26/2020
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
ms.openlocfilehash: c6767d99690a04d1001dd76a218cc90c9cecca39
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132427997"
---
# <a name="install-azure-powershell"></a>Menginstal Azure PowerShell

Artikel ini menjelaskan cara menginstal modul Azure PowerShell menggunakan [PowerShellGet](/powershell/scripting/gallery/installing-psget). Instruksi ini berfungsi di Windows, macOS, dan Linux.

Azure PowerShell ini juga tersedia di Azure [Cloud Shell](/azure/cloud-shell/overview).

## <a name="requirements"></a>Persyaratan

Azure PowerShell bekerja dengan PowerShell 5.1 atau yang lebih baru di Windows, atau PowerShell Core 6.x dan yang lebih baru di semua platform. Anda harus menginstal [PowerShell versi terbaru yang](/powershell/scripting/install/installing-powershell) tersedia untuk sistem operasi. Azure PowerShell tidak memiliki persyaratan tambahan saat menjalankan PowerShell 6.2.4 dan yang lebih baru.

Untuk memeriksa versi PowerShell, jalankan perintah:

```azurepowershell-interactive
$PSVersionTable.PSVersion
```

Untuk menggunakan Azure PowerShell PowerShell 5.1 di Windows:

1. Perbarui ke [Windows PowerShell 5.1](/powershell/scripting/windows-powershell/install/installing-windows-powershell#upgrading-existing-windows-powershell).
   Jika menggunakan versi Windows 10 1607 atau lebih tinggi, Anda sudah menginstal PowerShell 5.1.
2. Instal [.NET Framework 4.7.2 atau yang lebih baru.](/dotnet/framework/install)
3. Pastikan Anda memiliki PowerShell versi terbaruGet. Jalankan `Install-Module -Name PowerShellGet -Force` .

## <a name="install-the-azure-powershell-module"></a>Menginstal modul Azure PowerShell

> [!WARNING]
> Kami tidak mendukung modul AzureRM dan Az yang terinstal untuk PowerShell 5.1 di Windows saat yang sama. Jika ingin tetap menyediakan AzureRM di sistem Anda, instal modul Az untuk PowerShell 6.2.4 atau yang lebih baru.

Menggunakan cmdlet PowerShellGet merupakan metode penginstalan yang lebih disukai. Instal modul Az hanya untuk pengguna saat ini. Ini adalah lingkup instalasi yang direkomendasikan. Metode ini berfungsi sama pada platform Windows, macOS, dan Linux. Jalankan perintah berikut dari sesi PowerShell:

```powershell-interactive
if (Get-Module -Name AzureRM -ListAvailable) {
    Write-Warning -Message ('Az module not installed. Having both the AzureRM and ' +
      'Az modules installed at the same time is not supported.')
} else {
    Install-Module -Name Az -AllowClobber -Scope CurrentUser
}
```

Secara default, galeri PowerShell tidak dikonfigurasi sebagai penyimpanan tepercaya untuk PowerShellGet. Saat pertama kali menggunakan PSGallery Anda melihat perintah berikut ini:

```Output
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

Jawab `Yes` `Yes to All` atau lanjutkan dengan penginstalan.

Menginstal modul untuk semua pengguna pada sistem memerlukan hak istimewa yang tinggi. Mulai sesi PowerShell menggunakan **Jalankan sebagai administrator** di Windows atau gunakan perintah di `sudo` macOS atau Linux:

```powershell-interactive
if (Get-Module -Name AzureRM -ListAvailable) {
    Write-Warning -Message ('Az module not installed. Having both the AzureRM and ' +
      'Az modules installed at the same time is not supported.')
} else {
    Install-Module -Name Az -AllowClobber -Scope AllUsers
}
```

Modul Az adalah modul rollup untuk cmdlet Azure PowerShell lanjut. Menginstalnya akan mengunduh semua modul Az PowerShell yang tersedia secara umum, dan cmdlets mereka tersedia untuk digunakan.

## <a name="install-offline"></a>Menginstal secara offline

Di beberapa lingkungan, tidak dimungkinkan untuk menyambungkan ke Galeri PowerShell. Dalam situasi tersebut, Anda masih dapat menginstal secara offline menggunakan salah satu metode berikut:

* Unduh modul ke lokasi lain di jaringan Anda dan gunakan modul sebagai sumber instalasi.
  Metode ini memungkinkan Anda membuat cache modul PowerShell di satu server atau berbagi file untuk digunakan dengan PowerShellGet ke semua sistem terputus. Pelajari cara menyiapkan repositori lokal dan menginstal di sistem terputus dengan Bekerja [dengan penyimpanan PowerShell lokalGet](/powershell/scripting/gallery/how-to/working-with-local-psrepositories).
* [Unduh Azure PowerShell MSI](install-az-ps-msi.md) ke komputer yang tersambung ke jaringan, lalu salin penginstal ke sistem tanpa akses ke Galeri PowerShell. Ingat, penginstal MSI hanya berfungsi untuk PowerShell 5.1 di Windows.
* Simpan modul dengan [Simpan-Modul](/powershell/module/PowershellGet/Save-Module) ke berbagi file, atau simpan ke sumber lain dan salin secara manual ke komputer lain:

  ```powershell-interactive
  Save-Module -Name Az -Path '\\server\share\PowerShell\modules' -Force
  ```

## <a name="troubleshooting"></a>Pemecahan masalah

Berikut adalah beberapa masalah umum yang terlihat saat Azure PowerShell modul. Jika Anda mengalami masalah yang tidak tercantum di sini, [cantumkan masalah pada GitHub](https://github.com/azure/azure-powershell/issues).

### <a name="proxy-blocks-connection"></a>Proksi memblokir koneksi

Jika anda mendapatkan kesalahan dari `Install-Module` itu menunjukkan Galeri PowerShell tidak tidak dapat dijangkau, Anda mungkin di belakang proksi. Sistem operasi dan lingkungan jaringan yang berbeda memiliki persyaratan berbeda untuk mengonfigurasi proksi seluruh sistem. Hubungi administrator sistem untuk pengaturan proksi dan cara mengonfigurasinya untuk lingkungan Anda.

PowerShell sendiri mungkin tidak dikonfigurasi untuk menggunakan proksi ini secara otomatis. Dengan PowerShell 5.1 dan yang lebih baru, konfigurasi sesi PowerShell agar menggunakan proksi menggunakan perintah berikut:

```powershell
$webClient = New-Object System.Net.WebClient
$webClient.Proxy.Credentials = [System.Net.CredentialCache]::DefaultNetworkCredentials
```

Jika kredensial sistem operasi Anda dikonfigurasi dengan benar, konfigurasi ini mer rutekan permintaan PowerShell melalui proksi. Agar pengaturan ini tetap ada di antara sesi, tambahkan perintah ke profil [PowerShell Anda](/powershell/module/microsoft.powershell.core/about/about_profiles).

Untuk menginstal paket, proksi Anda perlu mengizinkan koneksi HTTPS ke alamat berikut:

* `https://www.powershellgallery.com`

## <a name="sign-in"></a>Tandatangan

Untuk mulai bekerja dengan Azure PowerShell, masuk dengan kredensial Azure Anda.

```powershell-interactive
# Connect to Azure with a browser sign in token
Connect-AzAccount
```

> [!NOTE]
> Jika Anda telah menonaktifkan muatan otomatis modul, impor modul secara manual dengan `Import-Module -Name Az` .
> Karena cara modul disusun, ini dapat memakan waktu beberapa detik.

Anda harus mengulangi langkah-langkah ini untuk setiap sesi PowerShell baru yang anda mulai. Untuk mempelajari cara tetap masuk ke Azure di seluruh sesi PowerShell, lihat Tetap [menggunakan kredensial pengguna di seluruh sesi PowerShell.](context-persistence.md)

## <a name="update-the-azure-powershell-module"></a>Memperbarui Azure PowerShell otomatis

Untuk memperbarui modul PowerShell, Anda harus menggunakan metode yang sama untuk menginstal modul. Misalnya, jika sebelumnya menggunakan `Install-Module` , Anda harus menggunakan [Update-Module untuk](/powershell/module/powershellget/update-module) mendapatkan versi terbaru. Jika sebelumnya menggunakan paket MSI, Anda harus mengunduh dan menginstal paket MSI baru.

Cmdlet PowerShellGet tidak bisa memperbarui modul yang diinstal dari paket MSI. Paket MSI tidak memperbarui modul yang diinstal menggunakan PowerShellGet. Jika mengalami masalah saat memperbarui menggunakan PowershellGet, Anda harus **menginstal ulang**, bukan **memperbarui**. Penginstalan ulang dilakukan dengan cara yang sama seperti menginstal, namun Anda perlu menambahkan `-Force` parameter:

```powershell
if (Get-Module -Name AzureRM -ListAvailable) {
    Write-Warning -Message ('Az module not installed. Having both the AzureRM and ' +
      'Az modules installed at the same time is not supported.')
} else {
    Install-Module -Name Az -AllowClobber -Force
}
```

Tidak seperti penginstalan berbasis MSI, menginstal atau memperbarui menggunakan PowerShellGet tidak menghapus versi lama yang mungkin ada di sistem Anda. Untuk menghapus versi lama Azure PowerShell dari sistem Anda, lihat [Menghapus Azure PowerShell modul](uninstall-az-ps.md). Untuk informasi selengkapnya tentang penginstalan berbasis MSI, lihat [Menginstal Azure PowerShell dengan MSI.](install-az-ps-msi.md)

## <a name="use-multiple-versions-of-azure-powershell"></a>Menggunakan beberapa versi Azure PowerShell

Anda dapat menginstal lebih dari satu versi Azure PowerShell. Untuk memeriksa apakah Anda memiliki beberapa versi Azure PowerShell diinstal, gunakan perintah berikut:

```powershell-interactive
Get-InstalledModule -Name Az -AllVersions | Select-Object -Property Name, Version
```

Untuk menghapus versi yang Azure PowerShell, lihat [Menghapus Azure PowerShell instalan modul](uninstall-az-ps.md).

Jika Anda memiliki lebih dari satu versi modul yang terinstal, muat otomatis modul `Import-Module` dan muat versi terbaru secara default.

Anda dapat menginstal atau memuat versi modul `Az` tertentu menggunakan `-RequiredVersion` parameter:

```powershell-interactive
# Install Az version 3.6.1
Install-Module -Name Az -RequiredVersion 3.6.1
# Load Az version 3.6.1
Import-Module -Name Az -RequiredVersion 3.6.1
```

## <a name="provide-feedback"></a>Berikan umpan balik

Jika menemukan bug dalam Azure PowerShell, [kan ada masalah di GitHub](https://github.com/Azure/azure-powershell/issues). Untuk memberikan umpan balik dari baris perintah, gunakan cmdlet [Kirim-Umpan](/powershell/module/az.accounts/send-feedback) Balik.

## <a name="next-steps"></a>Langkah Berikutnya

Untuk mempelajari selengkapnya tentang modul Azure PowerShell fiturnya, lihat Mulai [dengan Azure PowerShell](get-started-azureps.md). Jika Anda sudah terbiasa dengan lebih Azure PowerShell dan perlu melakukan migrasi dari AzureRM, lihat Melakukan [migrasi dari AzureRM ke Az](migrate-from-azurerm-to-az.md).
