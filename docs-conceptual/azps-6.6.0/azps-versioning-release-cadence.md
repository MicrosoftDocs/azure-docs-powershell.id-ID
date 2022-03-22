---
description: Anda ini berisi penerapan versi Azure PowerShell dan informasi rangkaian rilis untuk modul Az PowerShell.
ms.custom: devx-track-azurepowershell
ms.date: 02/08/2022
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
title: Penerapan versi modul Azure PowerShell dan rangkaian rilis
ms.openlocfilehash: 5f8da4947a76cda776a6df0457bbc46e8976e43f
ms.sourcegitcommit: b29dc53214e2018b30326c37fe98585658629e62
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 02/19/2022
ms.locfileid: "139129380"
---
# <a name="azure-powershell-module-versioning-and-release-cadence"></a>Penerapan versi modul Azure PowerShell dan rangkaian rilis

Modul Az PowerShell adalah modul rollup yang berisi lebih dari tujuh puluh modul layanan yang tersedia secara umum (GA) atau stabil untuk mengelola sumber daya Azure langsung dari PowerShell.

## <a name="versioning"></a>Versi

Modul Az PowerShell mengikuti [Penerapan Versi Skematis](https://semver.org/) untuk penomoran versi.
Versi modul layanan Azure tercakup dalam salah satu dari tiga kategori:

- Tersedia secara umum. Versi modul 1.0.0 dan lebih tinggi tanpa _pratinjau_ dalam versi. Mematuhi kebijakan perubahan pemecahan.
- Pratinjau. Modul lebih rendah dari versi 1.0.0. Tidak mematuhi kebijakan perubahan pemecahan.
- Pratinjau fitur. Versi modul 1.0.0 dan lebih tinggi dengan _pratinjau_ dalam versi. Tidak mematuhi kebijakan perubahan pemecahan.

Terdapat dua modul rollup Az PowerShell:

- [Az](https://www.powershellgallery.com/packages/Az/). Menginstal semua modul layanan GA untuk mengelola sumber daya Azure.
- [AzPreview](https://www.powershellgallery.com/packages/AzPreview/). Menginstal semua modul GA dan pratinjau untuk mengelola sumber daya Azure. Tidak menyertakan modul pratinjau fitur.

Versi modul AzPreview selalu berupa versi yang sama dan dirilis di waktu yang sama dengan modul Az.

## <a name="release-cadence"></a>Rangkaian rilis

Pembaruan terencana untuk modul Az PowerShell dirilis pada hari Selasa pertama setiap bulan. Kedua belas pembaruan terencana per tahun kalender ini dibagi menjadi dua kategori:

- Versi utama. Tidak lebih dari dua per tahun kalender yang memperkenalkan perubahan pemecahan. Nomor pertama dalam nomor versi diperbarui. Misalnya, versi 6.6.0 menjadi versi 7.0.0.
- Versi minor. Sepuluh per tahun kalender yang tidak memperkenalkan perubahan pemecahan. Nomor kedua dalam nomor versi diperbarui. Misalnya, versi 7.0.0 menjadi versi 7.1.0.

> [!WARNING]
> Sebelum memutakhirkan ke versi perubahan pemecahan utama dari modul Az PowerShell, Anda harus [**meninjau panduan migrasi**](https://aka.ms/azps-migration-latest).

Versi patch tak terencana dapat dirilis kapan saja untuk memperbaiki bug. Versi patch tidak memperkenalkan perubahan pemecahan. Nomor ketiga dalam nomor versi diperbarui. Misalnya, versi 6.2.0 menjadi versi 6.2.1.

> [!IMPORTANT]
> Perubahan pemecahan dapat terjadi kapan saja untuk modul pratinjau non-GA dan pratinjau fitur. Modul non-GA tidak diperlukan untuk mematuhi kebijakan perubahan pemecahan.

## <a name="additional-resources"></a>Sumber Daya Tambahan:

- [Modul Azure PowerShell](https://github.com/Azure/azure-powershell/blob/main/documentation/azure-powershell-modules.md).
- [Siklus Hidup Dukungan Azure PowerShell](azureps-support-lifecycle.md)
- [Rilis Azure PowerShell terdemistifikasi](https://techcommunity.microsoft.com/t5/azure-tools-blog/azure-powershell-releases-demystified/ba-p/1609863)
