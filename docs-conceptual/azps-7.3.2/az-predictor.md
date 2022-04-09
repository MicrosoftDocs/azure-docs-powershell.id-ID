---
description: Menggunakan Az Predictor untuk penyelesaian perintah sadar konteks cerdas di Azure PowerShell.
ms.custom: devx-track-azurepowershell
ms.date: 03/31/2022
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
title: Penyelesaian perintah sadar konteks cerdas dengan Az Predictor
ms.openlocfilehash: d544060c0c3ebdc3de63648d59fd828d02cd21cf
ms.sourcegitcommit: e56147b0ee15241ea300caf0d3699405fde2f731
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/01/2022
ms.locfileid: "141333208"
---
# <a name="intelligent-context-aware-command-completion-with-az-predictor"></a>Penyelesaian perintah sadar konteks cerdas dengan Az Predictor

## <a name="overview"></a>Gambaran Umum

[Az Predictor](https://www.powershellgallery.com/packages/Az.Tools.Predictor/) adalah modul PowerShell yang membantu Anda menavigasi cmdlet dan parameter [modul Az PowerShell](https://www.powershellgallery.com/packages/Az). Ini memberikan saran sadar konteks cerdas untuk penyelesaian perintah saat menggunakan Azure PowerShell.

Az Predictor menggunakan [model plugin subsistem yang](/powershell/scripting/learn/experimental-features#pssubsystempluginmodel) tersedia di PowerShell 7.2. Versi yang diperbarui ini memerlukan [PSReadLine 2.2.2](https://www.powershellgallery.com/packages/PSReadLine/2.2.2) atau lebih tinggi untuk menampilkan saran.

## <a name="requirements"></a>Persyaratan

Konfigurasi yang diperlukan untuk Az Predictor:

- [PowerShell 7.2](https://github.com/PowerShell/PowerShell/) atau lebih tinggi
- [PSReadline 2.2.2](https://github.com/PowerShell/PSReadLine/) atau lebih tinggi

Instal versi terbaru PSReadLine:

```powershell
Install-Module -Name PSReadline
```

## <a name="getting-started"></a>Memulai

### <a name="install-az-predictor"></a>Install Az Predictor

Instal modul Az.Tools.Predictor PowerShell

```powershell
Install-Module -Name Az.Tools.Predictor
```

### <a name="enable-az-predictor"></a>Enable Az Predictor

1. Aktifkan Prediktor Az untuk sesi PowerShell saat ini dan masa mendatang.

   ```powershell
   Enable-AzPredictor -AllSession
   ```

1. Atur tampilan pilihan Anda untuk saran.

   Aktifkan tampilan daftar:

   ```powershell
   Set-PSReadLineOption -PredictionViewStyle ListView
   ```

   Aktifkan tampilan sebaris:

   ```powershell
   Set-PSReadLineOption -PredictionViewStyle InlineView
   ```

> [!NOTE]
> Anda dapat beralih antara mode tampilan dengan tombol <kbd>F2</kbd> .

## <a name="uninstallation"></a>Hapus instalasi

Setelah diinstal dan diaktifkan, Az Predictor dimuat di profil PowerShell.
Untuk menghapus instalan modul Az.Tools.Predictor:

1. Tutup **semua** sesi PowerShell termasuk VS Code.

1. Luncurkan sesi PowerShell tanpa profil.

   ```powershell
   pwsh -noprofile
   ```

1. Uninstall Az Predictor

   ```powershell
   Uninstall-Module -Name Az.Tools.Predictor -Force
   ```

1. Tutup PowerShell

## <a name="privacy-and-data-collection"></a>Privasi dan pengumpulan data

### <a name="privacy"></a>Privasi

Prediktor Az menggunakan dua cmdlet Az sebelumnya untuk membuat saran dan mengabaikan cmdlet apa pun yang bukan bagian dari modul [Az PowerShell](https://www.powershellgallery.com/packages/Az) . Hanya nama cmdlet dan parameter yang dikirim ke API kami untuk mendapatkan saran. Nilai parameter dibuang.
Nama grup sumber daya dan lokasi yang digunakan disimpan secara lokal dan digunakan kembali dengan cmdlet berikutnya untuk kenyamanan tetapi tidak pernah dikirim ke API. Dalam versi pratinjau, modul menghasilkan dan mengirimkan informasi anonim tentang sesi saat ini yang digunakan untuk prediksi ke API. Informasi ini digunakan untuk menilai kualitas saran.

### <a name="data-collection"></a>Kumpulan data

Versi Az Predictor saat ini mengumpulkan informasi anonim tentang penggunaannya untuk mengidentifikasi masalah umum dan meningkatkan pengalaman rilis di masa mendatang. Az Predictor tidak mengumpulkan data pribadi atau pribadi apa pun.

Misalnya, data penggunaan membantu mengidentifikasi saran dan masalah yang tidak akurat seperti gangguan dengan PSReadLine. Meskipun kami menghargai wawasan yang diberikan data ini, kami memahami tidak semua orang ingin mengirim data penggunaan. Anda dapat menonaktifkan pengumpulan data dengan cmdlet [Disable-AzDataCollection](/powershell/module/az.accounts/disable-azdatacollection) . Anda juga dapat membaca [pernyataan privasi](https://go.microsoft.com/fwlink/?LinkID=528096&clcid=0x409) kami untuk mempelajari lebih lanjut.
