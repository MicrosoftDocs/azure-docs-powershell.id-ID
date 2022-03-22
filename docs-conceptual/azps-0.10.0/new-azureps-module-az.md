---
title: Memperkenalkan modul Azure PowerShell Az
description: Memperkenalkan modul Azure PowerShell baru Az, pengganti modul AzureRM.
ms.date: 02/12/2021
ms.devlang: powershell
ms.topic: conceptual
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
ms.openlocfilehash: f6ffd66d20943541c3591d41db7c72861f44204c
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132427402"
---
# <a name="introducing-the-new-azure-powershell-az-module"></a>Memperkenalkan modul Azure PowerShell Az

Mulai Desember 2018, modul Azure PowerShell Az dirilis secara umum dan sekarang menjadi modul PowerShell yang ditujukan untuk berinteraksi dengan Azure. Az menawarkan perintah yang lebih singkat, stabilitas yang lebih baik, dan dukungan lintas platform. Az juga memiliki paritas fitur dengan AzureRM sehingga memberikan jalur migrasi yang mudah.

Dengan modul Az, Azure PowerShell sekarang kompatibel dengan PowerShell 5.1 di Windows dan PowerShell Core 6.x dan yang lebih baru di semua platform yang didukung, termasuk Windows, macOS, dan Linux.

Az adalah modul baru, jadi versinya telah diatur ulang ke 1.0.0.

## <a name="why-a-new-module"></a>Mengapa ada modul baru?

Pembaruan besar bisa merepotkan, jadi penting bagi kami untuk memberi tahu Anda mengapa dibuat keputusan untuk memperkenalkan satu set modul baru, dengan cmdlet baru, untuk berinteraksi dengan Azure dari PowerShell.

Perubahan terbesar dan paling penting adalah bahwa [PowerShell](/powershell/scripting/overview), yang didasarkan pada pustaka .NET Standard, telah menjadi produk lintas platform sejak diperkenalkan.
Kami berkomitmen untuk membawa dukungan Azure ke semua platform, yang berarti bahwa modul Azure PowerShell perlu diperbarui untuk menggunakan .NET Standard dan kompatibel dengan PowerShell Core. Alih-alih memodifikasi modul AzureRM yang ada dan memperkenalkan perubahan kompleks untuk menambahkan dukungan ini, modul Az dibuat.

Dengan membuat modul baru, insinyur kami juga memiliki kesempatan untuk membuat desain dan penamaan cmdlet dan modul yang konsisten. Semua modul sekarang dimulai dengan awalan `Az.` dan semua cmdlet menggunakan bentuk _Kata Kerja_-`Az`_Kata Benda_. Sebelumnya,tidak hanya lebih panjang, nama cmdlet juga mengalami inkonsistensi.

Jumlah modul juga berkurang: Beberapa modul yang bekerja dengan layanan yang sama telah dirilis bersama, serta semua cmdlet bidang manajemen dan bidang data sekarang dimuat dalam modul tunggal untuk layanannya. Bagi Anda yang mengelola dependensi dan impor secara manual, hal ini membuat segalanya jauh lebih sederhana.

Dengan perubahan penting yang memerlukan pembuatan modul Azure PowerShell baru ini, tim kami telah berkomitmen untuk menjadikan penggunaan Azure dengan cmdlet PowerShell jauh lebih mudah dan didukung di lebih banyak platform dari sebelumnya.

## <a name="upgrade-to-az"></a>Upgrade ke Az

Untuk menggunakan fitur Azure terbaru di PowerShell, Anda harus bermigrasi ke modul Az sesegera mungkin. Jika Anda belum siap untuk menginstal modul Az sebagai pengganti AzureRM, ada beberapa opsi yang tersedia untuk bereksperimen dengan Az:

