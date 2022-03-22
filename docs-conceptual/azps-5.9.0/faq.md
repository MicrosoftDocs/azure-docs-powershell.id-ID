---
title: Pertanyaan Umum (FAQ)
description: Tanya Jawab Umum tentang Azure PowerShell.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 08/17/2020
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
ms.openlocfilehash: d9811c5d77c6b2fddcb6024c425940389594df39
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132428322"
---
# <a name="frequently-asked-questions-about-azure-powershell"></a>Tanya jawab umum tentang Azure PowerShell

## <a name="what-is-azure-powershell"></a>Apa itu Azure PowerShell?

Azure PowerShell adalah set cmdlet yang memungkinkan Anda untuk mengelola sumber daya Azure langsung dengan PowerShell. Pada bulan Desember 2018, modul Az PowerShell menjadi tersedia secara umum. Kini ini adalah modul PowerShell yang disarankan untuk berinteraksi dengan Azure. Untuk mempelajari selengkapnya tentang modul Az PowerShell, lihat [Memperkenalkan modul Az Azure PowerShell baru](/powershell/azure/new-azureps-module-az).

## <a name="how-do-i-disable-breaking-change-warning-messages-in-azure-powershell"></a>Bagaimana cara menonaktifkan pesan peringatan perubahan pemecahan di Azure PowerShell?

Untuk menekan pesan peringatan perubahan pemecahan di Azure PowerShell, Anda akan harus mengatur variabel lingkungan `SuppressAzurePowerShellBreakingChangeWarnings` ke `true`.

```azurepowershell
Set-Item -Path Env:\SuppressAzurePowerShellBreakingChangeWarnings -Value $true
```

## <a name="how-do-i-disable-the-azurerm-retirement-warning-message-in-azure-powershell"></a>Bagaimana cara menonaktifkan pesan peringatan penghentian AzureRM di Azure PowerShell?

Untuk menekan pesan peringatan penghentian AzureRM di Azure PowerShell, Anda akan harus mengatur variabel lingkungan `SuppressAzureRmModulesRetiringWarning` ke `true`.

```azurepowershell-interactive
Set-Item -Path Env:\SuppressAzureRmModulesRetiringWarning -Value $true
```

Satu kekurangan dari contoh sebelumnya adalah Anda akan harus menjalankan perintah untuk sesi PowerShell baru, kecuali jika Anda menambahkannya ke profil PowerShell Anda.

Untuk mengatur variabel lingkungan secara permanen, Anda juga dapat menggunakan contoh berikut.

```azurepowershell-interactive
[System.Environment]::SetEnvironmentVariable('SuppressAzureRmModulesRetiringWarning', 'true', [System.EnvironmentVariableTarget]::User)
```
