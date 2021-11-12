---
title: Melakukan Azure PowerShell skrip dari AzureRM ke Az
description: Pelajari langkah-langkah dan alat untuk melakukan migrasi skrip dari modul AzureRM ke modul Az yang baru.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 05/10/2019
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
ms.openlocfilehash: a0a6fcbc0a7bdae507ff5e16dd844e8425c929d5
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132421100"
---
# <a name="migrate-azure-powershell-from-azurerm-to-az"></a>Melakukan Azure PowerShell dari AzureRM ke Az

Modul Az memiliki fitur yang sama dengan AzureRM, namun menggunakan nama cmdlet yang lebih singkat dan lebih konsisten.
Skrip yang ditulis untuk cmdlet AzureRM tidak akan bekerja secara otomatis dengan modul baru. Untuk memudahkan transisi, Az menawarkan alat untuk memungkinkan Anda menjalankan skrip yang sudah ada menggunakan AzureRM. Tidak ada migrasi ke kumpulan perintah baru yang memungkinkan, tetapi artikel ini akan membantu Anda memulai transisi ke modul baru.

Untuk melihat daftar lengkap perubahan terbaru antara AzureRM dan Az, lihat perubahan [lengkap dari AzureRM ke Az.](migrate-az-1.0.0.md)

## <a name="ensure-existing-scripts-work-with-the-latest-azurerm-release"></a>Memastikan bahwa skrip yang sudah ada berfungsi dengan rilis AzureRM terbaru

Sebelum melakukan langkah-langkah migrasi, periksa versi AzureRM yang diinstal di sistem Anda. Dengan demikian, Anda dapat memastikan bahwa skrip sudah berjalan pada rilis terbaru dan memberi tahu anda versi AzureRM mana yang harus dihapus instalannya.

Untuk memeriksa versi AzureRM yang telah diinstal, jalankan perintah:

```powershell-interactive
Get-InstalledModule -Name AzureRM -AllVersions
```

Rilis __terbaru__ AzureRM yang tersedia adalah __6.13.1__. Jika Anda belum menginstal versi ini, skrip yang sudah ada mungkin memerlukan modifikasi tambahan untuk bekerja dengan modul Az yang melebihi apa yang dijelaskan di sini dan dalam [daftar perubahan terbaru.](migrate-az-1.0.0.md)

Jika skrip Anda tidak berfungsi dengan AzureRM 6.13.1, perbarui sesuai dengan panduan migrasi [AzureRM 5.x hingga 6.x.](/powershell/azure/azurerm/migration-guide.6.0.0)
Jika Anda menggunakan versi modul AzureRM yang lebih lama, ada panduan migrasi yang tersedia untuk setiap versi utama.

## <a name="uninstall-azurerm"></a>Menghapus instalan AzureRM