* Gunakan lingkungan `PowerShell` dengan [Azure Cloud Shell](/azure/cloud-shell/overview). Azure Cloud Shell adalah lingkungan shell berbasis browser yang sudah diinstal dengan modul Az dan kompatibilitas alias `Enable-AzureRM` aktif.
* Tetap instal modul AzureRM dengan PowerShell 5.1 untuk Windows, tetapi instal modul Az untuk PowerShell Core 6.x atau yang lebih baru. PowerShell 5.1 untuk Windows dan PowerShell Core menggunakan koleksi modul terpisah. Ikuti petunjuk untuk [menginstal PowerShell Core](/powershell/scripting/install/installing-powershell-core-on-windows), lalu [instal modul Az](install-az-ps.md) dari terminal PowerShell Core.

Untuk meningkatkan dari penginstalan AzureRM yang ada:

1. [Menghapus instalan modul AzureRM Azure PowerShell](/powershell/azure/uninstall-az-ps#uninstall-the-azurerm-module)
2. [Menginstal modul Az Azure PowerShell](install-az-ps.md)
3. **OPSIONAL**: Aktifkan mode kompatibilitas untuk menambahkan alias cmdlet AzureRM dengan [Enable-AzureRMAlias](/powershell/module/az.accounts/enable-azurermalias) selagi Anda membiasakan diri dengan set perintah baru. Untuk informasi selengkapnya, lihat bagian berikutnya atau [Memulai migrasi dari AzureRM ke Az](migrate-from-azurerm-to-az.md).

## <a name="migrate-existing-scripts-to-az"></a>Memigrasikan skrip yang ada ke Az

Nama cmdlet baru telah dirancang agar mudah dipelajari. Alih-alih menggunakan `AzureRm` atau `Azure` dalam nama cmdlet, gunakan `Az`. Misalnya, perintah lama `New-AzureRMVm` telah menjadi `New-AzVm`.
Migrasi lebih dari sekadar membiasakan diri dengan nama cmdlet baru. Ada modul, parameter, dan perubahan penting lainnya yang diganti namanya.

Untuk membantu Anda dalam proses migrasi dari AzureRM ke Az, kami memiliki sejumlah sumber daya:

* [Memulai migrasi dari AzureRM ke Az](migrate-from-azurerm-to-az.md)
* [Daftar lengkap perubahan berisiko dari AzureRM ke Az 1.0.0](migrate-az-1.0.0.md)
* Cmdlet [Enable-AzureRmAlias](/powershell/module/az.accounts/enable-azurermalias)

Modul Az memiliki mode kompatibilitas untuk membantu Anda menggunakan skrip yang ada saat memperbarui ke sintaksis baru. Cmdlet [Enable-AzureRmAlias](/powershell/module/az.accounts/enable-azurermalias) memungkinkan mode kompatibilitas melalui alias agar Anda dapat menggunakan skrip yang ada dengan modifikasi minimal saat melakukan migrasi penuh ke Az.

> [!IMPORTANT]
> Meskipun nama cmdlet merupakan alias, mungkin masih ada parameter baru (atau berganti nama) atau nilai pengembalian yang diubah untuk cmdlet Az. Proses migrasi tidak dapat berjalan otomatis hanya karena alias diaktifkan. Lihat [daftar lengkap perubahan yang berisiko](migrate-az-1.0.0.md) untuk menemukan bagian skrip yang memerlukan pembaruan.

## <a name="support-for-azurerm"></a>Dukungan untuk AzureRM

Karena modul Az PowerShell sekarang memiliki semua kemampuan modul AzureRM PowerShell dan lebih banyak lagi, kami akan menghentikan modul AzureRM PowerShell pada 29 Februari 2024.

Untuk menghindari gangguan layanan, [perbarui skrip Anda](https://aka.ms/azpsmigrate) yang menggunakan modul AzureRM PowerShell untuk menggunakan modul Az PowerShell paling lambat 29 Februari 2024. Untuk memperbarui skrip Anda secara otomatis, ikuti [panduan memulai cepat](/powershell/azure/quickstart-migrate-azurerm-to-az-automatically).
