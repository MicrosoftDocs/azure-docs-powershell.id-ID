---
title: Menginstal modul PowerShell Azure Az
description: Cara menginstal PowerShell Azure Az dengan PowerShellGet
ms.devlang: powershell
ms.topic: conceptual
ms.date: 11/02/2021
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
ms.openlocfilehash: b73a51b3fec11484b1083558284cb78dde633039
ms.sourcegitcommit: b7ef209e489945ce397bbbba2c5f34fa6b2ca22e
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "132429518"
---
# <a name="install-the-azure-az-powershell-module"></a>Menginstal modul PowerShell Azure Az

Artikel ini menjelaskan cara menginstal modul Azure Az PowerShell menggunakan [PowerShellGet](/powershell/scripting/gallery/installing-psget). Instruksi ini berfungsi di Windows, macOS, dan Linux.

Modul PowerShell Azure Az telah diinstal sebelumnya di Azure [Cloud Shell](/azure/cloud-shell/overview) dan dalam [gambar Docker](azureps-in-docker.md).

Modul PowerShell Azure Az adalah modul rollup. Menginstalnya akan mengunduh modul Az PowerShell yang tersedia secara umum, dan cmdlets mereka tersedia untuk digunakan.

## <a name="requirements"></a>Persyaratan

> [!NOTE]
> PowerShell 7.0.6 LTS, PowerShell 7.1.3, atau yang lebih tinggi adalah versi PowerShell yang disarankan untuk digunakan dengan modul PowerShell Azure Az di semua platform.

Azure PowerShell tidak memiliki persyaratan tambahan saat menjalankan PowerShell 7.0.6 LTS dan PowerShell 7.1.3 atau yang lebih tinggi.

- Instal [versi terbaru PowerShell yang](/powershell/scripting/install/installing-powershell) tersedia untuk sistem operasi Anda.

Untuk memeriksa versi PowerShell, jalankan perintah berikut ini dari dalam sesi PowerShell:

```azurepowershell
$PSVersionTable.PSVersion
```

Kebijakan eksekusi skrip PowerShell harus diatur ke bertanda tangan jarak jauh atau yang kurang terbatas.
`Get-ExecutionPolicy -List` dapat digunakan untuk menentukan kebijakan eksekusi saat ini. Untuk informasi selengkapnya, [lihat about_Execution_Policies](/powershell/module/microsoft.powershell.core/about/about_execution_policies).

```powershell
Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser
```

## <a name="installation"></a>Penginstalan

Menggunakan cmdlet [Install-Module](/powershell/module/powershellget/install-module) adalah metode penginstalan pilihan untuk modul Az PowerShell. Instal modul Az hanya untuk pengguna saat ini.
Ini adalah lingkup instalasi yang direkomendasikan. Metode ini berfungsi sama pada platform Windows, macOS, dan Linux. Jalankan perintah berikut dari sesi PowerShell:

```powershell
Install-Module -Name Az -Scope CurrentUser -Repository PSGallery -Force
```

## <a name="other-installation-options"></a>Opsi Penginstalan Lainnya

Sementara PowerShell 7.0.6 LTS, PowerShell 7.1.3, atau yang lebih tinggi merupakan versi PowerShell yang disarankan, dan merupakan opsi penginstalan yang disarankan, ada opsi penginstalan tambahan jika `Install-Module` diperlukan.

### <a name="installation-on-windows-powershell"></a>Instalasi pada Windows PowerShell

