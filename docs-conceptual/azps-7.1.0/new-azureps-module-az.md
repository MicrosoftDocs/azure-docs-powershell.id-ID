---
title: Memperkenalkan modul Azure Az PowerShell
description: Memperkenalkan modul Az PowerShell, direkomendasikan untuk berinteraksi dengan Azure, dan penggantian modul AzureRM PowerShell.
ms.date: 01/04/2022
ms.devlang: powershell
ms.topic: conceptual
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
ms.openlocfilehash: 31a0957337129d3b9bfd6c6355f83de596dedf5f
ms.sourcegitcommit: 05aa3fb79a622267cfbf8f641e61290dba4fd92d
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/03/2022
ms.locfileid: "138000479"
---
# <a name="introducing-the-azure-az-powershell-module"></a>Memperkenalkan modul Azure Az PowerShell

## <a name="overview"></a>Gambaran Umum

Modul Az PowerShell adalah satu set cmdlet untuk mengelola sumber daya Azure langsung dari PowerShell.
PowerShell menyediakan fitur canggih untuk otomatisasi yang dapat dimanfaatkan untuk mengelola sumber daya Azure Anda, misalnya dalam konteks pipa CI / CD.

Modul Az PowerShell adalah pengganti AzureRM dan merupakan versi yang disarankan untuk digunakan untuk berinteraksi dengan Azure.

Anda dapat menggunakan modul Az PowerShell dengan salah satu metode berikut:

* [Instal modul Az PowerShell melalui PowerShellGet](install-az-ps.md) (opsi yang direkomendasikan).
* [Instal modul Az PowerShell dengan MSI](install-az-ps-msi.md).
* [Gunakan Azure Cloud Shell](/azure/cloud-shell/overview).
* [Gunakan wadah Az PowerShell Docker](azureps-in-docker.md).

## <a name="features"></a>Fitur

Modul Az PowerShell memiliki manfaat berikut:

* Keamanan dan Stabilitas
  * Enkripsi cache token
  * Pencegahan tipe serangan man-in-the-middle
  * Mendukung autentikasi dengan ADFS 2019
  * Autentikasi nama pengguna dan kata sandi di PowerShell 7
  * Dukungan untuk fitur seperti evaluasi akses berkelanjutan
* Dukungan untuk semua layanan Azure
  * Semua layanan Azure yang tersedia secara umum memiliki modul PowerShell yang didukung sesuai
  * Beberapa perbaikan bug dan peningkatan versi API sejak AzureRM
* Kapabilitas baru
  * Dukungan di Cloud Shell dan lintas platform
  * Bisa mendapatkan dan menggunakan token akses untuk mengakses sumber daya Azure
  * Cmdlet tersedia untuk operasi REST tingkat lanjut dengan sumber daya Azure

> [!NOTE]
> PowerShell 7.0.6 LTS, PowerShell 7.1.3, atau lebih tinggi adalah versi PowerShell yang direkomendasikan untuk digunakan dengan modul Azure Az PowerShell di semua platform.

Modul Az PowerShell didasarkan pada library .NET Standard dan bekerja dengan PowerShell 7 dan yang lebih baru di semua platform termasuk Windows, macOS, dan Linux. Ini juga kompatibel dengan Windows PowerShell 5,1.

Kami berkomitmen untuk membawa dukungan Azure ke semua platform dan semua modul Az PowerShell adalah lintas platform.

## <a name="upgrade-your-environment-to-az"></a>Tingkatkan lingkungan Anda ke Az

Untuk mengikuti fitur Azure terbaru di PowerShell, Anda harus bermigrasi ke modul Az. Jika Anda belum siap untuk menginstal modul Az sebagai pengganti AzureRM, Anda memiliki beberapa opsi yang tersedia untuk bereksperimen dengan Az:

