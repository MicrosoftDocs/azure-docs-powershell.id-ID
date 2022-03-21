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
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132427997"
---
# <a name="install-azure-powershell"></a>Memasang Azure PowerShell

Artikel ini menjelaskan cara menginstal modul Azure PowerShell menggunakan [PowerShellGet](/powershell/scripting/gallery/installing-psget). Instruksi ini bekerja pada platform Windows, macOS, dan Linux.

Azure PowerShell juga tersedia di Azure [Cloud Shell](/azure/cloud-shell/overview).

## <a name="requirements"></a>Persyaratan

Azure PowerShell bekerja dengan PowerShell 5.1 atau versi lebih tinggi di Windows, atau di semua platform dengan PowerShell Core 6.x dan versi lebih baru. Anda harus menginstal [versi terbaru PowerShell](/powershell/scripting/install/installing-powershell) yang tersedia untuk sistem operasi Anda. Azure PowerShell tidak memiliki persyaratan tambahan saat dijalankan di PowerShell 6.2.4 dan yang lebih baru.

Untuk memeriksa versi PowerShell Anda, jalankan perintah:

```azurepowershell-interactive
$PSVersionTable.PSVersion
```

Untuk menggunakan Azure PowerShell di PowerShell 5.1 pada Windows:

1. Perbarui ke [Windows PowerShell 5.1](/powershell/scripting/windows-powershell/install/installing-windows-powershell#upgrading-existing-windows-powershell).
   Jika menggunakan Windows 10 versi 1607 atau lebih tinggi, Anda sudah menginstal PowerShell 5.1.
2. Instal [.NET Framework 4.7.2 or versi lebih baru](/dotnet/framework/install).
3. Pastikan Anda telah menginstal PowerShellGet versi terbaru. Jalankan `Install-Module -Name PowerShellGet -Force`.

## <a name="install-the-azure-powershell-module"></a>Menginstal modul Azure PowerShell

> [!WARNING]
> Kami tidak mendukung modul AzureRM dan Az diinstal untuk PowerShell 5.1 di Windows pada saat yang bersamaan. Jika Anda perlu menjaga AzureRM tetap tersedia di sistem Anda, instal modul Az untuk PowerShell 6.2.4 atau yang lebih baru.

Penggunaan cmdlet PowerShellGet adalah metode penginstalan yang lebih disarankan. Instal modul Az hanya untuk pengguna saat ini. Ini adalah cakupan penginstalan yang direkomendasikan. Metode ini bekerja sama pada platform Windows, macOS, dan Linux. Jalankan perintah dari sesi PowerShell berikut ini:

```powershell-interactive
if (Get-Module -Name AzureRM -ListAvailable) {
    Write-Warning -Message ('Az module not installed. Having both the AzureRM and ' +
      'Az modules installed at the same time is not supported.')
} else {
    Install-Module -Name Az -AllowClobber -Scope CurrentUser
}
```

Secara default, galeri PowerShell tidak dikonfigurasi sebagai repositori tepercaya untuk PowerShellGet. Pertama kali Anda menggunakan PSGallery, Anda akan melihat perintah berikut:

```Output
Untrusted repository

You are installing the modules from an untrusted repository. If you trust this repository, change
its InstallationPolicy value by running the `Set-PSRepository` cmdlet.

Are you sure you want to install the modules from 'PSGallery'?
[Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "N"):
```

Jawab `Yes` atau `Yes to All` untuk melanjutkan pemasangan.

Menginstal modul untuk semua pengguna pada sistem memerlukan hak istimewa yang tinggi. Mulai sesi PowerShell menggunakan **Jalankan sebagai administrator** di Windows atau gunakan perintah `sudo` di macOS atau Linux:

```powershell-interactive
if (Get-Module -Name AzureRM -ListAvailable) {
    Write-Warning -Message ('Az module not installed. Having both the AzureRM and ' +
      'Az modules installed at the same time is not supported.')
} else {
    Install-Module -Name Az -AllowClobber -Scope AllUsers
}
```

Modul Az adalah modul rollup untuk cmdlet Azure PowerShell. Menginstalnya berarti mengunduh semua modul Az PowerShell yang tersedia secara umum, dan membuat cmdlet-nya tersedia untuk digunakan.

## <a name="install-offline"></a>Menginstal secara Offline

Di beberapa lingkungan, tidak mungkin untuk terhubung ke Galeri PowerShell. Dalam situasi tersebut, Anda masih dapat menginstal secara offline menggunakan salah satu metode ini:

* Unduh modul ke lokasi lain di jaringan Anda dan gunakan sebagai sumber penginstalan.
  Metode ini memungkinkan Anda menyimpan modul PowerShell pada satu server atau berbagi file untuk disebarkan dengan PowerShellGet ke sistem yang terputus. Pelajari cara menyiapkan repositori lokal dan menginstal pada sistem yang terputus dengan [Bekerja dengan repositori PowerShellGet lokal](/powershell/scripting/gallery/how-to/working-with-local-psrepositories).
* [Unduh Azure PowerShell MSI](install-az-ps-msi.md) ke mesin yang terhubung ke jaringan, lalu salin penginstal ke sistem tanpa akses ke Galeri PowerShell. Perlu diingat bahwa penginstal MSI hanya berfungsi untuk PowerShell 5.1 di Windows.
* Simpan modul dengan [Simpan-Modul](/powershell/module/PowershellGet/Save-Module) ke berbagi file, atau simpan ke sumber lain dan salin secara manual ke mesin lain:

  ```powershell-interactive
  Save-Module -Name Az -Path '\\server\share\PowerShell\modules' -Force
  ```

## <a name="troubleshooting"></a>Pemecahan Masalah

Berikut beberapa masalah umum yang muncul saat menginstal Azure PowerShell. Jika masalah Anda tidak tercantum di sini, [ajukan masalah di GitHub](https://github.com/azure/azure-powershell/issues).

### <a name="proxy-blocks-connection"></a>Koneksi blok proksi

Jika Anda mendapatkan kesalahan dari `Install-Module` yang menunjukkan Galeri PowerShell tidak dapat dijangkau, Anda mungkin berada di belakang proksi. Sistem operasi dan lingkungan jaringan yang berbeda memiliki persyaratan yang berbeda untuk mengonfigurasi proksi di seluruh sistem. Hubungi administrator sistem Anda untuk pengaturan proksi Anda dan cara mengonfigurasinya untuk lingkungan Anda.

PowerShell sendiri mungkin tidak dikonfigurasi untuk menggunakan proksi ini secara otomatis. Dengan PowerShell 5.1 dan yang lebih baru, konfigurasikan sesi PowerShell untuk menggunakan proksi menggunakan perintah berikut:

```powershell
$webClient = New-Object System.Net.WebClient
$webClient.Proxy.Credentials = [System.Net.CredentialCache]::DefaultNetworkCredentials
```

Jika info masuk sistem operasi Anda dikonfigurasi dengan benar, konfigurasi ini merutekan permintaan PowerShell melalui proksi. Agar pengaturan ini bertahan di antara sesi, tambahkan perintah ke [profil PowerShell](/powershell/module/microsoft.powershell.core/about/about_profiles) Anda.

Untuk menginstal paket, proksi Anda perlu mengizinkan koneksi HTTPS ke alamat berikut:

* `https://www.powershellgallery.com`

## <a name="sign-in"></a>Masuk

Untuk mulai bekerja dengan Azure PowerShell/Azure CLI, masuk dengan info masuk Azure Anda.

```powershell-interactive
# Connect to Azure with a browser sign in token
Connect-AzAccount
```

> [!NOTE]
> Jika Anda telah menonaktifkan pemuatan otomatis modul, impor modul secara manual dengan `Import-Module -Name Az`.
> Karena cara modul disusun, ini bisa memakan waktu beberapa detik.

Anda harus mengulangi langkah-langkah ini untuk setiap sesi PowerShell baru yang Anda mulai. Untuk mempelajari cara mempertahankan masuk Azure Anda di seluruh sesi PowerShell, lihat [Mempertahankan info masuk pengguna di seluruh sesi PowerShell](context-persistence.md).

## <a name="update-the-azure-powershell-module"></a>Memperbarui modul Azure PowerShell

Untuk memperbarui modul PowerShell apa pun, Anda harus menggunakan metode yang sama yang digunakan untuk menginstal modul. Misalnya, jika Anda awalnya menggunakan `Install-Module`, Anda harus menggunakan [Update-Module](/powershell/module/powershellget/update-module) untuk mendapatkan versi terbaru. Jika Anda awalnya menggunakan paket MSI, Anda harus mengunduh dan menginstal paket MSI baru.

Cmdlet PowerShellGet tidak dapat memperbarui modul yang diinstal dari paket MSI. Paket MSI tidak memperbarui modul yang diinstal menggunakan PowerShellGet. Jika Anda memiliki masalah saat memperbarui menggunakan PowershellGet, Anda harus **menginstal ulang**, bukan **memperbarui**. Menginstal ulang dilakukan dengan cara yang sama seperti menginstal, tetapi Anda perlu menambahkan parameter `-Force`:

```powershell
if (Get-Module -Name AzureRM -ListAvailable) {
    Write-Warning -Message ('Az module not installed. Having both the AzureRM and ' +
      'Az modules installed at the same time is not supported.')
} else {
    Install-Module -Name Az -AllowClobber -Force
}
```

Tidak seperti penginstalan berbasis MSI, menginstal atau memperbarui menggunakan PowerShellGet tidak menghapus versi lama yang mungkin ada di sistem Anda. Untuk menghapus versi lama Azure PowerShell dari sistem Anda, lihat [Modul Menghapus instalan Azure PowerShell](uninstall-az-ps.md). Untuk informasi selengkapnya tentang instalasi berbasis MSI, lihat [Menginstal Azure PowerShell dengan MSI](install-az-ps-msi.md).

## <a name="use-multiple-versions-of-azure-powershell"></a>Menggunakan beberapa versi Azure PowerShell

Anda dapat menginstal lebih dari satu versi Azure PowerShell. Untuk memeriksa apakah Anda telah menginstal beberapa versi Azure PowerShell, gunakan perintah berikut:

```powershell-interactive
Get-InstalledModule -Name Az -AllVersions | Select-Object -Property Name, Version
```

Untuk menghapus versi Azure PowerShell, lihat [Modul Menghapus instalan Azure PowerShell](uninstall-az-ps.md).

Jika Anda memiliki lebih dari satu versi modul yang diinstal, modul memuat otomatis dan `Import-Module` memuat versi terbaru secara default.

Anda dapat menginstal atau memuat versi `Az` modul tertentu dengan menggunakan parameter `-RequiredVersion`:

```powershell-interactive
# Install Az version 3.6.1
Install-Module -Name Az -RequiredVersion 3.6.1
# Load Az version 3.6.1
Import-Module -Name Az -RequiredVersion 3.6.1
```

## <a name="provide-feedback"></a>Berikan umpan balik

Jika Anda menemukan bug di Azure PowerShell, [ajukan masalah di GitHub](https://github.com/Azure/azure-powershell/issues). Untuk memberikan umpan balik dari baris perintah, gunakan cmdlet [Send-Feedback](/powershell/module/az.accounts/send-feedback).

## <a name="next-steps"></a>Langkah berikutnya

Untuk mempelajari lebih lanjut tentang modul Azure PowerShell dan fitur-fiturnya, lihat [Mulai dengan Azure PowerShell](get-started-azureps.md). Jika Anda terbiasa dengan Azure PowerShell dan perlu bermigrasi dari AzureRM, lihat [Memigrasi dari AzureRM ke Az](migrate-from-azurerm-to-az.md).
