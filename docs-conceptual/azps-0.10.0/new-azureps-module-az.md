---
title: Memperkenalkan modul Azure PowerShell Az
description: Memperkenalkan modul Azure PowerShell Az, pengganti modul AzureRM.
ms.date: 02/12/2021
ms.devlang: powershell
ms.topic: conceptual
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
ms.openlocfilehash: f6ffd66d20943541c3591d41db7c72861f44204c
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132427402"
---
# <a name="introducing-the-new-azure-powershell-az-module"></a>Memperkenalkan modul az Azure PowerShell baru

Mulai Desember 2018, Azure PowerShell Az sedang dirilis secara umum dan kini merupakan modul PowerShell yang dituju untuk berinteraksi dengan Azure. Az menawarkan perintah yang lebih singkat, stabilitas yang ditingkatkan, dan dukungan lintas platform. Az juga memiliki fitur paritas dengan AzureRM, yang memberi Anda jalur migrasi yang mudah.

Dengan modul Az, Azure PowerShell kini kompatibel dengan PowerShell 5.1 di Windows dan PowerShell Core 6.x dan yang lebih baru di semua platform yang didukung - termasuk Windows, macOS, dan Linux.

Az adalah modul baru, jadi versinya telah diatur ulang ke 1.0.0.

## <a name="why-a-new-module"></a>Mengapa modul baru?

Pembaruan utama bisa merepotkan, jadi penting bagi Anda untuk mengetahui mengapa keputusan ini dibuat untuk memperkenalkan kumpulan modul baru, dengan cmdlet baru, untuk berinteraksi dengan Azure dari PowerShell.

Perubahan terbesar dan terpenting adalah PowerShell telah menjadi produk lintas platform sejak pengenalan [PowerShell,](/powershell/scripting/overview)berdasarkan pustaka .NET Standard.
Kami berkomitmen untuk menghadirkan dukungan Azure ke semua platform, yang berarti modul Azure PowerShell diperlukan untuk menggunakan .NET Standard dan kompatibel dengan PowerShell Core. Modul AzureRM yang sudah ada tidak perlu dibuat dan memperkenalkan perubahan kompleks untuk menambahkan dukungan ini, modul Az dibuat.

Membuat modul baru juga memberi kesempatan kepada teknisi kami untuk membuat desain dan penamaan cmdlet dan modul konsisten. Semua modul kini dimulai dengan `Az.` prefiks dan cmdlet semuanya menggunakan bentuk - `Az` _Kata Benda Kata_ Kerja. Sebelumnya, nama cmdlet tidak lagi lebih panjang, terdapat inkonsistensi dalam nama cmdlet.

Jumlah modul juga dikurangi: Beberapa modul yang bekerja dengan layanan yang sama telah diluncurkan bersama, dan cmdlet bidang manajemen dan bidang data kini telah dimuat semua dalam modul tunggal untuk layanan mereka. Bagi Anda yang mengelola dependensi dan impor secara manual, hal ini membuat segala hal menjadi jauh lebih sederhana.

Dengan melakukan perubahan penting yang diperlukan dalam membangun modul Azure PowerShell baru, tim telah berkomitmen untuk memudahkannya, dan di lebih banyak platform daripada yang sebelumnya memungkinkan, untuk menggunakan Azure dengan cmdlet PowerShell.

## <a name="upgrade-to-az"></a>Mutakhirkan ke Az

Untuk terus mengikuti fitur terbaru Azure di PowerShell, Anda harus melakukan migrasi ke modul Az sesegera mungkin. Jika Anda belum siap untuk menginstal modul Az sebagai pengganti AzureRM, Anda memiliki beberapa opsi yang tersedia untuk bereksperimen dengan Az:

