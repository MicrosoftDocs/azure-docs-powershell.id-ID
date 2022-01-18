---
Module Name: Az.StorageSync
Module Guid: 001b4bbc-9d7d-43b2-9e95-7a70325e9509
Download Help Link: https://docs.microsoft.com/powershell/module/az.storagesync
Help Version: 1.0.0.0
Locale: en-US
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StorageSync/StorageSync/help/Az.StorageSync.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StorageSync/StorageSync/help/Az.StorageSync.md
ms.openlocfilehash: 717dd7678e3b7445c545576dfed6689f7f9a19d9
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/02/2021
ms.locfileid: "136160982"
---
# Az.StorageSync Module
## Deskripsi
Cmdlet di modul Storage Sync memungkinkan Anda mengelola operasi terkait Sinkronisasi File Azure di PowerShell.

## Az.StorageSync Cmdlets
### [Get-AzStorageSyncCloudEndpoint](Get-AzStorageSyncCloudEndpoint.md)
Perintah ini mencantumkan semua titik akhir awan dalam grup sinkronisasi tertentu.

### [Get-AzStorageSyncGroup](Get-AzStorageSyncGroup.md)
Perintah ini mencantumkan semua grup sinkronisasi dalam layanan sinkronisasi penyimpanan tertentu.

### [Get-AzStorageSyncServer](Get-AzStorageSyncServer.md)
Perintah ini mencantumkan semua server yang terdaftar ke layanan sinkronisasi penyimpanan tertentu.

### [Get-AzStorageSyncServerEndpoint](Get-AzStorageSyncServerEndpoint.md)
Perintah ini mencantumkan semua titik akhir server dalam grup sinkronisasi tertentu.

### [Get-AzStorageSyncService](Get-AzStorageSyncService.md)
Perintah ini mencantumkan semua layanan sinkronisasi penyimpanan dalam lingkup langganan/grup sumber daya tertentu.

### [Invoke-AzStorageSyncChangeDetection](Invoke-AzStorageSyncChangeDetection.md)
Perintah ini bisa digunakan untuk memulai deteksi perubahan ruang nama secara manual. File dapat ditargetkan ke seluruh file bersama, subfolder, atau kumpulan file. Maksimum 10.000 item dapat dideteksi. Jika lingkup perubahan diketahui oleh Anda, batasi eksekusi perintah ini ke bagian ruang nama, jadi ubah deteksi bisa selesai dengan cepat dan dalam batas 10.000 item.

> [!Note]  
> Cmdlet Invoke-AzStorageSyncChangeDetection tidak akan mendeteksi perubahan berikut dalam berbagi file Azure:
> - File yang dihapus. 
> - File yang dipindahkan dari berbagi.
> - File yang dihapus dan dibuat dengan nama yang sama.  
> 
>  Perubahan ini akan dideteksi ketika [pekerjaan deteksi perubahan](https://docs.microsoft.com/azure/storage/files/storage-sync-files-troubleshoot?tabs=portal1%2Cazure-portal#afs-change-detection) berjalan.

### [Invoke-AzStorageSyncCompatibilityCheck](Invoke-AzStorageSyncCompatibilityCheck.md)
Memeriksa potensi masalah kompatibilitas antara sistem dan Sinkronisasi File Azure.

### [New-AzStorageSyncCloudEndpoint](New-AzStorageSyncCloudEndpoint.md)
Perintah ini akan membuat titik akhir awan Sinkronisasi File Azure dalam grup sinkronisasi.

### [New-AzStorageSyncGroup](New-AzStorageSyncGroup.md)
Perintah ini membuat grup sinkronisasi baru dalam layanan sinkronisasi penyimpanan tertentu.

### [New-AzStorageSyncServerEndpoint](New-AzStorageSyncServerEndpoint.md)
Perintah ini membuat titik akhir server baru pada server yang terdaftar. Proses ini mengaktifkan jalur tertentu di server untuk mulai menyinkronkan file dengan titik akhir lain dalam grup sinkronisasi.

### [New-AzStorageSyncService](New-AzStorageSyncService.md)
Perintah ini akan membuat layanan sinkronisasi penyimpanan baru dalam grup sumber daya.

### [Register-AzStorageSyncServer](Register-AzStorageSyncServer.md)
Perintah ini mendaftarkan server ke layanan sinkronisasi penyimpanan yang membuat hubungan kepercayaan. PowerShell atau portal Azure selanjutnya bisa digunakan untuk mengonfigurasi sinkronisasi di server ini.

### [Remove-AzStorageSyncCloudEndpoint](Remove-AzStorageSyncCloudEndpoint.md)
Perintah ini akan menghapus titik akhir awan tertentu dari grup sinkronisasi. Tanpa setidaknya satu titik akhir awan, tidak ada titik akhir server lain dalam grup sinkronisasi ini yang dapat disinkronkan.

### [Remove-AzStorageSyncGroup](Remove-AzStorageSyncGroup.md)
Perintah ini akan menghapus grup sinkronisasi tertentu.

### [Remove-AzStorageSyncServerEndpoint](Remove-AzStorageSyncServerEndpoint.md)
Perintah ini akan menghapus titik akhir server yang ditentukan. Sinkronisasi ke lokasi ini akan segera berhenti.

### [Remove-AzStorageSyncService](Remove-AzStorageSyncService.md)
Perintah ini akan menghapus layanan sinkronisasi penyimpanan tertentu.

### [Reset-AzStorageSyncServerCertificate](Reset-AzStorageSyncServerCertificate.md)
Gunakan untuk pemecahan masalah saja. Perintah ini akan meluncurkan sertifikat server sinkronisasi penyimpanan yang digunakan untuk menjelaskan identitas server ke layanan sinkronisasi penyimpanan.

### [Set-AzStorageSyncServerEndpoint](Set-AzStorageSyncServerEndpoint.md)
Perintah ini memungkinkan perubahan pada parameter titik akhir server yang dapat disesuaikan.

### [Set-AzStorageSyncService](Set-AzStorageSyncService.md)
Perintah ini mengatur layanan sinkronisasi penyimpanan dalam grup sumber daya.

### [Unregister-AzStorageSyncServer](Unregister-AzStorageSyncServer.md)
Peringatan: Membatalkan pendaftaran server akan mengakibatkan penghapusan kaskada dari semua titik akhir server di server ini. Perintah ini akan membatalkan pendaftaran server dari layanan sinkronisasi penyimpanannya.

