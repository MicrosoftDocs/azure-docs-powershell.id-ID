---
description: Artikel ini berisi Azure PowerShell versi dan rilis informasi irama untuk modul Az PowerShell.
ms.custom: devx-track-azurepowershell
ms.date: 02/08/2022
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
title: Azure PowerShell versi modul dan irama rilis
ms.openlocfilehash: 5f8da4947a76cda776a6df0457bbc46e8976e43f
ms.sourcegitcommit: cdca0d3199eb118c98aafb63ffcacc3dd080f0d4
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/16/2022
ms.locfileid: "138855243"
---
# <a name="azure-powershell-module-versioning-and-release-cadence"></a>Azure PowerShell versi modul dan irama rilis

Modul Az PowerShell adalah modul rollup yang berisi lebih dari tujuh puluh modul layanan yang tersedia secara umum (GA) atau stabil untuk mengelola sumber daya Azure langsung dari PowerShell.

## <a name="versioning"></a>Penerapan versi

Modul Az PowerShell mengikuti [Semantic Versioning](https://semver.org/) untuk penomolan versi.
Versi modul layanan Azure termasuk dalam salah satu dari tiga kategori:

- Tersedia secara umum. Modul versi 1.0.0 dan lebih tinggi tanpa _pratinjau_ dalam versi. Mematuhi kebijakan perubahan yang melanggar.
- Pratinjau. Modul kurang dari versi 1.0.0. Jangan mematuhi kebijakan perubahan yang melanggar.
- Pratinjau fitur. Modul versi 1.0.0 dan lebih tinggi dengan _pratinjau_ dalam versi. Jangan mematuhi kebijakan perubahan yang melanggar.

Ada dua modul rollup Az PowerShell:

- [Az](https://www.powershellgallery.com/packages/Az/). Menginstal semua modul layanan GA untuk mengelola sumber daya Azure.
- [AzPreview](https://www.powershellgallery.com/packages/AzPreview/). Menginstal semua modul GA dan pratinjau untuk mengelola sumber daya Azure. Tidak termasuk modul pratinjau fitur.

Versi modul AzPreview selalu versi yang sama dan dirilis pada saat yang sama dengan modul Az.

## <a name="release-cadence"></a>Melepaskan irama

Pembaruan yang direncanakan untuk modul Az PowerShell dirilis pada hari Selasa pertama setiap bulan. Dua belas pembaruan yang direncanakan per tahun kalender ini dipecah menjadi dua kategori:

- Versi utama. Tidak lebih dari dua per tahun kalender yang memperkenalkan perubahan yang melanggar. Nomor pertama di nomor versi diperbarui. Misalnya, versi 6.6.0 hingga versi 7.0.0.
- Versi minor. Sepuluh per tahun kalender yang tidak memperkenalkan perubahan yang melanggar. Nomor kedua dalam nomor versi diperbarui. Misalnya, versi 7.0.0 hingga versi 7.1.0.

> [!WARNING]
> Sebelum meningkatkan ke versi perubahan besar dari modul Az PowerShell, Anda harus [**meninjau panduan migrasi**](https://aka.ms/azps-migration-latest).

Versi patch yang tidak direncanakan dapat dirilis kapan saja untuk memperbaiki bug. Versi patch tidak memperkenalkan perubahan yang melanggar. Nomor ketiga dalam nomor versi diperbarui. Misalnya, versi 6.2.0 hingga versi 6.2.1.

> [!IMPORTANT]
> Melanggar perubahan dapat terjadi kapan saja untuk pratinjau non-GA dan modul pratinjau fitur. Modul non-GA tidak diharuskan mematuhi kebijakan perubahan yang melanggar.

## <a name="additional-resources"></a>Sumber Daya Tambahan:

- [Modul Azure PowerShell](https://github.com/Azure/azure-powershell/blob/main/documentation/azure-powershell-modules.md).
- [Siklus Hidup Dukungan Azure PowerShell](azureps-support-lifecycle.md)
- [Azure PowerShell melepaskan demystified](https://techcommunity.microsoft.com/t5/azure-tools-blog/azure-powershell-releases-demystified/ba-p/1609863)
