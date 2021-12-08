---
title: Melakukan Azure PowerShell skrip dari AzureRM ke Az
description: Pelajari langkah-langkah dan alat untuk melakukan migrasi Azure PowerShell skrip dari AzureRM ke modul PowerShell Az yang baru.
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
ms.date: 12/07/2021
ms.custom: devx-track-azurepowershell, contperf-fy21q2
ms.openlocfilehash: 851e14b01881c9c908b99625b3789374327d000c
ms.sourcegitcommit: 2a404a7aac28f6568e0e17912814e4403ea5d0d9
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/08/2021
ms.locfileid: "134110703"
---
# <a name="migrate-azure-powershell-from-azurerm-to-az"></a>Melakukan Azure PowerShell dari AzureRM ke Az

Semua versi modul PowerShell AzureRM telah usang. Modul [Az PowerShell](install-az-ps.md) kini merupakan modul PowerShell yang disarankan untuk berinteraksi dengan Azure.

## <a name="why-a-new-module"></a>Mengapa modul baru?

Perubahan terbesar dan paling penting adalah bahwa [PowerShell,](/powershell/scripting/overview)yang didasarkan pada pustaka .NET Standard, telah menjadi produk lintas platform sejak pengenalannya.

Seperti bahasa PowerShell, kami berkomitmen untuk menghadirkan dukungan Azure ke semua platform. Komitmen kami berarti bahwa Azure PowerShell modul diperlukan untuk menggunakan .NET Standard dan kompatibel dengan PowerShell Core. Modul Az dibuat untuk tidak mengubah modul AzureRM yang sudah ada dan memperkenalkan perubahan kompleks untuk menambahkan dukungan ini.

Membuat modul baru juga memungkinkan teknisi kami membuat desain, penamaan cmdlet, dan modul konsisten. Semua modul kini dimulai dengan `Az.` prefiks dan cmdlet semuanya `Verb-AzNoun` menggunakan konvensi penamaan. Sebelumnya, nama cmdlet lebih panjang dan tidak konsisten.

Jumlah modul juga dikurangi: Beberapa modul yang bekerja dengan layanan yang sama telah digabungkan. Cmdlet pesawat manajemen dan pesawat data untuk layanan yang sama kini dimuat dalam satu modul. Bagi Anda yang mengelola dependensi dan impor secara manual, konsolidasi ini membuat segalanya menjadi jauh lebih sederhana.

Dengan melakukan perubahan-perubahan penting ini, tim telah berkomitmen untuk memudahkan berbagai platform daripada sebelumnya yang memungkinkan untuk menggunakan Azure dengan cmdlet PowerShell.

## <a name="upgrading-to-az-powershell"></a>Memutakhirkan ke Az PowerShell

