---
title: Gambaran umum | PowerShell Tumpukan Azure Microsoft Docs
description: Gambaran umum PowerShell Azure Stack dengan instruksi untuk penginstalan dan konfigurasi.
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
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132428311"
---
# <a name="azurerm-module-250"></a>AzureRM Module 2.5.0

## <a name="requirements"></a>Persyaratan:
Versi minimum Azure Stack yang didukung adalah 1904.

Catatan: Jika Anda menggunakan versi instalan yang lebih lama, versi 1.2.11


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
    * Modul sumber daya baru yang mendukung versi api 2018-05-01 dengan profil hibrid 2019-03-01
    * PolicyDefinition(2016-12-01) dan PolicyDefinition(2017-06-01-preview) masih dengan versi api lama
* AzureRm.Compute
    * Modul perhitungan baru yang mendukung versi api 2017-12-01.'


* Rilis ini berkaitan dengan pemutakhiran profil api tertentu 2019-03-01-hybrid
* Semua modul akan mengambil lebih dari atau sama dengan dependensi pada modul AzureRm.Profile.
* Versi Api yang dikunyapkan oleh setiap modul akan diperbarui. 
    * Hitung - 30-12-2017
    * Jaringan - 01-10-2017
    * Storage - 01-2016
    * Sumber Daya - 01-02-2011
    * Keyvault - 2016-10-01
    * Dns - 2016-04-01
* Peta lengkap versi api untuk setiap tipe sumber daya dapat ditemukan di https://github.com/Azure/azure-rest-api-specs/blob/master/profile/2018-03-01-hybrid.json

## <a name="content"></a>Konten:
### <a name="azure-bridge"></a>Azure Bridge
Pratinjau rilis modul administrator Azure Stack AzureBridge yang memungkinkan Anda untuk men syndicate gambar dari Azure.

### <a name="backup"></a>Pencadangan
Rilis pratinjau modul administrator Cadangan yang memungkinkan administrator untuk:
- Mengonfigurasi di mana cadangan disimpan
- Melakukan pencadangan
- Cadangkan daftar dan pulihkan yang telah selesai

### <a name="commerce"></a>Perdagangan
Rilis pratinjau modul administrator Azure Stack Commerce yang menyediakan cara untuk menampilkan agregat penggunaan data di seluruh sistem Azure Stack Anda.

### <a name="compute"></a>Hitung
Rilis pratinjau modul administrator Hitung Tumpukan Azure yang menyediakan fungsionalitas untuk mengelola kuota perhitungan, gambar platform, disk yang dikelola dan ekstensi mesin virtual.

### <a name="fabric"></a>Fabric
Preview release of the Azure Stack Fabric administrator module which allows administrators to view and manage infrastructure components:
- Hentikan, Mulai dan Penutupan simpul unit skala
- Kuras dan Lanjutkan node unit skala untuk aktivitas yang terkait dengan FRU
- Perbaikan node unit skala
- Mulai ulang peran Infrastruktur
- Contoh peran Hentikan, Mulai dan Penutupan Infrastruktur
- Buat Kolam Renang IP baru


### <a name="gallery"></a>Galeri
Rilis pratinjau modul administrator Galeri Tumpukan Azure yang menyediakan fungsionalitas untuk mengelola item galeri di marketplace Azure Stack.

### <a name="infrastructure-insights"></a>Infrastruktur Insights
Rilis pratinjau modul Insights administrator infrastruktur yang memungkinkan administrator:
- Lihat kesehatan sumber daya stempel Azure Stack mereka
- Menampilkan dan mengelola pemberitahuan

### <a name="keyvault"></a>KeyVault
Rilis pratinjau modul administrator Azure Stack KeyVault yang memungkinkan administrator menampilkan kuota KeyVault.

### <a name="network"></a>Jaringan
Rilis pratinjau modul administrator jaringan yang memungkinkan:
- Manajemen kuota jaringan
- Menampilkan sumber daya jaringan yang dialokasikan seperti alamat IP publik, jaringan virtual, penyeimbang muat
- Menyediakan cmdlet yang menampilkan gambaran umum administrator

### <a name="storage"></a>Storage
Rilis pratinjau modul administrator Azure Stack Storage.  Dalam rilis ini, kami menyediakan fungsi untuk:
- Mengelola kuota penyimpanan
- Sumber daya penyimpanan terkumpul sampah yang dihapus
- Memulihkan akun penyimpanan yang dihapus
- Melakukan migrasi wadah dari satu berbagi ke yang lain
- Menampilkan informasi tentang komponen penyimpanan individual
- Menampilkan informasi penggunaan dan kinerja

### <a name="subscription-admin"></a>Admin Langganan
Rilis pratinjau modul administrator Langganan Tumpukan Azure.  Modul ini menyediakan fungsionalitas untuk administrator untuk:
- Mengelola paket dan penawaran
- Menampilkan informasi penggunaan dan kinerja
- Kelola RBAC

### <a name="subscription"></a>Langganan
Rilis pratinjau modul Langganan Tumpukan Azure.  Modul ini menyediakan fungsionalitas bagi Pengguna untuk:
- Membuat, Menghapus, dan Memperbarui Langganan

### <a name="update"></a>Perbarui
Rilis pratinjau modul administrator Pembaruan Tumpukan Azure.  Dalam modul ini administrator dapat:
- Membuat daftar dan menginstal pembaruan yang tersedia
- Lanjutkan pembaruan yang terganggu
- Menampilkan pembaruan yang diinstal