Modul Az tidak dijamin kompatibel dengan instalan AzureRM yang sudah ada di PowerShell 5.1 untuk Windows. Sebelum Anda menginstal modul Az, hapus [instalan AzureRM](/powershell/azure/uninstall-az-ps#uninstall-the-azurerm-module).

> [!IMPORTANT]
>
> Jika belum siap menghapus modul AzureRM dari sistem, Anda bisa menginstal modul Az untuk [PowerShell Core](/powershell/scripting/install/installing-powershell-core-on-windows) 6.x atau yang lebih baru sebagai gantinya. PowerShell Core dan PowerShell 5.1 Windows menggunakan pustaka modul yang berbeda, jadi tidak akan ada konflik. Anda masih bisa [mengaktifkan alias di](#enable-azurerm-compatibility-aliases) PowerShell Core.

## <a name="install-the-azure-powershell-az-module"></a>Menginstal modul Azure PowerShell Az

Langkah pertama adalah menginstal modul Az di platform Anda. Ketika menginstal Az, sebaiknya hapus instalan AzureRM. Dalam langkah berikut ini, Anda akan mempelajari cara terus menjalankan skrip yang sudah ada dan mengaktifkan kompatibilitas untuk nama cmdlet lama.

Untuk menginstal Azure PowerShell Az Anda, ikuti instruksi [di Menginstal modul Az](install-az-ps.md).

> [!NOTE]
> Di titik ini, Anda mungkin ingin menjalankan cmdlet [Uninstall-AzureRM](/powershell/module/az.accounts/uninstall-azurerm) yang disediakan di modul Az, hanya untuk memastikan bahwa semua versi AzureRM telah dihapus instalasinya dan tidak akan menyebabkan konflik.

## <a name="enable-azurerm-compatibility-aliases"></a>Mengaktifkan alias kompatibilitas AzureRM

Dengan menghapus instalan AzureRM dan skrip Anda bekerja dengan versi AzureRM terbaru, langkah berikutnya adalah mengaktifkan mode kompatibilitas untuk modul Az. Kompatibilitas diaktifkan dengan perintah:

```powershell-interactive
Enable-AzureRmAlias -Scope CurrentUser
```

Alias memungkinkan kemampuan untuk menggunakan nama cmdlet lama dengan modul Az yang terinstal. Alias ini ditulis ke profil untuk lingkup yang dipilih. Jika tidak ada profil, profil akan dibuat.
Ketika menggunakan lebih `-Scope` dari , izin yang sesuai diperlukan untuk membuat atau memperbarui file profil `CurrentUser` terkait.

> [!IMPORTANT]
> __Hanya__ nama cmdlet yang menggunakan alias, nama modul tidak! Jika Anda menggunakan , , daftar dependensi dalam nama cmdlet , atau yang sepenuhnya memenuhi syarat, pastikan bahwa Anda melakukan migrasi pada titik ini dengan mengikuti proses yang diuraikan dalam daftar perubahan yang memecahkan terkait `#Requires` `Import-Module` nama `.psd1` modul. [](migrate-az-1.0.0.md)

> [!WARNING]
>
> Anda dapat menggunakan cara `-Scope` lain untuk perintah ini, tetapi tidak disarankan. Alias akan ditulis ke profil pengguna untuk lingkup yang dipilih, jadi tetap aktifkan mereka dengan lingkup terbatas sesegera mungkin. Mengaktifkan alias seluruh sistem dapat menyebabkan masalah bagi pengguna lain yang menginstal AzureRM dalam lingkup lokal mereka.

Setelah mode alias diaktifkan, jalankan kembali skrip untuk mengonfirmasi bahwa skrip masih berfungsi seperti yang diharapkan.
Beberapa nama parameter telah diubah, ditambahkan, atau dibuat diperlukan oleh modul Az. Tipe output cmdlet mungkin juga telah berubah. Perubahan ini dijelaskan secara mendetail dalam [daftar perubahan yang sedang berganti.](migrate-az-1.0.0.md)

## <a name="update-cmdlets-modules-and-parameters"></a>Memperbarui cmdlet, modul, dan parameter

Dengan skrip yang diperbarui dan berjalan di bawah alias, Anda dapat menghabiskan waktu untuk memperbaruinya menggunakan cmdlet baru dan memanfaatkan perubahan lain seperti fitur baru. Untuk sebagian besar skrip, Anda hanya perlu memperbarui nama cmdlet, [mengikuti skema penamaan cmdlet baru di Az](migrate-az-1.0.0.md#cmdlet-noun-prefix-changes). There may also be some other changes that you need to make in order to have your scripts work, depending on what they do and which Azure PowerShell features they take advantage of.

Misalnya, [cmdlet Storage Blob](migrate-az-1.0.0.md#azstorage-previously-azurestorage-and-azurermstorage) telah benar-benar dibuat ulang untuk menggunakan model asinkron baru, jadi skrip yang menggunakannya akan membutuhkan lebih banyak pekerjaan untuk diperbarui daripada perubahan yang satu-satunya perubahan yang relevan adalah nama cmdlet.

Bahkan jika Anda hanya perlu membuat perubahan kecil dan sederhana pada skrip hingga saat ini - atau bahkan bekerja tanpa modifikasi tambahan saat alias diaktifkan - baca daftar lengkap perubahan pecah di [Az 1.0.0](migrate-az-1.0.0.md) untuk memastikan bahwa Anda tidak mengandalkan perilaku alias 'transparan' yang bisa menghilang setelah Anda mengubah nama cmdlet dan menonaktifkan alias.

## <a name="disable-aliases"></a>Menonaktifkan alias

Setelah Anda menyelesaikan migrasi dan tidak lagi mengandalkan aliasing perilaku, anda disarankan untuk menonaktifkan alias. Hal ini dilakukan dengan cmdlet [Disable-AzureRmAlias.](/powershell/module/az.accounts/disable-azurermalias)

> [!IMPORTANT]
> Saat menjalankan cmdlet __ini, pastikan__ bahwa Anda menjalankannya untuk setiap yang diminta untuk, jika tidak mungkin masih ada skrip pada sistem Anda yang mengandalkan `-Scope` perilaku `Enable-AzureRmAlias` alias.
