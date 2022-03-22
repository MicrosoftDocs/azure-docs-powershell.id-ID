---
title: Siklus hidup dukungan Azure PowerShell
description: Detail tentang siklus hidup dukungan modul Azure PowerShell
ms.devlang: powershell
ms.topic: conceptual
ms.date: 09/29/2021
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
ms.openlocfilehash: be9a9839e04fba0898a335ce8ec58b08f65d7e0d
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 11/02/2021
ms.locfileid: "132429455"
---
# <a name="azure-powershell-support-lifecycle"></a>Siklus Hidup Dukungan Azure PowerShell

## <a name="az-powershell-modules"></a>Modul Az PowerShell

_"Modul Az PowerShell"_ terdiri dari modul bernama _"Az"_ dan modul dependen yang ditandatangani oleh _"Microsoft Corporation"_ . Modul Az PowerShell dapat diidentifikasi dengan nama modul, yang dimulai dengan _"Az."_ . Untuk daftar modul Az PowerShell saat ini, lihat [Modul Azure PowerShell](https://github.com/Azure/azure-powershell/blob/master/documentation/azure-powershell-modules.md).

Siklus hidup dukungan modul Az PowerShell termasuk dalam [kebijakan siklus hidup Azure SDK](https://support.microsoft.com/help/18486). Kami mendukung dua versi minor terakhir dari versi utama saat ini dan versi minor terakhir dari versi utama sebelumnya modul Az PowerShell.

## <a name="azurerm-powershell-modules"></a>Modul AzureRM PowerShell

Karena modul Az PowerShell sekarang memiliki semua kemampuan modul AzureRM PowerShell dan lebih banyak lagi, kami akan menghentikan modul AzureRM PowerShell pada 29 Februari 2024.

Untuk menghindari gangguan layanan, [perbarui skrip Anda](https://aka.ms/azpsmigrate) yang menggunakan modul AzureRM PowerShell untuk menggunakan modul Az PowerShell paling lambat 29 Februari 2024. Untuk memperbarui skrip Anda secara otomatis, ikuti [panduan memulai cepat](/powershell/azure/quickstart-migrate-azurerm-to-az-automatically).

## <a name="supported-environments"></a>Lingkungan yang didukung

Tabel berikut mengidentifikasi platform yang didukung untuk modul Az, AzureRM, dan Azure PowerShell.

|        Az        | PowerShell <br/> 7.1.3 | PowerShell <br/> >= 7.0.6 | PowerShell <br/> <= 7.0.5 | Windows PowerShell <br/> 5.1 |
| :--------------: | :--------------------: | :-----------------------: | :-----------------------: | :--------------------------: |
|      Az 6.x      |       Didukung        |         Didukung         |       Tidak didukung       |          Didukung           |
|      Az 5.9      |       Didukung        |         Didukung         |         Didukung         |          Didukung           |
| AzureRM (6.13.2) |     Tidak Didukung      |       Tidak Didukung       |       Tidak Didukung       |          Didukung           |
|  Azure (5.3.1)   |     Tidak Didukung      |       Tidak Didukung       |       Tidak Didukung       |          Didukung           |

> [!NOTE]
> PowerShell 6.2 telah mencapai akhir masa pakainya pada tanggal 4 September 2020. Modul Az PowerShell tidak didukung pada versi PowerShell 6 mana pun.

### <a name="information-about-cve-2021-26701"></a>Informasi tentang CVE-2021-26701

Modul Az PowerShell menggunakan komponen yang dipengaruhi oleh penasihat keamanan [CVE-2021-26701](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-26701) yang telah diperbaiki di PowerShell 7.0.6 dan 7.1.3. Untuk informasi selengkapnya, lihat [Microsoft Security Advisory CVE-2021-26701: .NET Core Remote Code Execution Vulnerability](https://github.com/PowerShell/Announcements/issues/23).

Dimulai dengan Az 6.0.0, PowerShell 7.0.6 atau 7.1.3 atau yang lebih baru diperlukan. Saat modul Az.Accounts diimpor, pesan non-pemblokiran berikut akan ditampilkan jika versi PowerShell yang tidak didukung sedang digunakan: _"Versi Az.Accounts ini hanya didukung di Windows PowerShell 5.1 dan PowerShell 7.0.6 atau lebih tinggi, buka [https://aka.ms/install-powershell](https://aka.ms/install-powershell) untuk mempelajari cara meningkatkan. Untuk informasi lebih lanjut, kunjungi [https://aka.ms/azpslifecyle](https://aka.ms/azpslifecycle)."_
