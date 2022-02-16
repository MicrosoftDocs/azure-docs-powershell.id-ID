---
description: Pelajari langkah dan alat untuk memigrasikan skrip Azure PowerShell dari AzureRM ke modul Az PowerShell baru.
ms.custom: devx-track-azurepowershell, contperf-fy21q2
ms.date: 02/08/2022
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
title: Memigrasikan skrip Azure PowerShell dari AzureRM ke Az
ms.openlocfilehash: 5dc0b9568532e45fc4900f5eeadf77fe308ed89e
ms.sourcegitcommit: cdca0d3199eb118c98aafb63ffcacc3dd080f0d4
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/16/2022
ms.locfileid: "138855837"
---
# <a name="migrate-azure-powershell-from-azurerm-to-az"></a>Migrasikan Azure PowerShell dari AzureRM ke Az

Semua versi modul AzureRM PowerShell telah usang. Modul [Az PowerShell](install-az-ps.md) sekarang menjadi modul PowerShell yang direkomendasikan untuk berinteraksi dengan Azure.

## <a name="why-a-new-module"></a>Mengapa modul baru?

Perubahan terbesar dan paling penting adalah bahwa [PowerShell](/powershell/scripting/overview), yang didasarkan pada perpustakaan .NET Standard, telah menjadi produk lintas platform sejak diperkenalkan.

Seperti bahasa PowerShell, kami berkomitmen untuk menghadirkan dukungan Azure ke semua platform. Komitmen kami berarti bahwa modul Azure PowerShell perlu diperbarui untuk menggunakan .NET Standard dan kompatibel dengan PowerShell Core. Alih-alih memodifikasi modul AzureRM yang ada dan memperkenalkan perubahan kompleks untuk menambahkan dukungan ini, modul Az dibuat.

Membuat modul baru juga memungkinkan insinyur kami untuk membuat desain, penamaan cmdlet, dan modul yang konsisten. Semua modul sekarang dimulai dengan `Az.` awalan dan cmdlet semua menggunakan `Verb-AzNoun` konvensi penamaan. Sebelumnya, nama cmdlet lebih panjang dan tidak konsisten.

Jumlah modul juga berkurang: Beberapa modul yang bekerja dengan layanan yang sama telah digabungkan. Pesawat manajemen dan cmdlet bidang data untuk layanan yang sama sekarang terkandung dalam satu modul. Bagi Anda yang mengelola dependensi dan impor secara manual, konsolidasi ini membuat segalanya jauh lebih sederhana.

Dengan membuat perubahan penting ini, tim telah berkomitmen untuk membuatnya lebih mudah dari sebelumnya dan pada lebih banyak platform daripada yang sebelumnya mungkin untuk menggunakan Azure dengan cmdlet PowerShell.

## <a name="upgrading-to-az-powershell"></a>Upgrade ke Az PowerShell

