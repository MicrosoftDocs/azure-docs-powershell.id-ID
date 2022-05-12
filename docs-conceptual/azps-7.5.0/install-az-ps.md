---
description: Cara menginstal Azure Az PowerShell dengan PowerShellGet
ms.custom: devx-track-azurepowershell
ms.date: 05/11/2022
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
title: Menginstal modul Azure Az PowerShell
ms.openlocfilehash: 81095a4e38a04045a53a5aa159cb27b427ba6686
ms.sourcegitcommit: 97a10cac523612de4dbece96f25bd7e3f2431276
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/12/2022
ms.locfileid: "144957609"
---
# <a name="install-the-azure-az-powershell-module"></a>Menginstal modul Azure Az PowerShell

Artikel ini menjelaskan cara menginstal modul Azure Az PowerShell menggunakan [PowerShellGet](/powershell/scripting/gallery/installing-psget). Instruksi ini bekerja pada platform Windows, macOS, dan Linux.

Modul Azure Az PowerShell diinstal sebelumnya di Azure [Cloud Shell](/azure/cloud-shell/overview) dan di [citra Docker](azureps-in-docker.md).

Modul Azure Az PowerShell adalah modul rollup. Menginstalnya berarti mengunduh modul Az PowerShell yang tersedia secara umum, dan membuat cmdlet-nya tersedia untuk digunakan.

## <a name="requirements"></a>Persyaratan

> [!NOTE]
> PowerShell 7.0.6 LTS, PowerShell 7.1.3, atau lebih tinggi adalah versi PowerShell yang direkomendasikan untuk digunakan dengan modul Azure Az PowerShell di semua platform.

Azure PowerShell tidak memiliki persyaratan tambahan saat dijalankan di PowerShell 7.0.6 LTS dan PowerShell 7.1.3 atau versi yang lebih baru.

- Pasang [versi terbaru PowerShell](/powershell/scripting/install/installing-powershell) yang tersedia untuk sistem operasi Anda.

Untuk memeriksa versi PowerShell Anda, jalankan perintah berikut dari dalam sesi PowerShell:

```powershell
$PSVersionTable.PSVersion
```

