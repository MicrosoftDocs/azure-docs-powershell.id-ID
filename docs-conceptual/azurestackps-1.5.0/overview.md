---
title: Gambaran umum tentang PowerShell Admin Tumpukan Azure | Microsoft Docs
description: Gambaran umum PowerShell Admin Tumpukan Azure dengan instruksi untuk penginstalan dan konfigurasi.
author: bganapa
ms.author: bganapa
manager: knithinc
ms.devlang: powershell
ms.topic: conceptual
ms.manager: knithinc
ms.date: 09/21/2018
ms.openlocfilehash: afa83a6258e57e961576b328e67fad634704dddf
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132428299"
---
# <a name="azure-stack-module-150"></a>Azure Stack Module 1.5.0

## <a name="requirements"></a>Persyaratan:
Versi minimum Azure Stack yang didukung adalah 1808.

Catatan: Jika Anda menggunakan versi instalan yang lebih lama, versi 1.4.0

## <a name="known-issues"></a>Masalah umum:

- New-AzsOffer tidak memperbolehkan untuk membuat penawaran dengan negara bagian publik. Cmdlet Set-AzsOffer harus dipanggil sesudahnya untuk mengubah status.
- Ip Pool tidak bisa dihapus tanpa reeployment

## <a name="install"></a>Instal
```
# Remove previous versions of AzureStack modules
Uninstall-Module -Name AzureStack -Force 
Uninstall-Module AzureRM.AzureStackAdmin -Force
Uninstall-Module AzureRM.AzureStackStorage -Force
Get-Module Azs.* -ListAvailable | Uninstall-Module -Force


# Install the AzureRM.Bootstrapper module. Select Yes when prompted to install NuGet
Install-Module -Name AzureRm.BootStrapper

# Install and import the API Version Profile required by Azure Stack into the current PowerShell session.
Use-AzureRmProfile -Profile 2018-03-01-hybrid -Force

# Install Azure Stack Admin Module
Install-Module -Name AzureStack -RequiredVersion 1.5.0
```

## <a name="release-notes"></a>Catatan Rilis
* Semua modul Azure Stack Admin diperbarui agar lebih besar dari atau sama dengan dependensi pada modul AzureRm.Profile
* Dukungan untuk menangani nama sumber daya bertumel di semua modul
* Perbaikan bug di semua modul dengan ErrorActionPreference yang sedang ditimpa menjadi Stop
* Azs.Compute.Admin Module
    * Properti kuota baru ditambahkan untuk dukungan disk yang tersedia
    * Penambahan cmdlet terkait migrasi disk
    * Properti tambahan dalam objek ekstensi VM dan Gambar Platform
* Azs.Fabric.Admin 
    * Cmdlet baru untuk menambahkan node unit skala
* Azs.Backup.Admin
    * Set-AzsBackupShare kini merupakan alias untuk cmdlet Set-AzsBackupConfiguration
    * Get-AzsBackupLocation kini merupakan alias untuk cmdlet Get-AzsBackupConfiguration
    * Set-AzsBackupConfiguration, parameter BackupShare kini alias untuk jalur parameter
* Azs.Subscriptions
    * Get-AzsDelegatedProviderOffer, parameter OfferName kini alias untuk Penawaran
* Azs.Subscriptions.Admin
    * Get-AzsDelegatedProviderOffer, parameter OfferName kini alias untuk Penawaran

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
