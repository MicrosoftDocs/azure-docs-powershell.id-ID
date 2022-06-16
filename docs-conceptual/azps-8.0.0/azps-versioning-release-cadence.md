---
title: Azure PowerShell penerapan versi, irama rilis, dan perubahan yang melanggar
description: Artikel ini berisi Azure PowerShell informasi penerapan versi, irama rilis, dan perubahan yang melanggar untuk modul Az PowerShell.
ms.date: 06/14/2022
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
ms.custom: devx-track-azurepowershell
ms.openlocfilehash: 7a57273b8f573b4c2af8ee9b7aaa05bde2bb099b
ms.sourcegitcommit: 220709c859dac8c91c29ab8fd79e61bae2c8cc34
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/15/2022
ms.locfileid: "146383453"
---
# <a name="azure-powershell-versioning-release-cadence-and-breaking-changes"></a>Azure PowerShell penerapan versi, irama rilis, dan perubahan yang melanggar

Modul Az PowerShell adalah modul rollup yang berisi lebih dari 70 modul layanan yang tersedia secara umum (GA) atau stabil untuk mengelola sumber daya Azure langsung dari PowerShell.

## <a name="versioning"></a>Versi

Modul Az PowerShell mengikuti [Penerapan Versi Skematis](https://semver.org/) untuk penomoran versi.
Versi modul layanan Azure tercakup dalam salah satu dari tiga kategori:

- Tersedia secara umum. Versi modul 1.0.0 dan lebih tinggi tanpa _pratinjau_ dalam versi. Mematuhi kebijakan perubahan pemecahan.
- Pratinjau. Modul lebih rendah dari versi 1.0.0. Jangan mematuhi kebijakan perubahan yang melanggar.
- Pratinjau fitur. Versi modul 1.0.0 dan lebih tinggi dengan _pratinjau_ dalam versi. Jangan mematuhi kebijakan perubahan yang melanggar.

Terdapat dua modul rollup Az PowerShell:

- [Az](https://www.powershellgallery.com/packages/Az/). Menginstal semua modul layanan GA untuk mengelola sumber daya Azure.
- [AzPreview](https://www.powershellgallery.com/packages/AzPreview/). Menginstal semua modul GA dan pratinjau untuk mengelola sumber daya Azure. Tidak menyertakan modul pratinjau fitur.

Versi modul AzPreview selalu berupa versi yang sama dan dirilis di waktu yang sama dengan modul Az.

## <a name="release-cadence"></a>Rangkaian rilis

Pembaruan terencana untuk modul Az PowerShell dirilis pada hari Selasa pertama setiap bulan. 12 pembaruan yang direncanakan per tahun kalender ini berada dalam dua kategori:

- Versi utama. Paling banyak, dua per tahun kalender yang memperkenalkan perubahan yang melanggar. Nomor pertama dalam nomor versi diperbarui. Misalnya, versi 6.6.0 menjadi versi 7.0.0.
- Versi minor. 10 per tahun kalender yang tidak memperkenalkan perubahan yang melanggar. Nomor kedua dalam nomor versi diperbarui. Misalnya, versi 7.0.0 menjadi versi 7.1.0.

> [!WARNING]
> Sebelum memutakhirkan ke versi perubahan pemecahan utama dari modul Az PowerShell, Anda harus [**meninjau panduan migrasi**](https://aka.ms/azps-migration-latest).

Versi patch tak terencana dapat dirilis kapan saja untuk memperbaiki bug. Versi patch tidak memperkenalkan perubahan yang melanggar. Nomor ketiga dalam nomor versi diperbarui. Misalnya, versi 6.2.0 menjadi versi 6.2.1.

## <a name="breaking-changes"></a>Perubahan mencolok

> [!IMPORTANT]
> Perubahan pemecahan dapat terjadi kapan saja untuk modul pratinjau non-GA dan pratinjau fitur. Modul non-GA tidak diperlukan untuk mematuhi kebijakan perubahan pemecahan.

### <a name="breaking-change-warning-messages"></a>Melanggar pesan peringatan perubahan

Melanggar pesan peringatan perubahan adalah cara bagi penulis cmdlet Azure PowerShell untuk mengomunikasikan perubahan yang melanggar yang akan datang dengan pengguna akhir.

### <a name="suppress-breaking-change-warning-messages"></a>Sembunyikan pesan peringatan perubahan pemutusan

Untuk menekan melanggar perubahan pesan peringatan, lihat [Bagaimana cara menonaktifkan melanggar perubahan pesan peringatan di Azure PowerShell?](/powershell/azure/faq#how-do-i-disable-breaking-change-warning-messages-in-azure-powershell-).

Untuk informasi selengkapnya, lihat [Bantuan Atribut Breaking Changes](https://github.com/Azure/azure-powershell/blob/preview/documentation/breaking-changes/breaking-changes-attribute-help.md#supress-the-breaking-change-messages-at-runtime).

### <a name="when-do-breaking-changes-occur"></a>Kapan perubahan mencolok terjadi

Kami merilis dua versi perubahan yang melanggar per tahun:

- Satu di akhir musim semi
- Satu di musim gugur

Untuk informasi tentang rilis perubahan yang melanggar yang akan datang, lihat [Azure PowerShell pencapaian](https://github.com/Azure/azure-powershell/milestones).

### <a name="types-of-breaking-changes"></a>Jenis perubahan disruptif

Berbagai jenis perubahan yang melanggar dapat terjadi dalam cmdlet. Untuk informasi selengkapnya, lihat [Melanggar Definisi Perubahan](https://github.com/Azure/azure-powershell/blob/preview/documentation/breaking-changes/breaking-changes-definition.md).

## <a name="provide-feedback"></a>Berikan umpan balik

- Untuk umpan balik umum, gunakan [`Send-Feedback`](/powershell/module/azurerm.profile/send-feedback) cmdlet .
- Untuk masalah produk, catat [masalah di repositori GitHub azure-powershell](https://github.com/Azure/azure-powershell/issues).

## <a name="other-resources"></a>Sumber daya lainnya

- [Modul Azure PowerShell](https://github.com/Azure/azure-powershell/blob/main/documentation/azure-powershell-modules.md).
- [Siklus Hidup Dukungan Azure PowerShell](azureps-support-lifecycle.md)
- [Rilis Azure PowerShell terdemistifikasi](https://techcommunity.microsoft.com/t5/azure-tools-blog/azure-powershell-releases-demystified/ba-p/1609863)
