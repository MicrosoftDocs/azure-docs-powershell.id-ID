---
title: Menggunakan modul Azure PowerShell eksperimental
description: Memahami filosofi dan penggunaan modul Azure PowerShell eksperimental.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 09/05/2017
ms.custom: devx-track-azurepowershell
ms.openlocfilehash: aab6ad57d3f687ad0724781664695d2a0ece11a8
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132425047"
---
# <a name="using-experimental-azure-powershell-modules"></a>Menggunakan modul Azure PowerShell eksperimental

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

Dengan penekanan pada alat pengembang (terutama CLI) di Azure, tim Azure PowerShell bereksperimen dengan banyak peningkatan pada pengalaman Azure PowerShell.

## <a name="experimentation-methodology"></a>Metodologi eksperimen

Untuk memfasilitasi eksperimen, kami membuat modul Azure PowerShell baru yang menerapkan fungsionalitas Azure SDK yang ada dengan cara baru yang lebih mudah digunakan. Dalam kebanyakan kasus, cmdlet mencerminkan cmdlet yang ada dengan tepat. Namun, cmdlet eksperimental memberikan notasi singkat dan nilai default yang lebih cerdas yang membuatnya lebih mudah untuk membuat dan mengelola sumber daya Azure.

Modul-modul ini dapat diinstal berdampingan dengan modul Azure PowerShell yang ada. Nama cmdlet telah dipersingkat untuk memberikan nama yang lebih pendek dan menghindari konflik nama dengan cmdlet non-eksperimental yang ada.

Modul eksperimental menggunakan konvensi penamaan berikut: `AzureRM.*.Experiments`. Konvensi penamaan ini mirip dengan penamaan modul Pratinjau: `AzureRM.*.Preview`. Modul pratinjau berbeda dari modul eksperimental. Modul pratinjau menerapkan fungsionalitas baru layanan Azure yang hanya tersedia sebagai penawaran Pratinjau. Modul pratinjau menggantikan modul Azure PowerShell yang ada dan menggunakan cmdlet dan nama parameter yang sama.

## <a name="how-to-install-an-experimental-module"></a>Cara menginstal modul eksperimental

Modul eksperimental diterbitkan ke Galeri PowerShell seperti modul Azure PowerShell yang ada. Untuk melihat daftar modul eksperimental, jalankan perintah berikut:

```azurepowershell-interactive
Find-Module AzureRM.*.Experiments
```

```output
Version Name                         Repository Description
------- ----                         ---------- -----------
1.0.25  AzureRM.Compute.Experiments  PSGallery  Azure Compute experiments for VM creation
1.0.0   AzureRM.Websites.Experiments PSGallery  Create and deploy web applications using Azure App Services.
```

Untuk menginstal modul eksperimental, gunakan perintah berikut dari sesi PowerShell yang ditinggikan:

```azurepowershell-interactive
Install-Module AzureRM.Compute.Experiments
Install-Module AzureRM.Websites.Experiments
```

### <a name="documentation-and-support"></a>Dokumentasi dan dukungan

Dokumentasi disertakan dalam paket instal dan diakses menggunakan cmdlet `Get-Help`. Tidak ada dokumentasi resmi yang diterbitkan untuk modul eksperimental.

Kami mendorong Anda untuk menguji modul-modul ini. Umpan balik Anda memungkinkan kami meningkatkan kegunaan dan menanggapi kebutuhan Anda. Namun, karena eksperimental, dukungan untuk modul-modul ini terbatas. Pertanyaan atau laporan masalah dapat diajukan dengan membuat [masalah](https://github.com/Azure/azure-powershell/issues) di repositori GitHub.

## <a name="experiments-and-areas-of-improvement"></a>Eksperimen dan bidang perbaikan

Perbaikan ini dipilih berdasarkan pembeda utama dalam produk yang bersaing. Misalnya, Azure CLI 2.0 telah membuat titik mendasarkan perintah pada _skenario_ daripada _luas permukaan API_.
Azure CLI 2.0 menggunakan sejumlah default cerdas yang membuat skenario "memulai" lebih mudah bagi pengguna akhir.

### <a name="core-improvements"></a>Peningkatan inti

Perbaikan inti dianggap sebagai "akal sehat", dan sedikit eksperimen diperlukan untuk bergerak maju dalam menerapkan pembaruan ini.

- Cmdlet berbasis skenario - <em>*Semua</em>- cmdlet harus dirancang di sekitar skenario, bukan layanan Azure REST.

- Nama Yang Lebih Pendek - Termasuk nama cmdlet (misalnya, `New-AzureRmVM` => `New-AzVm`) dan nama parameter (misalnya, `-ResourceGroupName` => `-Rg`). Gunakan alias untuk kompatibilitas dengan cmdlet "lama". Menyediakan set parameter _yang kompatibel dengan versi sebelumnya_.

- Default Cerdas - Buat default cerdas untuk mengisi informasi "yang diperlukan". Contohnya:
  - Grup Sumber Daya
  - Lokasi
  - Sumber daya dependen

### <a name="experimental-improvements"></a>Perbaikan eksperimental

Perbaikan eksperimental menghadirkan perubahan signifikan yang ingin divalidasi oleh tim melalui eksperimen.

- Tipe sederhana - Buat skenario harus menjauh dari jenis kompleks dan objek konfigurasi. Sederhanakan konfigurasi menjadi satu atau dua parameter.

- "Smart Create" - Semua membuat skenario yang menerapkan "Smart Create" _tidak_ akan memiliki parameter yang diperlukan: semua informasi yang diperlukan akan dipilih oleh Azure PowerShell dengan cara yang berpendirian.

- Parameter Abu-abu - Dalam banyak kasus, beberapa parameter bisa "abu-abu" atau semi-opsional. Jika parameter tidak ditentukan, pengguna akan ditanya apakah mereka menginginkan parameter yang dihasilkan untuk mereka. Juga masuk akal bagi parameter abu-abu untuk menyimpulkan nilai berdasarkan konteks dengan persetujuan pengguna.
  Misalnya, mungkin masuk akal untuk memiliki parameter abu-abu yang menyarankan nilai yang paling baru digunakan.

- Pengalih `-Auto` - Pengalih `-Auto` akan memberikan cara "ikut serta" bagi pengguna untuk _default semua hal_ sambil menjaga integritas parameter yang diperlukan di jalur utama.

### <a name="feature-specific-switches"></a>Pengalih khusus fitur

Misalnya, skenario "Buat aplikasi web" mungkin memiliki pengalih `-Git` atau `-AddRemote` yang secara otomatis akan menambahkan remote "azure" ke repositori git yang ada.

- Default yang Dapat Diatur - Pengguna harus memiliki kemampuan untuk default parameter tertentu di mana-mana seperti `-ResourceGroupName` dan `-Location`.

- Default Ukuran - "Ukuran" sumber daya dapat membingungkan pengguna karena banyak Penyedia Sumber Daya menggunakan nama yang berbeda (misalnya, "Standard\_DS1\_v2" atau "S1"). Namun, sebagian besar pengguna lebih peduli tentang biaya. Oleh karena itu, masuk akal untuk menentukan ukuran "universal" berdasarkan jadwal penetapan harga. Pengguna dapat memilih ukuran tertentu atau membiarkan Azure PowerShell memilih _opsi terbaik_ berdasarkan sumber daya anggaran.

- Format Output - Azure PowerShell saat ini mengembalikan `PSObject` dan ada sedikit output konsol. Azure PowerShell mungkin perlu menampilkan beberapa informasi kepada pengguna mengenai "default cerdas" yang digunakan.
