---
title: Penjelasan Umum Azure Stack Admin PowerShell | Microsoft Docs
description: Penjelasan umum Azure Stack Admin PowerShell dengan petunjuk penginstalan dan konfigurasi.
author: bganapa
ms.author: bganapa
manager: knithinc
ms.devlang: powershell
ms.topic: conceptual
ms.manager: knithinc
ms.date: 09/21/2018
ms.openlocfilehash: afa83a6258e57e961576b328e67fad634704dddf
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132428299"
---
# <a name="azure-stack-module-150"></a>Modul Azure Stack 1.5.0

## <a name="requirements"></a>Persyaratan:
Versi Azure Stack minimum yang didukung adalah versi 1808.

Catatan: Jika Anda menggunakan versi yang lebih lama, instal versi 1.4.0

## <a name="known-issues"></a>Masalah umum:

- New-AzsOffer tidak mengizinkan untuk membuat penawaran dengan status publik. Cmdlet Set-AzsOffer perlu dipanggil setelahnya untuk mengubah status.
- Kumpulan IP tidak dapat dihapus tanpa penyebaran ulang

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
* Semua modul Admin Azure Stack diperbarui untuk dependensi yang lebih besar atau sama dengan modul AzureRm.Profile
* Dukungan untuk menangani nama sumber daya berlapis di semua modul
* Perbaikan bug di semua modul tempat ErrorActionPreference diganti menjadi Stop
* Modul Azs.Compute.Admin
    * Properti kuota baru ditambahkan untuk mendukung disk yang dikelola
    * Penambahan cmdlet terkait migrasi disk
    * Properti tambahan di objek ekstensi Platform Image dan VM
* Azs.Fabric.Admin 
    * Cmdlet baru untuk menambahkan node unit skala
* Azs.Backup.Admin
    * Set-AzsBackupShare sekarang menjadi alias untuk cmdlet Set-AzsBackupConfiguration
    * Get-AzsBackupLocation sekarang menjadi alias untuk cmdlet Get-AzsBackupConfiguration
    * Set-AzsBackupConfiguration, parameter BackupShare, sekarang menjadi alias untuk jalur parameter
* Azs.Subscriptions
    * Get-AzsDelegatedProviderOffer, parameter OfferName, sekarang menjadi alias untuk Penawaran
* Azs.Subscriptions.Admin
    * Get-AzsDelegatedProviderOffer, parameter OfferName, sekarang menjadi alias untuk Penawaran

## <a name="content"></a>Konten:
### <a name="azure-bridge"></a>Azure Bridge
Pratinjau rilis modul administrator Azure Stack AzureBridge yang memungkinkan Anda untuk sindikasi gambar dari Azure.

### <a name="backup"></a>Cadangan
Pratinjau rilis modul administrator Azure Backup yang memungkinkan administrator:
- Mengonfigurasi tempat cadangan disimpan
- Melakukan pencadangan
- Mencantumkan dan memulihkan cadangan yang telah selesai

### <a name="commerce"></a>Commerce
Pratinjau rilis modul administrator Azure Stack Commerce yang menyediakan cara untuk melihat penggunaan data gabungan di seluruh sistem Azure Stack.

### <a name="compute"></a>Compute
Pratinjau rilis modul administrator Azure Stack Compute yang menyediakan fungsi untuk mengelola kuota komputasi, gambar platform, disk terkelola, dan ekstensi komputer virtual.

### <a name="fabric"></a>Fabric
Pratinjau rilis modul administrator Azure Stack Fabric yang memungkinkan administrator untuk melihat dan mengelola komponen infrastruktur:
- Menghentikan, Memulai, dan Mematikan node unit skala
- Mengosongkan dan Melanjutkan node unit skala untuk aktivitas terkait FRU
- Perbaikan node unit skala
- Memulai kembali peran Infrastruktur
- Menghentikan, Memulai, dan Mematikan instans peran Infrastruktur
- Membuat Kumpulan IP baru


### <a name="gallery"></a>galeri
Pratinjau rilis modul administrator Azure Stack Gallery yang menyediakan fungsi untuk mengelola item galeri di marketplace Azure Stack.

### <a name="infrastructure-insights"></a>Infrastructure Insights
Pratinjau rilis modul administrator Infrastructure Insights yang memungkinkan administrator:
- Melihat kondisi sumber daya stamp Azure Stack
- Melihat dan mengelola peringatan

### <a name="keyvault"></a>Az.KeyVault
Pratinjau rilis modul administrator Azure Stack KeyVault yang memungkinkan administrator untuk melihat kuota KeyVault.

### <a name="network"></a>Jaringan
Pratinjau rilis modul administrator Jaringan yang memungkinkan:
- Pengelolaan kuota jaringan
- Melihat sumber daya jaringan yang dialokasikan seperti alamat IP publik, jaringan virtual, load balancer
- Menyediakan cmdlet yang menampilkan ringkasan administrator

### <a name="storage"></a>Penyimpanan
Pratinjau rilis modul administrator Azure Stack Storage.  Dalam rilis ini, kami menyediakan fungsi untuk:
- Mengelola kuota penyimpanan
- Pengumpul sampah sumber daya penyimpanan yang dihapus
- Memulihkan akun penyimpanan yang dihapus
- Memigrasikan kontainer dari satu bagian ke bagian lainnya
- Melihat informasi tentang komponen penyimpanan individu
- Melihat informasi penggunaan dan performa

### <a name="subscription-admin"></a>Admin Langganan
Pratinjau rilis modul administrator Langganan Azure Stack.  Modul ini menyediakan fungsi bagi administrator untuk:
- Mengelola paket dan penawaran
- Melihat informasi penggunaan dan performa
- Mengelola RBAC

### <a name="subscription"></a>Langganan
Pratinjau rilis modul Langganan Azure Stack.  Modul ini menyediakan fungsi bagi Pengguna untuk:
- Membuat, Menghapus, dan Memperbarui Langganan

### <a name="update"></a>Pembaruan
Pratinjau rilis modul administrator Azure Stack Update.  Dalam modul ini, administrator dapat:
- Mencantumkan dan menginstal pembaruan yang tersedia
- Melanjutkan pembaruan yang terganggu
- Melihat pembaruan yang diinstal
