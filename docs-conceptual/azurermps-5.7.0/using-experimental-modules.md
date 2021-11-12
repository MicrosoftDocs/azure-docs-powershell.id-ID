---
title: Menggunakan modul Azure PowerShell eksperimental
description: Memahami ilmu filsafat dan penggunaan modul Azure PowerShell eksperimental.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 09/05/2017
ms.custom: devx-track-azurepowershell
ms.openlocfilehash: aab6ad57d3f687ad0724781664695d2a0ece11a8
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132425047"
---
# <a name="using-experimental-azure-powershell-modules"></a>Menggunakan modul Azure PowerShell eksperimental

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

Dengan penekanan pada alat pengembang (khususnya CLIS) di Azure, tim Azure PowerShell sedang bereksperimen dengan banyak penyempurnaan pada pengalaman Azure PowerShell anda.

## <a name="experimentation-methodology"></a>Metodologi eksperimen

Untuk memfasilitasi eksperimen, kami membuat modul baru Azure PowerShell yang mengimplementasikan fungsionalitas Azure SDK yang sudah ada dengan cara baru yang lebih mudah digunakan. Dalam banyak kasus, cmdlet sama persis seperti cmdlet yang sudah ada. Namun, cmdlet eksperimental menyediakan notasi singkatan dan nilai default yang lebih cerdas yang memudahkan untuk membuat dan mengelola sumber daya Azure.

Modul ini dapat diinstal berdampingan dengan modul Azure PowerShell yang sudah ada. Nama cmdlet telah disingkat untuk memberikan nama yang lebih singkat dan menghindari konflik nama dengan cmdlet yang sudah ada dan bukan eksperimental.

Modul eksperimental menggunakan konvensi penamaan berikut: `AzureRM.*.Experiments` . Konvensi penamaan ini mirip dengan penamaan modul Pratinjau: `AzureRM.*.Preview` . Modul pratinjau berbeda dari modul eksperimental. Modul pratinjau menerapkan fungsi baru layanan Azure yang hanya tersedia sebagai penawaran Pratinjau. Modul pratinjau menggantikan modul Azure PowerShell yang sudah ada dan menggunakan cmdlet dan nama parameter yang sama.

## <a name="how-to-install-an-experimental-module"></a>Cara menginstal modul eksperimental

Modul eksperimental diterbitkan ke Galeri PowerShell sama seperti modul Azure PowerShell yang sudah ada. Untuk melihat daftar modul eksperimental, jalankan perintah berikut:

```azurepowershell-interactive
Find-Module AzureRM.*.Experiments
```

```output
Version Name                         Repository Description
------- ----                         ---------- -----------
1.0.25  AzureRM.Compute.Experiments  PSGallery  Azure Compute experiments for VM creation
1.0.0   AzureRM.Websites.Experiments PSGallery  Create and deploy web applications using Azure App Services.
```

Untuk menginstal modul eksperimental, gunakan perintah berikut dari sesi PowerShell yang ditingkatkan:

```azurepowershell-interactive
Install-Module AzureRM.Compute.Experiments
Install-Module AzureRM.Websites.Experiments
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

- "Smart Create" - Semua skenario pembuatan yang  menerapkan "Smart Create" tidak akan memiliki parameter yang diperlukan: semua informasi yang diperlukan akan dipilih oleh Azure PowerShell oleh para opini.

- Parameter Abu-abu - Dalam banyak kasus, beberapa parameter bisa "abu-abu" atau semi-opsional. Jika parameter tidak ditentukan, pengguna akan ditanya apakah mereka ingin parameter dibuat untuk mereka. Parameter abu-abu juga dapat disimpulkan berdasarkan konteks dengan persetujuan pengguna.
  Misalnya, mungkin akan masuk akal membuat parameter abu-abu menyarankan nilai yang terakhir digunakan.

- `-Auto`Sakelar - Sakelar akan menyediakan cara "memilih" bagi pengguna untuk default semua hal sekaligus mempertahankan integritas parameter yang diperlukan `-Auto` dalam jalur garis utama. 

### <a name="feature-specific-switches"></a>Sakelar khusus fitur

Misalnya, skenario "Buat aplikasi web" mungkin memiliki atau beralih yang akan menambahkan jarak jauh "azure" secara otomatis ke repositori `-Git` `-AddRemote` git yang ada.

- Settable Default - Pengguna harus memiliki kemampuan untuk menetapkan parameter lain secara default seperti `-ResourceGroupName` dan `-Location` .

- Default Ukuran - "ukuran" sumber daya dapat membingungkan bagi pengguna karena banyak Penyedia Sumber Daya menggunakan nama yang berbeda (misalnya, "Standar \_ DS1 \_ v2" atau "S1"). Namun, sebagian besar pengguna lebih peduli dengan biaya. Oleh karena itu, menetapkan ukuran "universal" berdasarkan jadwal harga akan lebih masuk akal. Pengguna dapat memilih ukuran tertentu atau Azure PowerShell opsi _terbaik_ berdasarkan sumber daya anggaran.

- Format Output - Azure PowerShell ini `PSObject` mengembalikan s dan tidak ada sedikit output konsol. Azure PowerShell mungkin perlu menampilkan beberapa informasi kepada pengguna mengenai "default cerdas" yang digunakan.