Skrip yang ditulis untuk cmdlet AzureRM tidak akan secara otomatis berfungsi dengan Az. Untuk memudahkan transisi, toolkit [migrasi AzureRM](https://github.com/Azure/azure-powershell-migration) ke Az telah dikembangkan. Tidak ada migrasi ke kumpulan perintah baru yang memungkinkan, tetapi artikel ini akan membantu Anda memulai transisi ke modul Az PowerShell. Untuk mempelajari selengkapnya tentang mengapa modul Az PowerShell dibuat, lihat Memperkenalkan modul az Azure PowerShell az yang [baru.](new-azureps-module-az.md)

Nama cmdlet baru telah dirancang agar mudah untuk dipelajari. Daripada menggunakan `AzureRm` atau dalam nama `Azure` cmdlet, gunakan `Az` . Misalnya, cmdlet lama `New-AzureRMVm` telah menjadi `New-AzVm` .
Namun, migrasi tidak hanya mengenal nama cmdlet yang baru. Terdapat modul, parameter, dan perubahan penting lainnya yang diubah namanya.

Untuk melihat daftar lengkap perubahan terbaru antara AzureRM dan Az, lihat perubahan [lengkap dari AzureRM ke Az.](migrate-az-1.0.0.md)

## <a name="ensure-existing-scripts-work-with-the-latest-azurerm-release"></a>Memastikan bahwa skrip yang sudah ada berfungsi dengan rilis AzureRM terbaru

Sebelum melakukan langkah-langkah migrasi, periksa versi AzureRM yang diinstal di sistem Anda.
Dengan demikian, Anda dapat memastikan bahwa skrip sudah berjalan pada rilis terbaru dan memberi tahu versi AzureRM mana yang harus dihapus instalannya.

Untuk memeriksa versi AzureRM yang telah diinstal, jalankan contoh berikut:

```azurepowershell
Get-Module -Name AzureRM -ListAvailable -All
```

Rilis **terbaru** AzureRM yang tersedia adalah **6.13.1**. Jika Anda belum menginstal versi ini, skrip yang sudah ada mungkin memerlukan modifikasi tambahan untuk bekerja dengan modul Az yang melebihi lingkup apa yang dijelaskan di artikel ini dan dalam [daftar perubahan terbaru.](migrate-az-1.0.0.md)

Jika skrip Anda tidak berfungsi dengan AzureRM 6.13.1, perbarui sesuai dengan panduan migrasi [AzureRM 5.x hingga 6.x.](/powershell/azure/azurerm/migration-guide.6.0.0) Jika Anda menggunakan versi modul AzureRM yang lebih lama, ada panduan migrasi yang tersedia untuk setiap versi utama.

## <a name="option-1-recommended-automatically-migrate-your-powershell-scripts"></a>Opsi 1 (disarankan): Melakukan migrasi skrip PowerShell Anda secara otomatis

Opsi ini disarankan untuk meminimalkan upaya yang diperlukan untuk melakukan migrasi skrip AzureRM ke Az.

### <a name="install-the-azurerm-to-az-migration-toolkit"></a>Instal toolkit migrasi AzureRM ke Az

```azurepowershell
Install-Module -Name Az.Tools.Migration
```

### <a name="convert-your-scripts-automatically"></a>Mengonversi skrip secara otomatis

Dengan toolkit migrasi AzureRM ke Az, Anda dapat membuat rencana untuk menentukan perubahan apa yang akan dijalankan pada skrip sebelum membuat modifikasi pada skrip dan sebelum menginstal modul Az PowerShell.

Mulai [cepat migrasi skrip PowerShell](quickstart-migrate-azurerm-to-az-automatically.md) secara otomatis dari AzureRM ke modul Az PowerShell akan memandu Anda sepanjang proses pembaruan skrip PowerShell secara otomatis dari AzureRM ke modul Az PowerShell.

## <a name="option-2-use-compatibility-mode-with-enable-azurermalias"></a>Opsi 2: Gunakan mode kompatibilitas dengan Enable-AzureRmAlias

Modul Az memiliki mode kompatibilitas untuk membantu Anda menggunakan skrip yang sudah ada saat memperbarui ke sintaks yang baru. Cmdlet [Enable-AzureRmAlias](/powershell/module/az.accounts/enable-azurermalias) mengaktifkan mode kompatibilitas melalui alias. Mode ini memungkinkan Anda menggunakan skrip yang sudah ada dengan modifikasi minimal saat bekerja menuju migrasi penuh ke Az. Secara default, `Enable-AzureRmAlias` hanya mengaktifkan alias kompatibilitas untuk sesi PowerShell saat ini. Gunakan `Scope` parameternya untuk tetap berada di alias kompatibilitas di seluruh sesi PowerShell. Untuk informasi selengkapnya, [lihat Enable-AzureRmAlias referensi referensi .](/powershell/module/az.accounts/enable-azurermalias)

> [!IMPORTANT]
> Meskipun nama cmdlet alias, mungkin masih ada parameter baru (atau yang diganti namanya) atau mengubah nilai pengembalian untuk cmdlet Az. Jangan berharap mengaktifkan alias untuk menangani migrasi untuk Anda! Lihat daftar [perubahan terkini untuk menemukan](migrate-az-1.0.0.md) tempat skrip Anda mungkin memerlukan pembaruan.

## <a name="option-3-migrate-your-scripts-in-visual-studio-code-with-the-azure-powershell-extension"></a>Opsi 3: Melakukan migrasi skrip Visual Studio Code dengan ekstensi Azure PowerShell

### <a name="install-the-azure-powershell-extension-for-visual-studio-code"></a>Menginstal Azure PowerShell ekstensi untuk Visual Studio Code

Menginstal ekstensi [Azure PowerShell untuk VSCode](https://marketplace.visualstudio.com/items?itemName=azps-tools.azps-tools)

### <a name="convert-your-scripts-manually"></a>Mengonversi skrip secara manual

1. Memuat skrip AzureRM Anda di VSCode
2. Mulai migrasi dengan membuka palet `Ctrl+Shift+P` perintah, lalu pilih `Migrate Azure PowerShell script`
3. Pilih versi sumber `AzureRM`
4. Ikuti tindakan yang disarankan untuk setiap perintah atau parameter yang digarisbawahi.

## <a name="next-steps"></a>Langkah berikutnya

* [Menghapus instalan AzureRM](uninstall-az-ps.md#uninstall-the-azurerm-module)
* [Menginstal Azure PowerShell](install-az-ps.md)
