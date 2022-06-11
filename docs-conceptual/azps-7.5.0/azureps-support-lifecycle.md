---
description: Detail tentang siklus hidup dukungan modul Azure PowerShell
ms.custom: devx-track-azurepowershell
ms.date: 06/09/2022
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
title: Siklus hidup dukungan Azure PowerShell
ms.openlocfilehash: 85b99a50b52eab0914dbd809509c9d87e8d90aef
ms.sourcegitcommit: 37440f9593703a5e400f8052b026691982899953
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/11/2022
ms.locfileid: "146259703"
---
# <a name="azure-powershell-support-lifecycle"></a>Siklus Hidup Dukungan Azure PowerShell

## <a name="az-powershell-modules"></a>Modul Az PowerShell

_"Modul Az PowerShell"_ terdiri dari modul bernama _"Az"_ dan modul dependen yang ditandatangani oleh _"Microsoft Corporation"_ . Modul Az PowerShell dapat diidentifikasi dengan nama modul, yang dimulai dengan _"Az."_ . Untuk daftar modul Az PowerShell saat ini, lihat [Modul Azure PowerShell](https://github.com/Azure/azure-powershell/blob/master/documentation/azure-powershell-modules.md).

Siklus hidup dukungan modul Az PowerShell termasuk dalam [kebijakan siklus hidup Azure SDK](https://support.microsoft.com/help/18486). Kami mendukung dua versi minor terakhir dari versi utama saat ini dan versi minor terakhir dari versi utama sebelumnya modul Az PowerShell.

## <a name="azurerm-powershell-modules"></a>Modul AzureRM PowerShell

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

Untuk menghindari gangguan layanan, [perbarui skrip Anda](https://aka.ms/azpsmigrate) yang menggunakan modul AzureRM PowerShell untuk menggunakan modul Az PowerShell paling lambat 29 Februari 2024. Untuk memperbarui skrip Anda secara otomatis, ikuti [panduan memulai cepat](/powershell/azure/quickstart-migrate-azurerm-to-az-automatically).

## <a name="supported-environments"></a>Lingkungan yang didukung

Tabel berikut mengidentifikasi platform yang didukung untuk modul Az, AzureRM, dan Azure PowerShell.

|        Az        | PowerShell <br/> 7.1.3 | PowerShell <br/> >= 7.0.6 | PowerShell <br/> <= 7.0.5 | Windows PowerShell <br/> 5.1 |
| :--------------: | :--------------------: | :-----------------------: | :-----------------------: | :--------------------------: |
|      Az 8.x      |       Didukung        |         Didukung         |       Tidak didukung       |          Didukung           |
|      Az 7.x      |       Didukung        |         Didukung         |       Tidak didukung       |          Didukung           |
|      Az 6.x      |     Tidak didukung      |       Tidak didukung       |       Tidak didukung       |        Tidak didukung         |
| AzureRM (6.13.2) |     Tidak Didukung      |       Tidak Didukung       |       Tidak Didukung       |          Didukung           |
|  Azure (5.3.1)   |     Tidak Didukung      |       Tidak Didukung       |       Tidak Didukung       |          Didukung           |

> [!NOTE]
> PowerShell 6.2 telah mencapai akhir masa pakainya pada tanggal 4 September 2020. Modul Az PowerShell tidak didukung pada versi PowerShell 6 mana pun.

### <a name="information-about-cve-2021-26701"></a>Informasi tentang CVE-2021-26701

Modul Az PowerShell menggunakan komponen yang dipengaruhi oleh penasihat keamanan [CVE-2021-26701](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-26701) yang telah diperbaiki di PowerShell 7.0.6 dan 7.1.3. Untuk informasi selengkapnya, lihat [Microsoft Security Advisory CVE-2021-26701: .NET Core Remote Code Execution Vulnerability](https://github.com/PowerShell/Announcements/issues/23).

Dimulai dengan Az 6.0.0, PowerShell 7.0.6 atau 7.1.3 atau yang lebih baru diperlukan. Saat modul Az.Accounts diimpor, pesan non-pemblokiran berikut ditampilkan jika versi PowerShell yang tidak didukung sedang digunakan: _"Versi Az.Accounts ini hanya didukung pada Windows PowerShell 5.1 dan PowerShell 7.0.6 atau yang lebih baru, buka [https://aka.ms/install-powershell](https://aka.ms/install-powershell) untuk mempelajari cara meningkatkan. Untuk informasi lebih lanjut, buka [https://aka.ms/azpslifecyle](https://aka.ms/azpslifecycle)."_
