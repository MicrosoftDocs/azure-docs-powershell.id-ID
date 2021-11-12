---
title: Menggunakan modul Azure PowerShell eksperimental
description: Memahami ilmu filsafat dan penggunaan modul Azure PowerShell eksperimental.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 10/05/2021
ms.custom: devx-track-azurepowershell
ms.openlocfilehash: 2b72f39d58f8f7349326b71a5646fd90fbd4b333
ms.sourcegitcommit: c489152c02cceaa5c8e284933af57f07c5350961
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/07/2021
ms.locfileid: "132429341"
---
# <a name="use-experimental-azure-powershell-modules"></a>Menggunakan modul Azure PowerShell eksperimental

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

Dengan penekanan pada alat pengembang (khususnya CLIS) di Azure, tim Azure PowerShell sedang bereksperimen dengan banyak penyempurnaan pada pengalaman Azure PowerShell Anda.

## <a name="experimentation-methodology"></a>Metodologi eksperimen

Untuk memfasilitasi eksperimen, kami membuat modul baru Azure PowerShell yang mengimplementasikan fungsionalitas Azure SDK yang sudah ada dalam cara baru yang lebih mudah digunakan. Dalam banyak kasus, cmdlet sama persis dengan cmdlet yang sudah ada. Namun, cmdlet eksperimental menyediakan notasi singkatan dan nilai default yang lebih cerdas yang memudahkan untuk membuat dan mengelola sumber daya Azure.

Modul ini dapat diinstal berdampingan dengan modul Azure PowerShell yang sudah ada. Nama cmdlet telah disingkat untuk memberikan nama yang lebih singkat dan menghindari konflik nama dengan cmdlet yang sudah ada dan bukan eksperimental.

Modul eksperimental menggunakan konvensi penamaan berikut: `AzureRM.*.Experiments` . Konvensi penamaan ini mirip dengan penamaan modul Pratinjau: `AzureRM.*.Preview` . Modul pratinjau berbeda dari modul eksperimental. Modul pratinjau menerapkan fungsi baru layanan Azure yang hanya tersedia sebagai penawaran Pratinjau. Modul pratinjau menggantikan modul Azure PowerShell yang sudah ada dan menggunakan cmdlet dan nama parameter yang sama.

## <a name="how-to-install-an-experimental-module"></a>Cara menginstal modul eksperimental

Modul eksperimental diterbitkan ke Galeri PowerShell sama seperti modul Azure PowerShell yang sudah ada. Untuk melihat daftar modul eksperimental, jalankan perintah berikut:

```powershell
Find-Module -Name AzureRM.*.Experiments
```

```Output
Version Name                         Repository Description
------- ----                         ---------- -----------
1.0.25  AzureRM.Compute.Experiments  PSGallery  Azure Compute experiments for VM creation
1.0.0   AzureRM.Websites.Experiments PSGallery  Create and deploy web applications using Azure App Services.
```

Untuk menginstal modul eksperimental, gunakan perintah berikut dari sesi PowerShell yang ditingkatkan:

```powershell
Install-Module -Name AzureRM.Compute.Experiments
Install-Module -Name AzureRM.Websites.Experiments
```

### <a name="documentation-and-support"></a>Dokumentasi dan dukungan

Dokumentasi disertakan dalam paket penginstalan dan diakses menggunakan `Get-Help` cmdlet. Tidak ada dokumentasi resmi yang diterbitkan untuk modul eksperimental.

Kami mendorong Anda untuk menguji modul ini. Umpan balik Anda memungkinkan kami meningkatkan kegunaan dan merespons kebutuhan Anda. Namun, untuk percobaan, dukungan untuk modul ini terbatas. Pertanyaan atau laporan masalah dapat dikirimkan dengan membuat [masalah](https://github.com/Azure/azure-powershell/issues) di GitHub penyimpanan.

## <a name="experiments-and-areas-of-improvement"></a>Eksperimen dan area perbaikan

Penyempurnaan ini dipilih berdasarkan perbedaan kunci dalam bersaing dengan produk. Misalnya, Azure CLI 2.0 telah membuat poin dari perintah basing _pada skenario_ daripada area _permukaan API._
Azure CLI 2.0 menggunakan sejumlah default cerdas yang memudahkan skenario "memulai" bagi pengguna akhir.

### <a name="core-improvements"></a>Penyempurnaan inti

Penyempurnaan inti dianggap sebagai "common sense", dan sedikit eksperimen diperlukan untuk bergerak maju dalam menerapkan pembaruan ini.

- Cmdlet berbasis skenario - <em>*Semua</em>- cmdlet harus dirancang untuk skenario, bukan layanan Azure REST.

- Nama yang Lebih Pendek - Berisi nama cmdlet (misalnya, `New-AzureRmVM`  =>  `New-AzVm` ) dan nama parameter (misalnya, `-ResourceGroupName`  =>  `-Rg` ). Gunakan alias untuk kompatibilitas dengan cmdlet "lama". Menyediakan set parameter _yang kompatibel_ mundur.

- Default Cerdas - Buat default cerdas untuk mengisi informasi "diperlukan". Misalnya:
  - Grup Sumber Daya
  - Lokasi
  - Sumber daya dependen

### <a name="experimental-improvements"></a>Penyempurnaan eksperimental

Penyempurnaan eksperimental memberikan perubahan signifikan yang ingin divalidasi oleh tim melalui eksperimen.

- Tipe sederhana - Membuat skenario harus beralih dari tipe kompleks dan objek konfigurasi. Sederhanakan konfigurasi hingga satu atau dua parameter.

- "Smart Create" - Semua skenario pembuatan yang  menerapkan "Smart Create" tidak akan memiliki parameter yang diperlukan: semua informasi yang diperlukan akan dipilih oleh Azure PowerShell secara pendapat.

- Parameter Abu-abu - Dalam banyak kasus, beberapa parameter bisa "abu-abu" atau semi-opsional. Jika parameter tidak ditentukan, pengguna akan ditanya apakah mereka ingin parameter dibuat untuk mereka. Parameter abu-abu juga dapat disimpulkan berdasarkan konteks dengan persetujuan pengguna.
  Misalnya, mungkin akan masuk akal membuat parameter abu-abu menyarankan nilai yang terakhir digunakan.

- `-Auto`Sakelar - Sakelar akan menyediakan cara "memilih" bagi pengguna untuk default semua hal sekaligus mempertahankan integritas parameter yang diperlukan `-Auto` dalam jalur garis utama. 

### <a name="feature-specific-switches"></a>Sakelar khusus fitur

Misalnya, skenario "Buat aplikasi web" mungkin memiliki atau beralih yang akan menambahkan jarak jauh "azure" secara otomatis ke repositori `-Git` `-AddRemote` git yang ada.

- Settable Defaults - Pengguna harus dapat mengatur default untuk parameter umum seperti `-ResourceGroupName` dan `-Location` .

- Default Ukuran - "ukuran" sumber daya dapat membingungkan bagi pengguna karena banyak Penyedia Sumber Daya menggunakan nama yang berbeda (misalnya, "Standar \_ DS1 \_ v2" atau "S1"). Namun, sebagian besar pengguna lebih peduli dengan biaya. Jadi masuk akal menentukan ukuran "universal" berdasarkan jadwal harga. Pengguna dapat memilih ukuran tertentu atau Azure PowerShell opsi _terbaik_ berdasarkan sumber daya anggaran.

- Format Output - Azure PowerShell saat `PSObject` ini mengembalikan nilai dan tidak ada output konsol. Azure PowerShell mungkin perlu menampilkan beberapa informasi kepada pengguna tentang "default cerdas" yang digunakan.