Kebijakan eksekusi skrip PowerShell harus berupa diatur ke ditandai jarak jauh atau kurang membatasi.
`Get-ExecutionPolicy -List` dapat digunakan untuk menentukan kebijakan eksekusi saat ini. Untuk informasi selengkapnya, lihat [about_Execution_Policies](/powershell/module/microsoft.powershell.core/about/about_execution_policies).

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```

## <a name="installation"></a>Penginstalan

Menggunakan cmdlet [Install-Module](/powershell/module/powershellget/install-module) adalah metode penginstalan yang diutamakan untuk modul Az PowerShell. Pasang modul Az hanya untuk pengguna saat ini.
Ini adalah cakupan penginstalan yang direkomendasikan. Metode ini bekerja sama pada platform Windows, macOS, dan Linux. Jalankan perintah dari sesi PowerShell berikut ini:

```powershell
Install-Module -Name Az -Scope CurrentUser -Repository PSGallery -Force
```

## <a name="other-installation-options"></a>Opsi Penginstalan Lainnya

Saat PowerShell 7.0.6 LTS, PowerShell 7.1.3, atau versi yang lebih baru adalah versi PowerShell yang direkomendasikan, dan `Install-Module` adalah opsi penginstalan yang direkomendasikan, terdapat opsi penginstalan tambahan jika diperlukan.

### <a name="installation-on-windows-powershell"></a>Penginstalan di Windows PowerShell

> [!IMPORTANT]
> Jika Anda menginstal modul AzureRM PowerShell, lihat bagian [koeksistensi Az dan AzureRM](install-az-ps.md#az-and-azurerm-coexistence) dari artikel ini sebelum melanjutkan.

Modul Azure Az PowerShell juga didukung untuk penggunaan dengan PowerShell 5.1 di Windows. Untuk menggunakan modul Azure Az PowerShell di PowerShell 5.1 di Windows:

1. Perbarui ke [Windows PowerShell 5.1](/powershell/scripting/windows-powershell/install/installing-windows-powershell#upgrading-existing-windows-powershell).
   Jika menggunakan Windows 10 versi 1607 atau lebih tinggi, Anda telah menginstal PowerShell 5.1.
1. Instal [.NET Framework 4.7.2 or versi lebih baru](/dotnet/framework/install).
1. Pastikan Anda telah menginstal PowerShellGet versi terbaru. Jalankan `Install-Module -Name PowerShellGet -Force`.

### <a name="offline-installation"></a>Penginstalan Offline

Di beberapa lingkungan, tidak mungkin untuk terhubung ke Galeri PowerShell. Dalam situasi tersebut, Anda dapat menginstal modul Az PowerShell secara offline menggunakan salah satu metode ini:

- [Unduh Azure PowerShell MSI](install-az-ps-msi.md). Perlu diingat bahwa penginstal MSI hanya berfungsi untuk PowerShell 5.1 di Windows.
- Unduh modul ke lokasi lain di jaringan Anda dan gunakan sebagai sumber penginstalan.
  Metode ini memungkinkan Anda menyimpan modul PowerShell pada satu server atau berbagi file untuk disebarkan dengan PowerShellGet ke sistem yang terputus. Pelajari cara menyiapkan repositori lokal dan menginstal pada sistem yang terputus dengan [Bekerja dengan repositori PowerShellGet lokal](/powershell/scripting/gallery/how-to/working-with-local-psrepositories).
- Simpan modul dengan [Simpan-Modul](/powershell/module/PowershellGet/Save-Module) ke berbagi file, atau simpan ke sumber lain dan salin secara manual ke mesin lain.

## <a name="sign-in"></a>Masuk

Untuk mulai bekerja dengan Azure PowerShell, masuk dengan info masuk Azure Anda.

```azurepowershell
Connect-AzAccount
```

Setelah menjalankan perintah ini, jendela browser baru akan muncul dan Anda dapat masuk ke akun Azure Anda.

## <a name="update-the-azure-powershell-module"></a>Memperbarui modul Azure PowerShell

Untuk memperbarui modul PowerShell apa pun, Anda harus menggunakan metode yang sama yang digunakan untuk menginstal modul. Misalnya, jika Anda awalnya menggunakan `Install-Module`, Anda harus menggunakan [Update-Module](/powershell/module/powershellget/update-module) untuk mendapatkan versi terbaru. Jika Anda awalnya menggunakan paket MSI, Anda harus mengunduh dan menginstal paket MSI baru.

Cmdlet PowerShellGet tidak dapat memperbarui modul yang diinstal dari paket MSI. Paket MSI tidak memperbarui modul yang diinstal menggunakan PowerShellGet. Jika Anda memiliki masalah saat memperbarui menggunakan PowerShellGet, Anda harus **menginstal ulang**, bukan **memperbarui**. Menginstal ulang dilakukan dengan cara yang sama seperti saat menginstal. Pastikan Anda menggunakan parameter `Force` dengan `Install-Module` saat menginstal ulang.

Tidak seperti penginstalan berbasis MSI, menginstal atau memperbarui menggunakan PowerShellGet tidak menghapus versi lama yang mungkin ada di sistem Anda.

> [!NOTE]
> Penghapusan instalan dapat menjadi rumit jika Anda memiliki lebih dari satu versi modul Az PowerShell yang terinstal. Karena kompleksitas ini, kami hanya mendukung penghapusan instalan semua versi modul Az PowerShell yang saat ini terinstal.

Untuk menghapus semua versi modul Az PowerShell dari sistem Anda, lihat [Menghapus instalan modul Azure PowerShell](uninstall-az-ps.md). Untuk informasi selengkapnya tentang instalasi berbasis MSI, lihat [Menginstal Azure PowerShell dengan MSI](install-az-ps-msi.md).

## <a name="troubleshooting"></a>Pemecahan Masalah

Berikut beberapa masalah umum yang muncul saat menginstal Azure Az PowerShell. Jika masalah Anda tidak tercantum di sini, [ajukan masalah di GitHub](https://github.com/azure/azure-powershell/issues).

### <a name="az-and-azurerm-coexistence"></a>Koeksistensi Az dan AzureRM

> [!WARNING]
> Kami tidak mendukung modul AzureRM dan Az diinstal untuk PowerShell 5.1 di Windows pada saat yang bersamaan.

Dalam skenario di mana Anda ingin menginstal AzureRM dan modul Az PowerShell di sistem yang sama, AzureRM harus diinstal hanya di cakupan pengguna untuk Windows PowerShell. Pasang modul Az PowerShell untuk PowerShell 7.0.6 LTS, PowerShell 7.1.3, atau versi yang lebih tinggi di sistem yang sama.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

#### <a name="visual-studio"></a>Visual Studio

Versi Visual Studio yang lebih lama dapat menginstal Azure PowerShell sebagai bagian dari beban kerja pengembangan Azure, yang menginstal modul AzureRM. Azure PowerShell dapat dihapus menggunakan penginstal Visual Studio atau dengan menggunakan "Uninstall" di Aplikasi & fitur. Jika Anda telah menginstal PowerShell 7.x, Anda mungkin harus [menginstal secara manual](install-az-ps.md#installation) modul Azure Az PowerShell.

### <a name="proxy-blocks-connection"></a>Koneksi blok proksi

Jika Anda mendapatkan kesalahan dari `Install-Module` di mana Galeri PowerShell tidak dapat dijangkau, Anda mungkin berada di belakang proksi. Sistem operasi dan lingkungan jaringan yang berbeda memiliki persyaratan yang berbeda untuk mengonfigurasi proksi di seluruh sistem. Hubungi administrator sistem Anda untuk pengaturan proksi Anda dan cara mengonfigurasinya untuk lingkungan Anda.

PowerShell sendiri mungkin tidak dikonfigurasi untuk menggunakan proksi ini secara otomatis. Dengan PowerShell 5.1 dan yang lebih baru, konfigurasikan sesi PowerShell untuk menggunakan proksi menggunakan perintah berikut:

```powershell
$webClient = New-Object -TypeName System.Net.WebClient
$webClient.Proxy.Credentials = [System.Net.CredentialCache]::DefaultNetworkCredentials
```

Jika info masuk sistem operasi Anda dikonfigurasi dengan benar, konfigurasi ini merutekan permintaan PowerShell melalui proksi. Agar pengaturan ini bertahan di antara sesi, tambahkan perintah ke [profil PowerShell](/powershell/module/microsoft.powershell.core/about/about_profiles) Anda.

Untuk menginstal paket, proksi Anda harus memungkinkan koneksi HTTPS ke [www.powershellgallery.com](https://www.powershellgallery.com).

## <a name="provide-feedback"></a>Berikan umpan balik

Jika Anda menemukan bug di modul Azure Az PowerShell, [ajukan masalah di GitHub](https://github.com/Azure/azure-powershell/issues). Untuk memberikan umpan balik di sesi PowerShell, gunakan cmdlet [Send-Feedback](/powershell/module/az.accounts/send-feedback).

## <a name="next-steps"></a>Langkah berikutnya

Untuk mempelajari selengkapnya tentang modul Azure Az PowerShell dan fiturnya, lihat [Memulai dengan Azure PowerShell](get-started-azureps.md). Jika Anda terbiasa dengan Azure PowerShell dan perlu bermigrasi dari AzureRM, lihat [Memigrasi dari AzureRM ke Az](migrate-from-azurerm-to-az.md).
