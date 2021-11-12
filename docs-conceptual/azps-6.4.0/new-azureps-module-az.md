---
title: Memperkenalkan modul PowerShell Azure Az
description: Memperkenalkan modul Az PowerShell, disarankan untuk berinteraksi dengan Azure, dan pengganti modul PowerShell AzureRM.
ms.date: 09/27/2021
ms.devlang: powershell
ms.topic: conceptual
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
ms.openlocfilehash: 4e6c5fc546407618fe8996f9ce4cbc15cb3801d7
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "132429486"
---
# <a name="introducing-the-azure-az-powershell-module"></a>Memperkenalkan modul PowerShell Azure Az

## <a name="overview"></a>Gambaran umum

Modul Az PowerShell adalah kumpulan cmdlet untuk mengelola sumber daya Azure langsung dari PowerShell.
PowerShell menyediakan fitur canggih untuk otomatisasi yang dapat dimanfaatkan untuk mengelola sumber daya Azure, misalnya dalam konteks saluran CI/CD.

Modul Az PowerShell adalah pengganti AzureRM dan merupakan versi yang disarankan untuk digunakan dalam berinteraksi dengan Azure.

Anda bisa menggunakan modul Az PowerShell dengan salah satu metode berikut ini:

* [Instal modul Az PowerShell melalui PowerShellGet](install-az-ps.md) (opsi yang disarankan).
* [Instal modul Az PowerShell dengan MSI.](install-az-ps-msi.md)
* [Gunakan Azure Cloud Shell](/azure/cloud-shell/overview).
* [Gunakan wadah Az PowerShell Docker](azureps-in-docker.md).

## <a name="features"></a>Fitur

Modul Az PowerShell menampilkan manfaat berikut ini:

* Keamanan dan stabilitas
  * Enkripsi cache token
  * Pencegahan tipe serangan man-in-the-middle
  * Autentikasi dukungan dengan ADFS 2019
  * Autentikasi nama pengguna dan kata sandi di PowerShell 7
  * Dukungan untuk fitur seperti evaluasi akses berkelanjutan (akan hadir 2021)
* Dukungan untuk semua layanan Azure
  * Semua layanan Azure yang tersedia secara umum memiliki modul PowerShell yang didukung terkait
  * Beberapa perbaikan bug dan pemutakhiran versi API sejak AzureRM
* Kapabilitas baru
  * Dukungan di Cloud Shell dan lintas platform
  * Bisa mendapatkan dan menggunakan token akses untuk mengakses sumber daya Azure
  * Cmdlet tersedia untuk operasi REST tingkat lanjut dengan sumber daya Azure

> [!NOTE]
> PowerShell 7.0.6 LTS, PowerShell 7.1.3, atau yang lebih tinggi adalah versi PowerShell yang disarankan untuk digunakan dengan modul PowerShell Azure Az di semua platform.

Modul Az PowerShell didasarkan pada pustaka .NET Standard dan berfungsi dengan PowerShell 7 dan yang lebih baru di semua platform termasuk Windows, macOS, dan Linux. Ini juga kompatibel dengan Windows PowerShell 5.1.

Kami berkomitmen untuk menghadirkan dukungan Azure ke semua platform dan semua modul Az PowerShell adalah platform lintas platform.

## <a name="upgrade-your-environment-to-az"></a>Mutakhirkan lingkungan Anda ke Az

Untuk terus mengikuti fitur Terbaru Azure di PowerShell, Anda harus melakukan migrasi ke modul Az. Jika Anda belum siap untuk menginstal modul Az sebagai pengganti AzureRM, Anda memiliki beberapa opsi yang tersedia untuk bereksperimen dengan Az:

* Menggunakan lingkungan `PowerShell` dengan Azure Cloud [Shell](/azure/cloud-shell/overview). Azure Cloud Shell adalah lingkungan shell berbasis browser yang dilengkapi dengan alias kompatibilitas dan instalan modul Az `Enable-AzureRM` yang diaktifkan.
* Biarkan modul AzureRM terinstal di Windows PowerShell 5.1 dan instal modul Az di PowerShell 7 atau yang lebih baru. Windows PowerShell 5.1 dan PowerShell 7 dan yang lebih baru menggunakan kumpulan modul terpisah. Ikuti instruksi untuk menginstal versi [terbaru PowerShell lalu](/powershell/scripting/install/installing-powershell) instal [modul Az dari](install-az-ps.md) PowerShell 7 atau yang lebih baru.

Untuk memutakhirkan dari instalan AzureRM yang sudah ada:

1. [Menghapus instalan Azure PowerShell modul AzureRM](/powershell/azure/uninstall-az-ps#uninstall-the-azurerm-module)
1. [Instal modul Azure PowerShell Az](install-az-ps.md)
1. **OPSIONAL**: Mengaktifkan mode kompatibilitas untuk menambahkan alias untuk cmdlet AzureRM dengan [Enable-AzureRMAlias](/powershell/module/az.accounts/enable-azurermalias) ketika Anda terbiasa dengan kumpulan perintah baru. Untuk informasi selengkapnya, lihat bagian berikutnya atau [Memulai migrasi dari AzureRM ke Az](migrate-from-azurerm-to-az.md).

## <a name="migrate-existing-scripts-from-azurerm-to-az"></a>Melakukan migrasi skrip yang sudah ada dari AzureRM ke Az

Jika skrip Anda masih didasarkan pada modul AzureRM, kami memiliki beberapa sumber daya untuk membantu Anda melakukan migrasi:

* [Mulai migrasi dari AzureRM ke Az](migrate-from-azurerm-to-az.md)
* [Daftar lengkap memutus perubahan dari AzureRM ke Az 1.0.0](migrate-az-1.0.0.md)
* Cmdlet [Enable-AzureRmAlias](/powershell/module/az.accounts/enable-azurermalias)

## <a name="supportability"></a>Dukungan

Az adalah modul PowerShell terbaru untuk Azure. Masalah atau permintaan fitur dapat masuk secara langsung [ke GitHub penyimpanan](https://github.com/Azure/azure-powershell), atau melalui dukungan Microsoft jika Anda memiliki kontrak dukungan. Permintaan fitur akan diterapkan dalam versi terbaru Az. Masalah kritis akan diterapkan pada dua versi terakhir Az.

Karena modul PowerShell Az kini memiliki semua kapabilitas modul PowerShell AzureRM dan lainnya, kami akan menghentikan modul PowerShell AzureRM pada 29 Februari 2024.

Untuk menghindari gangguan [layanan,](https://aka.ms/azpsmigrate) perbarui skrip Anda yang menggunakan modul PowerShell AzureRM untuk menggunakan modul Az PowerShell sebelum 29 Februari 2024. Untuk memperbarui skrip secara otomatis, ikuti [panduan mulai cepat](/powershell/azure/quickstart-migrate-azurerm-to-az-automatically).

## <a name="data-collection"></a>Pengumpulan data

Azure PowerShell mengumpulkan data telemetri secara default. Microsoft menggabungkan data yang dikumpulkan untuk mengidentifikasi pola penggunaan untuk mengidentifikasi masalah-masalah umum dan untuk meningkatkan Azure PowerShell.
Microsoft Azure PowerShell tidak mengumpulkan data pribadi atau pribadi apa pun. Misalnya, data penggunaan membantu mengidentifikasi masalah seperti cmdlet dengan keberhasilan rendah dan membantu memprioritaskan pekerjaan kami.

Meskipun kami menghargai wawasan yang menyediakan data ini, kami juga memahami bahwa tidak semua orang ingin mengirim data penggunaan. Anda dapat menonaktifkan pengumpulan data dengan [`Disable-AzDataCollection`](/powershell/module/az.accounts/disable-azdatacollection) cmdlet. Anda juga dapat membaca pernyataan [privasi kami](https://privacy.microsoft.com/privacystatement) untuk mempelajari selengkapnya.