> [!IMPORTANT]
> Jika Anda telah menginstal modul PowerShell AzureRM, lihat bagian [koeksistensi Az](install-az-ps.md#az-and-azurerm-coexistence) dan AzureRM dari artikel ini sebelum melanjutkan.

Modul PowerShell Azure Az juga didukung untuk digunakan dengan PowerShell 5.1 di Windows. Untuk menggunakan modul PowerShell Azure Az di PowerShell 5.1 di Windows:

1. Perbarui ke [Windows PowerShell 5.1](/powershell/scripting/windows-powershell/install/installing-windows-powershell#upgrading-existing-windows-powershell).
   Jika menggunakan versi Windows 10 1607 atau lebih tinggi, Anda telah menginstal PowerShell 5.1.
2. Instal [.NET Framework 4.7.2 atau yang lebih baru.](/dotnet/framework/install)
3. Pastikan Anda memiliki PowerShell versi terbaruGet. Jalankan `Install-Module -Name PowerShellGet -Force` .

### <a name="offline-installation"></a>Instalasi Offline

Di beberapa lingkungan, tidak dimungkinkan untuk menyambungkan ke Galeri PowerShell. Dalam situasi tersebut, Anda bisa menginstal modul Az PowerShell secara offline menggunakan salah satu metode ini:

- [Unduh Azure PowerShell MSI](install-az-ps-msi.md). Ingatlah bahwa penginstal MSI hanya berfungsi untuk PowerShell 5.1 di Windows.
- Unduh modul ke lokasi lain di jaringan Anda dan gunakan modul sebagai sumber instalasi.
  Metode ini memungkinkan Anda membuat cache modul PowerShell di satu server atau berbagi file untuk digunakan dengan PowerShellGet ke semua sistem terputus. Pelajari cara menyiapkan repositori lokal dan menginstal di sistem terputus dengan Bekerja [dengan penyimpanan PowerShell lokalGet](/powershell/scripting/gallery/how-to/working-with-local-psrepositories).
- Simpan modul dengan [Simpan-Modul](/powershell/module/PowershellGet/Save-Module) ke berbagi file, atau simpan ke sumber lain dan salin secara manual ke komputer lain.

## <a name="sign-in"></a>Tandatangan

Untuk mulai bekerja dengan Azure PowerShell, masuk dengan kredensial Azure Anda.

```powershell
Connect-AzAccount
```

Setelah menjalankan perintah ini, jendela browser baru akan muncul dan Anda dapat masuk ke akun Azure.

## <a name="update-the-azure-powershell-module"></a>Memperbarui modul Azure PowerShell

Untuk memperbarui modul PowerShell, Anda harus menggunakan metode yang sama untuk menginstal modul. Misalnya, jika sebelumnya menggunakan `Install-Module` , Anda harus menggunakan [Update-Module untuk](/powershell/module/powershellget/update-module) mendapatkan versi terbaru. Jika sebelumnya menggunakan paket MSI, Anda harus mengunduh dan menginstal paket MSI baru.

Cmdlet PowerShellGet tidak bisa memperbarui modul yang diinstal dari paket MSI. Paket MSI tidak memperbarui modul yang diinstal menggunakan PowerShellGet. Jika mengalami masalah saat memperbarui menggunakan PowerShellGet, Anda harus **menginstal ulang**, bukan **memperbarui**. Menginstal ulang dilakukan dengan cara yang sama seperti menginstal. Pastikan Anda menggunakan `Force` parameter ketika `Install-Module` menginstal ulang.

Tidak seperti penginstalan berbasis MSI, menginstal atau memperbarui menggunakan PowerShellGet tidak menghapus versi lama yang mungkin ada pada sistem Anda.

> [!NOTE]
> Penghapusan instalan bisa rumit jika Anda memiliki lebih dari satu versi modul Az PowerShell yang terinstal. Karena kompleksitas ini, kami hanya mendukung penghapusan instalan semua versi modul Az PowerShell yang saat ini terinstal.

Untuk menghapus semua versi modul Az PowerShell dari sistem Anda, lihat [Menghapus Azure PowerShell modul](uninstall-az-ps.md). Untuk informasi selengkapnya tentang penginstalan berbasis MSI, lihat [Menginstal Azure PowerShell dengan MSI.](install-az-ps-msi.md)

## <a name="troubleshooting"></a>Pemecahan masalah

Berikut adalah beberapa masalah umum yang terlihat saat menginstal modul PowerShell Azure Az. Jika Anda mengalami masalah yang tidak tercantum di sini, [cantumkan masalah pada GitHub](https://github.com/azure/azure-powershell/issues).

### <a name="az-and-azurerm-coexistence"></a>Koeksistensi Az dan AzureRM

> [!WARNING]
> Kami tidak mendukung modul AzureRM dan Az yang terinstal untuk PowerShell 5.1 di Windows saat yang sama.

Dalam skenario di mana Anda ingin menginstal modul AzureRM dan Az PowerShell pada sistem yang sama, AzureRM harus diinstal hanya dalam lingkup pengguna untuk Windows PowerShell. Instal modul Az PowerShell untuk PowerShell 7.0.6 LTS, PowerShell 7.1.3, atau yang lebih tinggi dalam sistem yang sama.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

#### <a name="visual-studio"></a>Visual Studio

Versi lama Visual Studio mungkin Azure PowerShell beban kerja pengembangan Azure, yang menginstal modul AzureRM. Azure PowerShell dapat dihapus menggunakan penginstal Visual Studio atau menggunakan "Hapus instalan" di Aplikasi & otomatis. Jika Anda sudah menginstal PowerShell 7.x, Anda mungkin harus [menginstal modul](install-az-ps.md#installation) PowerShell Azure Az secara manual.

### <a name="proxy-blocks-connection"></a>Proksi memblokir koneksi

Jika mendapatkan kesalahan dari `Install-Module` Galeri PowerShell tidak dapat dijangkau, Anda mungkin di belakang proksi. Sistem operasi dan lingkungan jaringan yang berbeda memiliki persyaratan berbeda untuk mengonfigurasi proksi seluruh sistem. Hubungi administrator sistem untuk pengaturan proksi dan cara mengonfigurasinya untuk lingkungan Anda.

PowerShell sendiri mungkin tidak dikonfigurasi untuk menggunakan proksi ini secara otomatis. Dengan PowerShell 5.1 dan yang lebih baru, konfigurasi sesi PowerShell agar menggunakan proksi menggunakan perintah berikut:

```powershell
$webClient = New-Object -TypeName System.Net.WebClient
$webClient.Proxy.Credentials = [System.Net.CredentialCache]::DefaultNetworkCredentials
```

Jika kredensial sistem operasi Anda dikonfigurasi dengan benar, konfigurasi ini mer rutekan permintaan PowerShell melalui proksi. Agar pengaturan ini tetap ada di antara sesi, tambahkan perintah ke profil [PowerShell Anda](/powershell/module/microsoft.powershell.core/about/about_profiles).

Untuk menginstal paket, proksi Anda perlu mengizinkan koneksi HTTPS [www.powershellgallery.com](https://www.powershellgallery.com).

## <a name="provide-feedback"></a>Berikan umpan balik

Jika Anda menemukan bug dalam modul PowerShell Azure Az, [mengajukan masalah di GitHub](https://github.com/Azure/azure-powershell/issues). Untuk memberikan umpan balik dari dalam sesi PowerShell, gunakan cmdlet [Kirim-Umpan](/powershell/module/az.accounts/send-feedback) Balik.

## <a name="next-steps"></a>Langkah Berikutnya

Untuk mempelajari selengkapnya tentang modul PowerShell Azure Az dan fiturnya, lihat [Mulai dengan Azure PowerShell](get-started-azureps.md). Jika Anda sudah terbiasa dengan lebih Azure PowerShell dan perlu melakukan migrasi dari AzureRM, lihat Melakukan [migrasi dari AzureRM ke Az](migrate-from-azurerm-to-az.md).
