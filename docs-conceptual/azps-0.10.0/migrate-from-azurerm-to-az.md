---
title: Memigrasikan skrip Azure PowerShell dari AzureRM ke Az
description: Pelajari langkah dan alat untuk memigrasikan skrip dari modul AzureRM ke modul Az baru.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 05/10/2019
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
ms.openlocfilehash: a0a6fcbc0a7bdae507ff5e16dd844e8425c929d5
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132421100"
---
# <a name="migrate-azure-powershell-from-azurerm-to-az"></a>Memigrasikan Azure PowerShell dari AzureRM ke Az

Modul Az memiliki persamaan fitur dengan AzureRM, tetapi menggunakan nama cmdlet yang lebih pendek dan lebih konsisten.
Skrip yang ditulis untuk cmdlet AzureRM tidak akan secara otomatis berfungsi dengan modul baru. Untuk mempermudah transisi, Az menawarkan alat untuk memungkinkan Anda menjalankan skrip yang ada menggunakan AzureRM. Tidak ada migrasi ke set perintah baru selalu mudah, tetapi artikel ini akan membantu Anda memulai transisi ke modul baru.

Untuk melihat daftar lengkap perubahan yang dapat menyebabkan gangguan antara AzureRM dan Az, lihat [perubahan lengkap dari AzureRM ke Az](migrate-az-1.0.0.md).

## <a name="ensure-existing-scripts-work-with-the-latest-azurerm-release"></a>Memastikan skrip yang ada berfungsi dengan rilis AzureRM terbaru

Sebelum melakukan langkah migrasi, periksa versi AzureRM mana yang terinstal pada sistem Anda. Melakukan hal itu memungkinkan Anda memastikan skrip sudah berjalan pada rilis terbaru, dan mengetahui jika Anda dapat mengaktifkan alias perintah tanpa menghapus penginstalan AzureRM.

Untuk memeriksa versi AzureRM mana yang telah Anda terinstal, jalankan perintah:

```powershell-interactive
Get-InstalledModule -Name AzureRM -AllVersions
```

Rilis AzureRM __terbaru__ yang tersedia adalah __6.13.1__. Jika Anda tidak menginstal versi ini, skrip yang ada mungkin memerlukan modifikasi tambahan untuk bekerja dengan modul Az di luar apa yang dijelaskan di sini dan dalam [daftar perubahan yang melanggar](migrate-az-1.0.0.md).

Jika skrip Anda tidak berfungsi dengan AzureRM 6.13.1, perbarui sesuai dengan [panduan migrasi AzureRM 5.x hingga 6.x](/powershell/azure/azurerm/migration-guide.6.0.0).
Jika Anda menggunakan versi modul AzureRM yang lebih lama, ada panduan migrasi yang tersedia untuk setiap versi utama.

## <a name="uninstall-azurerm"></a>Menghapus instalan AzureRM

