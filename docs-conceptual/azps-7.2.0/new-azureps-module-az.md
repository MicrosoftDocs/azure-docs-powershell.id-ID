---
description: Memperkenalkan modul Az PowerShell, yang direkomendasikan untuk berinteraksi dengan Azure, dan penggantian modul AzureRM PowerShell.
ms.custom: devx-track-azurepowershell
ms.date: 02/08/2022
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
title: Memperkenalkan modul Azure Az PowerShell
ms.openlocfilehash: b5a73d44cff5c6b32604d30ff86aa5f0147205e6
ms.sourcegitcommit: cdca0d3199eb118c98aafb63ffcacc3dd080f0d4
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/16/2022
ms.locfileid: "138855009"
---
# <a name="introducing-the-azure-az-powershell-module"></a>Memperkenalkan modul Azure Az PowerShell

## <a name="overview"></a>Gambaran Umum

Modul Az PowerShell adalah sekumpulan cmdlet untuk mengelola sumber daya Azure langsung dari PowerShell.
PowerShell menyediakan fitur canggih untuk otomatisasi yang dapat dimanfaatkan untuk mengelola sumber daya Azure Anda, misalnya dalam konteks pipeline CI/CD.

Modul Az PowerShell adalah pengganti AzureRM dan merupakan versi yang disarankan untuk digunakan untuk berinteraksi dengan Azure.

Anda dapat menggunakan modul Az PowerShell dengan salah satu metode berikut:

* [Instal modul Az PowerShell melalui PowerShellGet](install-az-ps.md) (opsi yang disarankan).
* [Instal modul Az PowerShell dengan MSI](install-az-ps-msi.md).
* [Gunakan Azure Cloud Shell](/azure/cloud-shell/overview).
* [Gunakan wadah Az PowerShell Docker](azureps-in-docker.md).

## <a name="features"></a>Fitur

Modul Az PowerShell menampilkan manfaat berikut:

* Keamanan dan stabilitas
  * Enkripsi cache token
  * Pencegahan tipe serangan man-in-the-middle
  * Mendukung otentikasi dengan ADFS 2019
  * Autentikasi nama pengguna dan kata sandi di PowerShell 7
  * Dukungan untuk fitur seperti evaluasi akses berkelanjutan
* Dukungan untuk semua layanan Azure
  * Semua layanan Azure yang tersedia secara umum memiliki modul PowerShell yang didukung yang sesuai
  * Beberapa perbaikan bug dan peningkatan versi API sejak AzureRM
* Kapabilitas baru
  * Dukungan di Cloud Shell dan lintas platform
  * Bisa mendapatkan dan menggunakan token akses untuk mengakses sumber daya Azure
  * Cmdlet tersedia untuk operasi REST tingkat lanjut dengan sumber daya Azure

> [!NOTE]
> PowerShell 7.0.6 LTS, PowerShell 7.1.3, atau lebih tinggi adalah versi PowerShell yang direkomendasikan untuk digunakan dengan modul Azure Az PowerShell di semua platform.

Modul Az PowerShell didasarkan pada library .NET Standard dan bekerja dengan PowerShell 7 dan yang lebih baru pada semua platform termasuk Windows, macOS, dan Linux. Ini juga kompatibel dengan Windows PowerShell 5.1.

Kami berkomitmen untuk menghadirkan dukungan Azure ke semua platform dan semua modul Az PowerShell bersifat lintas platform.

## <a name="upgrade-your-environment-to-az"></a>Tingkatkan lingkungan Anda ke Az

Untuk mengikuti fitur Azure terbaru di PowerShell, Anda harus bermigrasi ke modul Az. Jika Anda belum siap untuk menginstal modul Az sebagai pengganti AzureRM, Anda memiliki beberapa opsi yang tersedia untuk bereksperimen dengan Az:

* `PowerShell` Gunakan lingkungan dengan [Azure Cloud Shell](/azure/cloud-shell/overview). Azure Cloud Shell adalah lingkungan shell berbasis browser yang dilengkapi dengan modul Az yang diinstal dan `Enable-AzureRM` alias kompatibilitas diaktifkan.
* Simpan modul AzureRM yang diinstal di Windows PowerShell 5.1 dan instal modul Az di PowerShell 7 atau versi lebih baru. Windows PowerShell 5.1 dan PowerShell 7 dan yang lebih baru menggunakan koleksi modul terpisah. Ikuti petunjuk untuk menginstal [PowerShell versi terbaru](/powershell/scripting/install/installing-powershell) lalu [instal modul Az](install-az-ps.md) dari PowerShell 7 atau yang lebih baru.

Untuk meningkatkan dari instalasi AzureRM yang sudah ada:

1. [Menghapus modul Azure PowerShell AzureRM](/powershell/azure/uninstall-az-ps#uninstall-the-azurerm-module)
1. [Menginstal modul Azure PowerShell Az](install-az-ps.md)
1. **OPSIONAL**: Aktifkan mode kompatibilitas untuk menambahkan alias untuk cmdlet AzureRM dengan [Enable-AzureRMAlias](/powershell/module/az.accounts/enable-azurermalias) saat Anda terbiasa dengan kumpulan perintah baru. Untuk informasi selengkapnya, lihat bagian berikutnya atau [Mulai migrasi dari AzureRM ke Az](migrate-from-azurerm-to-az.md).

## <a name="migrate-existing-scripts-from-azurerm-to-az"></a>Memigrasikan skrip yang ada dari AzureRM ke Az

Jika skrip Anda masih didasarkan pada modul AzureRM, kami memiliki beberapa sumber daya untuk membantu Anda melakukan migrasi:

* [Memulai migrasi dari AzureRM ke Az](migrate-from-azurerm-to-az.md)
* [Daftar lengkap perubahan yang melanggar dari AzureRM ke Az 1.0.0](migrate-az-1.0.0.md)
* Cmdlet [Enable-AzureRmAlias](/powershell/module/az.accounts/enable-azurermalias)

## <a name="supportability"></a>Dukungan

Az adalah modul PowerShell terbaru untuk Azure. Masalah atau permintaan fitur dapat dicatat langsung di [repositori GitHub](https://github.com/Azure/azure-powershell), atau melalui dukungan Microsoft jika Anda memiliki kontrak dukungan. Permintaan fitur akan diimplementasikan dalam az versi terbaru. Masalah kritis akan diimplementasikan pada dua versi terakhir Az.

Karena modul Az PowerShell sekarang memiliki semua kemampuan modul AzureRM PowerShell dan lebih banyak lagi, kami akan menghentikan modul AzureRM PowerShell pada 29 Februari 2024.

Untuk menghindari gangguan layanan, [perbarui skrip Anda](https://aka.ms/azpsmigrate) yang menggunakan modul AzureRM PowerShell untuk menggunakan modul Az PowerShell paling lambat 29 Februari 2024. Untuk memperbarui skrip Anda secara otomatis, ikuti [panduan memulai cepat](/powershell/azure/quickstart-migrate-azurerm-to-az-automatically).

## <a name="data-collection"></a>Kumpulan data

Azure PowerShell mengumpulkan data telemetri secara default. Microsoft mengumpulkan data untuk mengidentifikasi pola penggunaan untuk mengidentifikasi masalah umum dan untuk meningkatkan pengalaman Azure PowerShell.
Microsoft Azure PowerShell tidak mengumpulkan data pribadi atau pribadi. Misalnya, data penggunaan membantu mengidentifikasi masalah seperti cmdlet dengan keberhasilan rendah dan membantu memprioritaskan pekerjaan kami.

Meskipun kami menghargai wawasan yang diberikan data ini, kami juga memahami bahwa tidak semua orang ingin mengirim data penggunaan. Anda dapat menonaktifkan pengumpulan data dengan [`Disable-AzDataCollection`](/powershell/module/az.accounts/disable-azdatacollection) cmdlet. Anda juga dapat membaca [pernyataan privasi](https://privacy.microsoft.com/privacystatement) kami untuk mempelajari lebih lanjut.
