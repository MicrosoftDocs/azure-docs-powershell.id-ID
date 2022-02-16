---
description: Detail tentang siklus hidup dukungan modul Azure PowerShell
ms.custom: devx-track-azurepowershell
ms.date: 02/08/2022
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
title: Azure PowerShell mendukung siklus hidup
ms.openlocfilehash: 79b27197c5906532dadfe9bd0a21ffef7644cc01
ms.sourcegitcommit: cdca0d3199eb118c98aafb63ffcacc3dd080f0d4
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/16/2022
ms.locfileid: "138855675"
---
# <a name="azure-powershell-support-lifecycle"></a>Siklus Hidup Dukungan Azure PowerShell

## <a name="az-powershell-modules"></a>Modul Az PowerShell

_"Modul Az PowerShell"_ terdiri dari modul bernama _"Az"_ dan modul dependen yang ditandatangani oleh _"Microsoft Corporation"_. Modul Az PowerShell dapat diidentifikasi dengan nama mereka, yang dimulai dengan _"Az"_. Untuk daftar modul Az PowerShell saat ini, lihat [modul Azure PowerShell](https://github.com/Azure/azure-powershell/blob/master/documentation/azure-powershell-modules.md).

Siklus hidup dukungan modul Az PowerShell berada di bawah [kebijakan siklus hidup Azure SDK](https://support.microsoft.com/help/18486). Kami mendukung dua versi minor terakhir dari versi utama saat ini dan versi minor terakhir dari versi utama modul Az PowerShell sebelumnya.

## <a name="azurerm-powershell-modules"></a>Modul AzureRM PowerShell

Karena modul Az PowerShell sekarang memiliki semua kemampuan modul AzureRM PowerShell dan lebih banyak lagi, kami akan menghentikan modul AzureRM PowerShell pada 29 Februari 2024.

Untuk menghindari gangguan layanan, [perbarui skrip Anda](https://aka.ms/azpsmigrate) yang menggunakan modul AzureRM PowerShell untuk menggunakan modul Az PowerShell paling lambat 29 Februari 2024. Untuk memperbarui skrip Anda secara otomatis, ikuti [panduan memulai cepat](/powershell/azure/quickstart-migrate-azurerm-to-az-automatically).

## <a name="supported-environments"></a>Lingkungan yang didukung

Tabel berikut mengidentifikasi platform yang didukung untuk modul Az, AzureRM, dan Azure PowerShell.

|        Az        | PowerShell <br/> 7.1.3 | PowerShell <br/> >= 7.0.6 | PowerShell <br/> <= 7.0.5 | Windows PowerShell <br/> 5.1 |
| :--------------: | :--------------------: | :-----------------------: | :-----------------------: | :--------------------------: |
|      Az 7.x      |       Didukung        |         Didukung         |       Tidak didukung       |          Didukung           |
|      Az 6.x      |       Didukung        |         Didukung         |       Tidak didukung       |          Didukung           |
| AzureRM (6.13.2) |     Tidak Didukung      |       Tidak Didukung       |       Tidak Didukung       |          Didukung           |
|  Azure (5.3.1)   |     Tidak Didukung      |       Tidak Didukung       |       Tidak Didukung       |          Didukung           |

> [!NOTE]
> PowerShell 6.2 telah mencapai akhir hayatnya pada 4 September 2020. Modul Az PowerShell tidak didukung pada versi PowerShell 6 apa pun.

### <a name="information-about-cve-2021-26701"></a>Informasi mengenai CVE-2021-26701

Modul Az PowerShell menggunakan komponen yang dipengaruhi oleh penasihat keamanan [CVE-2021-26701](https://msrc.microsoft.com/update-guide/vulnerability/CVE-2021-26701) yang telah diperbaiki di PowerShell 7.0.6 dan 7.1.3. Untuk informasi selengkapnya, lihat [Microsoft Security Advisory CVE-2021-26701: Kerentanan Eksekusi Kode Jarak Jauh .NET Core](https://github.com/PowerShell/Announcements/issues/23).

Dimulai dengan Az 6.0.0, PowerShell 7.0.6 atau 7.1.3 atau yang lebih baru diperlukan. Ketika modul Az.Accounts diimpor, pesan non-pemblokiran berikut akan ditampilkan jika versi PowerShell yang tidak didukung digunakan: _"Versi Az.Accounts ini hanya didukung pada Windows PowerShell 5.1 dan PowerShell 7.0.6 atau lebih baru, terbuka [https://aka.ms/install-powershell](https://aka.ms/install-powershell) untuk mempelajari cara meningkatkan. Untuk informasi lebih lanjut, pergi ke [https://aka.ms/azpslifecyle](https://aka.ms/azpslifecycle)."_