Skrip yang ditulis untuk cmdlet AzureRM tidak akan secara otomatis berfungsi dengan Az. Untuk mempermudah transisi, [toolkit migrasi AzureRM ke Az](https://github.com/Azure/azure-powershell-migration) dikembangkan. Tidak ada migrasi ke set perintah baru yang akan nyaman, tetapi artikel ini akan membantu Anda memulai transisi ke modul Az PowerShell. Untuk mempelajari selengkapnya tentang mengapa modul Az PowerShell dibuat, lihat [Memperkenalkan modul Azure PowerShell Az baru](new-azureps-module-az.md).

Nama-nama cmdlet baru telah dirancang agar mudah dipelajari. Alih-alih menggunakan `AzureRm` atau `Azure` dalam nama cmdlet, gunakan `Az`. Misalnya, cmdlet `New-AzureRMVm` lama telah menjadi `New-AzVm`.
Namun, migrasi lebih dari sekadar menjadi akrab dengan nama cmdlet baru. Ada modul, parameter, dan perubahan penting lainnya yang berganti nama.

Untuk melihat daftar lengkap perubahan yang melanggar antara AzureRM dan Az, lihat [perubahan lengkap dari AzureRM ke Az](migrate-az-1.0.0.md).

## <a name="ensure-existing-scripts-work-with-the-latest-azurerm-release"></a>Pastikan skrip yang ada berfungsi dengan rilis AzureRM terbaru

Sebelum mengambil langkah migrasi apa pun, periksa versi AzureRM mana yang diinstal pada sistem Anda.
Melakukan hal itu memungkinkan Anda untuk memastikan skrip sudah berjalan pada rilis terbaru dan memberi tahu Anda versi AzureRM mana yang harus dihapus.

Untuk memeriksa versi AzureRM mana yang telah Anda instal, jalankan contoh berikut:

```azurepowershell
Get-Module -Name AzureRM -ListAvailable -All
```

Rilis **terbaru** yang tersedia dari AzureRM adalah **6.13.1**. Jika Anda tidak menginstal versi ini, skrip yang ada mungkin memerlukan modifikasi tambahan untuk bekerja dengan modul Az di luar cakupan apa yang dijelaskan dalam artikel ini dan dalam [daftar perubahan yang melanggar](migrate-az-1.0.0.md).

Jika skrip Anda tidak berfungsi dengan AzureRM 6.13.1, perbarui sesuai [dengan panduan migrasi AzureRM 5.x ke 6.x](/powershell/azure/azurerm/migration-guide.6.0.0). Jika Anda menggunakan versi modul AzureRM yang lebih lama, ada panduan migrasi yang tersedia untuk setiap versi utama.

## <a name="option-1-recommended-automatically-migrate-your-powershell-scripts"></a>Opsi 1 (disarankan): Migrasi skrip PowerShell Anda secara otomatis

Opsi yang direkomendasikan ini meminimalkan upaya yang diperlukan untuk memigrasikan skrip AzureRM ke Az.

### <a name="install-the-azurerm-to-az-migration-toolkit"></a>Menginstal toolkit migrasi AzureRM ke Az

```azurepowershell
Install-Module -Name Az.Tools.Migration
```

### <a name="convert-your-scripts-automatically"></a>Mengonversi skrip Anda secara otomatis

Dengan toolkit migrasi AzureRM ke Az, Anda dapat membuat rencana untuk menentukan perubahan apa yang akan dilakukan pada skrip Anda sebelum melakukan modifikasi apa pun padanya dan sebelum menginstal modul Az PowerShell.

[Skrip PowerShell yang secara otomatis bermigrasi dari AzureRM ke modul Az PowerShell](quickstart-migrate-azurerm-to-az-automatically.md) yang mulai cepat memandu Anda melalui seluruh proses memperbarui skrip PowerShell Anda secara otomatis dari AzureRM ke modul Az PowerShell.

## <a name="option-2-use-compatibility-mode-with-enable-azurermalias"></a>Opsi 2: Gunakan mode kompatibilitas dengan Enable-AzureRmAlias

Modul Az memiliki mode kompatibilitas untuk membantu Anda menggunakan skrip yang ada saat Anda memperbarui ke sintaks baru. Cmdlet [Enable-AzureRmAlias](/powershell/module/az.accounts/enable-azurermalias) memungkinkan mode kompatibilitas melalui alias. Mode ini memungkinkan Anda untuk menggunakan skrip yang ada dengan modifikasi minimal saat bekerja menuju migrasi penuh ke Az. Secara default, `Enable-AzureRmAlias` hanya mengaktifkan alias kompatibilitas untuk sesi PowerShell saat ini. Gunakan parameternya `Scope` untuk mempertahankan alias kompatibilitas di seluruh sesi PowerShell. Untuk informasi [selengkapnya, lihat dokumentasi referensi Enable-AzureRmAlias](/powershell/module/az.accounts/enable-azurermalias).

> [!IMPORTANT]
> Meskipun nama cmdlet alias, mungkin masih ada parameter baru (atau berganti nama) atau mengubah nilai pengembalian untuk cmdlet Az. Jangan berharap memungkinkan alias untuk mengurus migrasi untuk Anda! Lihat [daftar perubahan pemecahan penuh](migrate-az-1.0.0.md) untuk menemukan di mana skrip Anda mungkin memerlukan pembaruan.

## <a name="option-3-migrate-your-scripts-in-visual-studio-code-with-the-azure-powershell-extension"></a>Opsi 3: Memigrasikan skrip Anda dalam Visual Studio Code dengan ekstensi Azure PowerShell

### <a name="install-the-azure-powershell-extension-for-visual-studio-code"></a>Instal ekstensi Azure PowerShell untuk Visual Studio Code

Instal [ekstensi Azure PowerShell untuk VSCode](https://marketplace.visualstudio.com/items?itemName=azps-tools.azps-tools)

### <a name="convert-your-scripts-manually"></a>Mengonversi skrip Anda secara manual

1. Memuat skrip AzureRM Anda di VSCode
2. Mulai migrasi dengan membuka palet `Ctrl+Shift+P` perintah dan pilih `Migrate Azure PowerShell script`
3. Pilih versi sumber `AzureRM`
4. Ikuti tindakan yang disarankan untuk setiap perintah atau parameter yang digarisbawahi.

## <a name="next-steps"></a>Langkah berikutnya

* [Uninstall AzureRM](uninstall-az-ps.md#uninstall-the-azurerm-module)
* [Instal Azure PowerShell](install-az-ps.md).
