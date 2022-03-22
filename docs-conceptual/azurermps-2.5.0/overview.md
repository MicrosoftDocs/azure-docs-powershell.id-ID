---
title: Gambaran Umum Azure Stack PowerShell | Microsoft Docs
description: Gambaran umum Azure Stack PowerShell dengan instruksi untuk penginstalan dan konfigurasi.
author: bganapa
ms.author: bganapa
manager: knithinc
ms.devlang: powershell
ms.topic: conceptual
ms.manager: knithinc
ms.date: 09/21/2018
ms.custom: devx-track-azurepowershell
ms.openlocfilehash: 4b72bbd1bda93767251e0ba3d488f798575d9115
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132428311"
---
# <a name="azurerm-module-250"></a>AzureRM Module 2.5.0

## <a name="requirements"></a>Persyaratan:
Versi Azure Stack minimum yang didukung adalah versi tahun 1904.

Catatan: Jika Anda menggunakan versi yang lebih lama, pasang versi 1.2.11


## <a name="install"></a>Instal
```powershell-interactive
# Remove previous versions of AzureStack modules
Uninstall-Module -Name AzureStack -Force 
Uninstall-Module -Name AzureRM -Force 
Uninstall-Module AzureRM.AzureStackAdmin -Force -ErrorAction Continue
Uninstall-Module AzureRM.AzureStackStorage -Force -ErrorAction Continue
Get-Module Azs.* -ListAvailable | Uninstall-Module -Force
Get-Module Azure.* -ListAvailable | Uninstall-Module -Force


# Install the AzureRM.Bootstrapper module. Select Yes when prompted to install NuGet
Install-Module -Name AzureRm.BootStrapper

# Install and import the API Version Profile required by Azure Stack into the current PowerShell session.
Use-AzureRmProfile -Profile 2018-03-01-hybrid -Force

```

## <a name="release-notes"></a>Catatan Rilis
* AzureRm.Resources
    * Modul Sumber Daya baru yang mendukung versi api 2018-05-01 dengan profil hibrid 2019-03-01
    * Operasi PolicyDefinition(2016-12-01) dan PolicyAssisgment(2017-06-01-preview) masih dengan versi api lama
* AzureRm.Compute
    * Modul komputasi baru yang mendukung versi api 2017-12-01.'


* Rilis ini sesuai dengan profil api spesifik azurestack 2019-03-01-hybrid
* Semua modul mengambil lebih besar dari atau sama dengan dependensi di modul AzureRm.Profile.
* Versi Api yang didukung oleh setiap modul diperbarui. 
    * Komputasi - 2017-12-30
    * Jaringan - 2017-10-01
    * Penyimpanan - 2016-01-01
    * Sumber daya - 2018-02-01
    * Keyvault - 2016-10-01
    * Dns - 2016-04-01
* Peta versi api lengkap untuk setiap jenis sumber daya dapat ditemukan di https://github.com/Azure/azure-rest-api-specs/blob/master/profile/2018-03-01-hybrid.json

## <a name="content"></a>Konten:
### <a name="azure-bridge"></a>Azure Bridge
Pratinjau rilis modul administrator Azure Stack AzureBridge yang memungkinkan Anda untuk mensindikasikan citra dari Azure.

### <a name="backup"></a>Cadangan
Pratinjau rilis modul administrator Microsoft Azure Backup yang memungkinkan administrator untuk:
- Mengonfigurasi tempat cadangan disimpan
- Melakukan pencadangan
- Mencantumkan dan memulihkan cadangan yang telah selesai

### <a name="commerce"></a>Commerce
Pratinjau rilis modul administrator Azure Stack Commerce yang menyediakan cara untuk menampilkan penggunaan data agregat di seluruh sistem Azure Stack.

### <a name="compute"></a>Compute
Pratinjau rilis modul administrator Azure Stack Compute yang menyediakan fungsionalitas untuk mengelola kuota komputasi, citra platform, disk terkelola, dan ekstensi mesin virtual.

### <a name="fabric"></a>Fabric
Pratinjau rilis modul administrator Azure Stack Fabric yang memungkinkan administrator untuk menampilkan dan mengelola komponen infrastruktur:
- Menghentikan, Memulai, dan Mematikan node unit skala
- Menguras dan Melanjutkan node unit skala untuk aktivitas terkait FRU
- Perbaikan node unit skala
- Memulai kembali peran Infrastruktur
- Menghentikan, Memulai, dan Mematikan instans peran Infrastruktur
- Membuat Kumpulan IP baru


### <a name="gallery"></a>galeri
Pratinjau rilis modul administrator Azure Stack Gallery yang menyediakan fungsionalitas untuk mengelola item galeri di marketplace Azure Stack.

### <a name="infrastructure-insights"></a>Infrastructure Insights
Pratinjau rilis modul administrator Infrastructure Insights yang memungkinkan administrator:
- Menampilkan kesehatan sumber daya stempel Azure Stack
- Menampilkan dan mengelola peringatan

### <a name="keyvault"></a>Az.KeyVault
Pratinjau rilis modul administrator Azure Stack KeyVault yang memungkinkan administrator untuk menampilkan kuota KeyVault.

### <a name="network"></a>Jaringan
Pratinjau rilis modul administrator Jaringan yang memungkinkan:
- Manajemen kuota jaringan
- Menampilkan sumber daya jaringan yang dialokasikan seperti alamat IP publik, jaringan virtual, penyeimbang beban
- Menyediakan cmdlet yang menampilkan gambaran umum administrator

### <a name="storage"></a>Penyimpanan
Pratinjau rilis modul administrator Azure Stack Storage.  Dalam rilis ini kami menyediakan fungsionalitas untuk:
- Mengelola kuota penyimpanan
- Sampah mengumpulkan sumber daya penyimpanan yang dihapus
- Memulihkan akun penyimpanan yang dihapus
- Memigrasikan kontainer dari satu bagian ke bagian lainnya
- Melihat informasi tentang komponen penyimpanan individu
- Menampilkan informasi penggunaan dan performa

### <a name="subscription-admin"></a>Admin Langganan
Pratinjau rilis modul administrator Langganan Azure Stack.  Modul ini menyediakan fungsionalitas bagi administrator untuk:
- Mengelola paket dan penawaran
- Menampilkan informasi penggunaan dan performa
- Mengelola RBAC

### <a name="subscription"></a>Langganan
Pratinjau rilis modul Langganan Azure Stack.  Modul ini menyediakan fungsionalitas bagi Pengguna untuk:
- Membuat, Menghapus, dan Memperbarui Langganan

### <a name="update"></a>Pembaruan
Pratinjau rilis modul administrator Azure Stack Update.  Dalam modul ini administrator dapat:
- Mencantumkan dan menginstal pembaruan yang tersedia
- Melanjutkan pembaruan yang terganggu
- Melihat pembaruan yang diinstal