* Menggunakan lingkungan `PowerShell` dengan Azure Cloud [Shell](/azure/cloud-shell/overview). Azure Cloud Shell adalah lingkungan shell berbasis browser yang dilengkapi dengan alias kompatibilitas dan instalan modul Az `Enable-AzureRM` yang diaktifkan.
* Tetap instal modul AzureRM dengan PowerShell 5.1 untuk Windows, tetapi instal modul Az untuk PowerShell Core 6.x atau yang lebih baru. PowerShell 5.1 Windows dan PowerShell Core menggunakan kumpulan modul terpisah. Ikuti instruksi untuk [menginstal PowerShell Core](/powershell/scripting/install/installing-powershell-core-on-windows) lalu [instal modul Az](install-az-ps.md) dari terminal PowerShell Core.

Untuk memutakhirkan dari instalan AzureRM yang sudah ada:

1. [Menghapus instalan Azure PowerShell modul AzureRM](/powershell/azure/uninstall-az-ps#uninstall-the-azurerm-module)
2. [Instal modul Azure PowerShell Az](install-az-ps.md)
3. **OPSIONAL**: Mengaktifkan mode kompatibilitas untuk menambahkan alias untuk cmdlet AzureRM dengan [Enable-AzureRMAlias](/powershell/module/az.accounts/enable-azurermalias) ketika Anda terbiasa dengan kumpulan perintah baru. Lihat bagian berikutnya atau [Memulai migrasi dari AzureRM ke Az](migrate-from-azurerm-to-az.md) untuk detail selengkapnya.

## <a name="migrate-existing-scripts-to-az"></a>Melakukan migrasi skrip yang sudah ada ke Az

Nama cmdlet baru telah dirancang agar mudah untuk dipelajari. Daripada menggunakan `AzureRm` atau dalam nama `Azure` cmdlet, gunakan `Az` . Misalnya, perintah lama `New-AzureRMVm` telah menjadi `New-AzVm` .
Migrasi tidak hanya memahami nama cmdlet yang baru, tetapi juga: Terdapat modul, parameter, dan perubahan penting lain yang telah diubah namanya.

Untuk membantu Anda dalam proses migrasi dari AzureRM ke Az, kami memiliki sejumlah sumber daya:

* [Mulai migrasi dari AzureRM ke Az](migrate-from-azurerm-to-az.md)
* [Daftar lengkap memutus perubahan dari AzureRM ke Az 1.0.0](migrate-az-1.0.0.md)
* Cmdlet [Enable-AzureRmAlias](/powershell/module/az.accounts/enable-azurermalias)

Modul Az memiliki mode kompatibilitas untuk membantu Anda menggunakan skrip yang sudah ada saat anda memperbarui ke sintaks yang baru. Cmdlet [Enable-AzureRmAlias](/powershell/module/az.accounts/enable-azurermalias) mengaktifkan mode kompatibilitas melalui alias, agar Anda dapat menggunakan skrip yang sudah ada dengan modifikasi minimal saat bekerja menuju migrasi penuh ke Az.

> [!IMPORTANT]
> Meskipun nama cmdlet alias, mungkin masih ada parameter baru (atau yang diganti namanya) atau mengubah nilai pengembalian untuk cmdlet Az. Jangan berharap mengaktifkan alias untuk menangani migrasi untuk Anda! Lihat daftar [perubahan terkini untuk menemukan](migrate-az-1.0.0.md) tempat skrip Anda mungkin memerlukan pembaruan.

## <a name="support-for-azurerm"></a>Dukungan untuk AzureRM

Karena modul PowerShell Az kini memiliki semua kapabilitas modul PowerShell AzureRM dan lainnya, kami akan menghentikan modul PowerShell AzureRM pada 29 Februari 2024.

Untuk menghindari gangguan [layanan,](https://aka.ms/azpsmigrate) perbarui skrip Anda yang menggunakan modul PowerShell AzureRM untuk menggunakan modul Az PowerShell sebelum 29 Februari 2024. Untuk memperbarui skrip secara otomatis, ikuti [panduan mulai cepat](/powershell/azure/quickstart-migrate-azurerm-to-az-automatically).
