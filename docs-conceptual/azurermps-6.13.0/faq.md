---
title: Pertanyaan Umum (FAQ)
description: Tanya Jawab Umum tentang Azure PowerShell.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 10/05/2021
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
ms.openlocfilehash: a565584ae6af122bf6a4574e9577d72ae7e23076
ms.sourcegitcommit: c489152c02cceaa5c8e284933af57f07c5350961
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 10/07/2021
ms.locfileid: "132429363"
---
# <a name="frequently-asked-questions-about-azure-powershell"></a>Tanya jawab umum tentang Azure PowerShell

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## <a name="what-is-azure-powershell"></a>Apa itu Azure PowerShell?

Azure PowerShell adalah set cmdlet yang memungkinkan Anda untuk mengelola sumber daya Azure langsung dengan PowerShell. Pada bulan Desember 2018, modul Az PowerShell menjadi tersedia secara umum. Kini ini adalah modul PowerShell yang disarankan untuk berinteraksi dengan Azure. Untuk mempelajari selengkapnya tentang modul Az PowerShell, lihat [Memperkenalkan modul Az Azure PowerShell baru](/powershell/azure/new-azureps-module-az).

## <a name="how-do-i-disable-breaking-change-warning-messages-in-azure-powershell"></a>Bagaimana cara menonaktifkan pesan peringatan perubahan pemecahan di Azure PowerShell?

Untuk menekan pesan peringatan perubahan pemecahan di Azure PowerShell, Anda akan harus mengatur variabel lingkungan `SuppressAzurePowerShellBreakingChangeWarnings` ke `true`.

```powershell
Set-Item -Path Env:\SuppressAzurePowerShellBreakingChangeWarnings -Value $true
```

## <a name="how-do-i-disable-the-azurerm-retirement-warning-message-in-azure-powershell"></a>Bagaimana cara menonaktifkan pesan peringatan penghentian AzureRM di Azure PowerShell?

Untuk menekan pesan peringatan penghentian AzureRM di Azure PowerShell, Anda akan harus mengatur variabel lingkungan `SuppressAzureRmModulesRetiringWarning` ke `true`.

```powershell
Set-Item -Path Env:\SuppressAzureRmModulesRetiringWarning -Value $true
```

Satu kekurangan dari contoh sebelumnya adalah Anda akan harus menjalankan perintah untuk sesi PowerShell baru, kecuali jika Anda menambahkannya ke profil PowerShell Anda.

Untuk mengatur variabel lingkungan secara permanen, Anda juga dapat menggunakan contoh berikut.

```powershell
[System.Environment]::SetEnvironmentVariable('SuppressAzureRmModulesRetiringWarning', 'true', [System.EnvironmentVariableTarget]::User)
```
