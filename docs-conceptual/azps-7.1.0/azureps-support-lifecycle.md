---
title: Azure PowerShell hidup dukungan
description: Detail tentang siklus hidup dukungan modul Azure PowerShell baru
ms.devlang: powershell
ms.topic: conceptual
ms.date: 01/04/2022
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
ms.openlocfilehash: d68081b063d8a0a97133bec71dae3c9a1ae3c326
ms.sourcegitcommit: e109cc5320478db6aa8a52d49996b133007a65b9
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 01/12/2022
ms.locfileid: "135958429"
---
# <a name="azure-powershell-support-lifecycle"></a>Azure PowerShell Siklus Hidup Dukungan

## <a name="az-powershell-modules"></a>Modul Az PowerShell

"Modul _Az PowerShell"_ terdiri dari modul bernama _"Az"_ dan modul dependen yang ditandatangani oleh _"Microsoft Corporation"_. Modul Az PowerShell diidentifikasi dengan namanya, yang dimulai dengan _"Az."_. Untuk daftar modul Az PowerShell saat ini, lihat [Azure PowerShell Modul](https://github.com/Azure/azure-powershell/blob/master/documentation/azure-powershell-modules.md).

Siklus hidup dukungan modul Az PowerShell berada di bawah [kebijakan siklus hidup Azure SDK](https://support.microsoft.com/help/18486). Kami mendukung dua versi minor terakhir dari versi utama saat ini dan versi minor terakhir dari modul Az PowerShell versi utama sebelumnya.

## <a name="azurerm-powershell-modules"></a>Modul PowerShell AzureRM

Karena modul PowerShell Az kini memiliki semua kapabilitas modul PowerShell AzureRM dan lainnya, kami akan menghentikan modul PowerShell AzureRM pada 29 Februari 2024.

Untuk menghindari gangguan [layanan,](https://aka.ms/azpsmigrate) perbarui skrip Anda yang menggunakan modul PowerShell AzureRM untuk menggunakan modul Az PowerShell sebelum 29 Februari 2024. Untuk memperbarui skrip secara otomatis, ikuti [panduan mulai cepat](/powershell/azure/quickstart-migrate-azurerm-to-az-automatically).

## <a name="supported-environments"></a>Lingkungan yang didukung

Tabel berikut mengidentifikasi platform yang didukung untuk Az, AzureRM, dan Azure PowerShell modul.

|        Az        | PowerShell <br/> 7.1.3 | PowerShell <br/> >= 7,0,6 | PowerShell <br/> <= 7,0,5 | Windows PowerShell <br/> 5.1 |
| :--------------: | :--------------------: | :-----------------------: | :-----------------------: | :--------------------------: |
|      Az 7.x      |       Didukung        |         Didukung         |       Tidak didukung       |          Didukung           |
|      Az 6.x      |       Didukung        |         Didukung         |       Tidak didukung       |          Didukung           |
| AzureRM (6.13.2) |     Tidak Didukung      |       Tidak Didukung       |       Tidak Didukung       |          Didukung           |
|  Azure (5.3.1)   |     Tidak Didukung      |       Tidak Didukung       |       Tidak Didukung       |          Didukung           |

> [!NOTE]
> PowerShell 6.2 telah mencapai masa berakhirnya mulai 4 September 2020. Modul Az PowerShell tidak didukung di versi PowerShell 6 apa pun.

### <a name="information-about-cve-2021-26701"></a>Informasi tentang ESCUDO-2021-26701

Modul Az PowerShell menggunakan komponen yang terkena dampak saran keamanan [MODULE-2021-26701](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-26701) yang telah diperbaiki di PowerShell 7.0.6 dan 7.1.3. Untuk informasi selengkapnya, lihat [Microsoft Security Advisory VBA-2021-26701: .NET Core Remote Code Execution Vulnerability](https://github.com/PowerShell/Announcements/issues/23).

Dimulai dengan Az 6.0.0, PowerShell 7.0.6 atau 7.1.3 atau lebih baru diperlukan. Saat modul Az.Accounts diimpor, pesan tidak memblokir berikut ini akan ditampilkan jika versi PowerShell yang tidak didukung sedang digunakan: "Versi Az.Accounts ini hanya didukung di _Windows PowerShell 5.1 dan PowerShell 7.0.6 atau yang lebih besar, buka untuk mempelajari cara [https://aka.ms/install-powershell](https://aka.ms/install-powershell) memutakhirkan. Untuk informasi lebih lanjut, buka [https://aka.ms/azpslifecyle](https://aka.ms/azpslifecycle) ."_