* `PowerShell` Gunakan lingkungan dengan [Azure Cloud Shell](/azure/cloud-shell/overview). Azure Cloud Shell adalah lingkungan shell berbasis browser yang dilengkapi dengan modul Az yang diinstal dan `Enable-AzureRM` alias kompatibilitas diaktifkan.
* Simpan modul AzureRM yang diinstal di Windows PowerShell 5.1 dan instal modul Az di PowerShell 7 atau yang lebih baru. Windows PowerShell 5.1 dan PowerShell 7 dan yang lebih baru menggunakan koleksi modul terpisah. Ikuti petunjuk untuk menginstal [versi terbaru PowerShell](/powershell/scripting/install/installing-powershell) dan kemudian [instal modul Az](install-az-ps.md) dari PowerShell 7 atau yang lebih baru.

Untuk memutakhirkan dari instalasi AzureRM yang sudah ada:

1. [Menghapus instalasi modul AzureRM Azure PowerShell](/powershell/azure/uninstall-az-ps#uninstall-the-azurerm-module)
1. [Instal modul Azure PowerShell Az](install-az-ps.md)
1. **OPSIONAL**: Aktifkan mode kompatibilitas untuk menambahkan alias untuk cmdlet AzureRM dengan [Enable-AzureRMAlias](/powershell/module/az.accounts/enable-azurermalias) saat Anda terbiasa dengan set perintah baru. Untuk informasi selengkapnya, lihat bagian berikutnya atau [Mulai migrasi dari AzureRM ke Az](migrate-from-azurerm-to-az.md).

## <a name="migrate-existing-scripts-from-azurerm-to-az"></a>Migrasi skrip yang ada dari AzureRM ke Az

Jika skrip Anda masih didasarkan pada modul AzureRM, kami memiliki beberapa sumber daya untuk membantu Anda dengan migrasi:

* [Mulai dengan migrasi dari AzureRM ke Az](migrate-from-azurerm-to-az.md)
* [Daftar lengkap perubahan putus dari AzureRM ke Az 1.0.0](migrate-az-1.0.0.md)
* The [Enable-AzureRmAlias](/powershell/module/az.accounts/enable-azurermalias) cmdlet

## <a name="supportability"></a>Dukungan

Az adalah modul PowerShell terbaru untuk Azure. Masalah atau permintaan fitur dapat dicatat langsung di [repositori GitHub](https://github.com/Azure/azure-powershell), atau melalui dukungan Microsoft jika Anda memiliki kontrak dukungan. Permintaan fitur akan diimplementasikan dalam versi terbaru Az. Masalah kritis akan diimplementasikan pada dua versi terakhir Az.

Karena modul Az PowerShell sekarang memiliki semua kemampuan modul AzureRM PowerShell dan lebih banyak lagi, kami akan menghentikan modul AzureRM PowerShell pada 29 Februari 2024.

Untuk menghindari gangguan layanan, [perbarui skrip Anda](https://aka.ms/azpsmigrate) yang menggunakan modul AzureRM PowerShell untuk menggunakan modul Az PowerShell paling lambat 29 Februari 2024. Untuk memperbarui skrip Anda secara otomatis, ikuti [panduan memulai cepat](/powershell/azure/quickstart-migrate-azurerm-to-az-automatically).

## <a name="data-collection"></a>Kumpulan data

Azure PowerShell mengumpulkan data telemetri secara default. Microsoft mengumpulkan data untuk mengidentifikasi pola penggunaan untuk mengidentifikasi masalah umum dan untuk meningkatkan pengalaman Azure PowerShell.
Microsoft Azure PowerShell tidak mengumpulkan data pribadi atau pribadi. Misalnya, data penggunaan membantu mengidentifikasi masalah seperti cmdlet dengan keberhasilan rendah dan membantu memprioritaskan pekerjaan kami.

Meskipun kami menghargai wawasan yang diberikan data ini, kami juga memahami bahwa tidak semua orang ingin mengirim data penggunaan. Anda dapat menonaktifkan pengumpulan data dengan [`Disable-AzDataCollection`](/powershell/module/az.accounts/disable-azdatacollection) cmdlet. Anda juga dapat membaca [pernyataan privasi](https://privacy.microsoft.com/privacystatement) kami untuk mempelajari lebih lanjut.
