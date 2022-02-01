---
title: Azure PowerShell versi modul dan pelepasan irama
description: Artikel ini berisi Azure PowerShell versi dan rilis informasi irama untuk modul Az PowerShell.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 01/31/2022
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
ms.openlocfilehash: 72397b3ed28426b99ff1ef300ed58c9a501f4494
ms.sourcegitcommit: 00a2bdaf41dfa3e1d97339ec08bccc1bc4220bc3
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/01/2022
ms.locfileid: "137915675"
---
# <a name="azure-powershell-module-versioning-and-release-cadence"></a>Azure PowerShell versi modul dan pelepasan irama

Modul Az PowerShell adalah modul rollup yang berisi lebih dari tujuh puluh modul layanan yang tersedia secara umum (GA) atau stabil untuk mengelola sumber daya Azure langsung dari PowerShell.

## <a name="versioning"></a>Penerapan versi

Modul Az PowerShell mengikuti [Semantic Versioning](https://semver.org/) untuk penomoan versi.
Versi modul layanan Azure termasuk dalam salah satu dari tiga kategori:

- Tersedia secara umum. Modul versi 1.0.0 dan lebih tinggi tanpa _pratinjau_ dalam versi. Mematuhi melanggar kebijakan perubahan.
- Pratinjau. Modul kurang dari versi 1.0.0. Jangan mematuhi melanggar kebijakan perubahan.
- Pratinjau fitur. Modul versi 1.0.0 dan lebih tinggi dengan _pratinjau_ dalam versi. Jangan mematuhi melanggar kebijakan perubahan.

Ada dua modul rollup Az PowerShell:

- [Az](https://www.powershellgallery.com/packages/Az/). Menginstal semua modul layanan GA untuk mengelola sumber daya Azure.
- [AzPreview](https://www.powershellgallery.com/packages/AzPreview/). Menginstal semua modul GA dan pratinjau untuk mengelola sumber daya Azure. Tidak termasuk modul pratinjau fitur.

Versi modul AzPreview selalu versi yang sama dan dirilis pada saat yang sama dengan modul Az.

## <a name="release-cadence"></a>Lepaskan irama

Pembaruan yang direncanakan untuk modul Az PowerShell dirilis pada hari Selasa pertama setiap bulan. Dua belas pembaruan yang direncanakan per tahun kalender ini dipecah menjadi dua kategori:

- Versi utama. Tidak lebih dari dua per tahun kalender yang memperkenalkan perubahan yang melanggar. Nomor pertama dalam nomor versi diperbarui. Misalnya, versi 6.6.0 ke versi 7.0.0.
- Versi minor. Sepuluh per tahun kalender yang tidak memperkenalkan perubahan melanggar. Nomor kedua dalam nomor versi diperbarui. Misalnya, versi 7.0.0 ke versi 7.1.0.

> [!WARNING]
> Sebelum memutakhirkan ke versi perubahan besar modul Az PowerShell, Anda harus [**meninjau panduan migrasi**](https://aka.ms/azps-migration-latest).

Versi patch yang tidak direncanakan dapat dirilis kapan saja untuk memperbaiki bug. Versi patch tidak memperkenalkan perubahan yang melanggar. Nomor ketiga dalam nomor versi diperbarui. Misalnya, versi 6.2.0 ke versi 6.2.1.

> [!IMPORTANT]
> Melanggar perubahan dapat terjadi pada setiap titik untuk preview non-GA dan fitur modul preview. Modul non-GA tidak diharuskan untuk mematuhi kebijakan perubahan yang melanggar.

## <a name="additional-resources"></a>Sumber Daya Tambahan:

- [Modul Azure PowerShell](https://github.com/Azure/azure-powershell/blob/main/documentation/azure-powershell-modules.md).
- [siklus hidup dukungan Azure PowerShell](azureps-support-lifecycle.md)
- [Azure PowerShell rilis demystified](https://techcommunity.microsoft.com/t5/azure-tools-blog/azure-powershell-releases-demystified/ba-p/1609863)