Modul Az tidak dijamin kompatibel dengan penginstalan AzureRM yang ada di PowerShell 5.1 untuk Windows. Sebelum Anda menginstal modul Az, [hapus instalan AzureRM](/powershell/azure/uninstall-az-ps#uninstall-the-azurerm-module).

> [!IMPORTANT]
>
> Jika Anda belum siap untuk menghapus modul AzureRM dari sistem Anda, Anda dapat menginstal modul Az untuk [PowerShell Core](/powershell/scripting/install/installing-powershell-core-on-windows) 6.x atau yang lebih baru. PowerShell Core dan PowerShell 5.1 untuk Windows menggunakan pustaka modul yang berbeda, sehingga tidak akan ada konflik. Anda masih dapat [mengaktifkan alias](#enable-azurerm-compatibility-aliases) di PowerShell Core.

## <a name="install-the-azure-powershell-az-module"></a>Menginstal modul Az Azure PowerShell

Langkah pertama adalah menginstal modul Az di platform Anda. Saat menginstal Az, sebaiknya Anda menghapus instalan AzureRM. Pada langkah-langkah berikut, Anda akan mempelajari cara tetap menjalankan skrip yang ada dan mengaktifkan kompatibilitas untuk nama cmdlet lama.

Untuk menginstal modul Az Azure PowerShell, ikuti petunjuk di [Instal modul Az](install-az-ps.md).

> [!NOTE]
> Pada titik ini, Anda mungkin ingin menjalankan cmdlet [Uninstall-AzureRM](/powershell/module/az.accounts/uninstall-azurerm) yang disediakan dalam modul Az, hanya untuk memastikan bahwa semua versi AzureRM telah dihapus dan tidak akan menyebabkan konflik.

## <a name="enable-azurerm-compatibility-aliases"></a>Mengaktifkan alias kompatibilitas AzureRM

Dengan dihapusnya instalan AzureRM dan skrip Anda berfungsi dengan versi AzureRM terbaru, langkah selanjutnya adalah mengaktifkan mode kompatibilitas untuk modul Az. Kompatibilitas diaktifkan dengan perintah:

```powershell-interactive
Enable-AzureRmAlias -Scope CurrentUser
```

Alias memungkinkan kemampuan untuk menggunakan nama cmdlet lama dengan modul Az yang terinstal. Alias ini ditulis ke profil pengguna untuk cakupan yang dipilih. Jika tidak ada, profil pengguna akan dibuat.
Saat menggunakan `-Scope` yang lebih luas dari `CurrentUser`, izin yang sesuai diperlukan untuk membuat atau memperbarui file profil yang sesuai.

> [!IMPORTANT]
> __Hanya__ nama cmdlet yang berupa alias - nama modul tidak! Jika Anda menggunakan `#Requires`, `Import-Module`, daftar dependensi dalam `.psd1`, atau nama cmdlet yang sepenuhnya memenuhi syarat, pastikan bahwa Anda memigrasikannya pada saat ini dengan mengikuti proses yang diuraikan dalam [daftar perubahan yang melanggar](migrate-az-1.0.0.md) mengenai nama modul.

> [!WARNING]
>
> Anda dapat menggunakan `-Scope` yang berbeda untuk perintah ini, tetapi tidak disarankan. Alias ditulis ke profil pengguna untuk cakupan yang dipilih, jadi tetap aktifkan dengan cakupan paling terbatas. Mengaktifkan alias di seluruh sistem dapat menyebabkan masalah bagi pengguna lain yang menginstal AzureRM di cakupan lokal mereka.

Setelah mode alias diaktifkan, jalankan skrip Anda lagi untuk mengonfirmasi alias masih berfungsi seperti yang diharapkan.
Beberapa nama parameter telah diubah, ditambahkan, atau dibuat yang diperlukan oleh modul Az. Jenis output cmdlet mungkin telah berubah juga. Perubahan ini dirinci dalam [daftar perubahan yang melanggar](migrate-az-1.0.0.md).

## <a name="update-cmdlets-modules-and-parameters"></a>Memperbarui cmdlet, modul, dan parameter

Dengan skrip yang diperbarui dan berjalan di bawah alias, Anda dapat meluangkan waktu untuk memperbaruinya untuk menggunakan cmdlet baru dan memanfaatkan perubahan lain seperti fitur baru. Untuk sebagian besar skrip, Anda hanya perlu memperbarui nama cmdlet, [mengikuti skema penamaan cmdlet baru di Az](migrate-az-1.0.0.md#cmdlet-noun-prefix-changes). Mungkin juga ada beberapa perubahan lain yang perlu Anda buat agar skrip Anda berfungsi, tergantung pada apa yang dilakukannya dan fitur Azure PowerShell mana yang dimanfaatkan.

Misalnya, [cmdlet Blob Storage](migrate-az-1.0.0.md#azstorage-previously-azurestorage-and-azurermstorage) telah sepenuhnya dikerjakan ulang untuk menggunakan model asinkron baru, sehingga skrip yang menggunakannya akan membutuhkan lebih banyak pekerjaan untuk diperbarui daripada yang satu-satunya perubahan yang relevan adalah nama cmdlet.

Meskipun Anda hanya perlu membuat perubahan kecil dan sederhana pada skrip Anda hingga saat ini - atau bahkan berfungsi tanpa modifikasi tambahan saat alias diaktifkan - baca [daftar lengkap perubahan yang melanggar di Az 1.0.0](migrate-az-1.0.0.md) untuk memastikan bahwa Anda tidak mengandalkan perilaku alias 'transparan' yang dapat hilang setelah Anda mengubah nama cmdlet dan menonaktifkan alias.

## <a name="disable-aliases"></a>Menonaktifkan alias

Setelah Anda menyelesaikan migrasi dan tidak lagi mengandalkan perilaku alias, disarankan agar Anda menonaktifkan alias. Ini dilakukan dengan cmdlet [Disable-AzureRmAlias](/powershell/module/az.accounts/disable-azurermalias).

> [!IMPORTANT]
> Saat menjalankan cmdlet ini, __pastikan__ Anda memanggilnya untuk setiap `-Scope` yang `Enable-AzureRmAlias` dipanggil, jika tidak, mungkin masih ada skrip di sistem Anda yang mengandalkan perilaku alias.
