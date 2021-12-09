---
title: Gambaran umum | PowerShell Admin Tumpukan Azure Microsoft Docs
description: Gambaran umum PowerShell Admin Tumpukan Azure dengan instruksi untuk penginstalan dan konfigurasi.
author: mattbriggs
ms.author: mabrigg
manager: femila
ms.devlang: powershell
ms.topic: conceptual
ms.manager: femila
ms.date: 09/23/2021
ms.openlocfilehash: 6770a5509f48f40e3dde4db2fcd23ede074ce7d4
ms.sourcegitcommit: 1cf30f43dda849e046415dd10e55625f12ef21c4
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/09/2021
ms.locfileid: "134505389"
---
# <a name="azure-stack-module-183"></a>Azure Stack Module 1.8.3

## <a name="requirements"></a>Persyaratan:

Versi Minimum Tumpukan Azure yang didukung adalah 2002.

Catatan: Untuk versi Lama Azure Stack, centang Instal [Powershell Tumpukan Azure](/azure/azure-stack/azure-stack-powershell-install#install-azure-stack-powershell)

> [!IMPORTANT]  
> Anda telah mencapai halaman web untuk versi lama Azure Stack Hub PowerShell. Semua versi modul PowerShell Azure Resource Manager (AzureRM) usang, tetapi tidak didukung. Modul AzureRM tidak akan diperbarui lagi di build Azure Stack Hub mendatang. Modul Az akan digunakan untuk build 2002 dan yang lebih baru. Profil hibrid 2020-09-01 tidak didukung untuk modul AzureRM.  
> 
> Modul Az PowerShell kini merupakan modul PowerShell yang disarankan untuk berinteraksi dengan Azure dan Azure Stack Hub. Untuk mulai menggunakan modul Az PowerShell, lihat Menginstal [modul pratinjau PowerShell Az untuk Azure Stack Hub](/azure-stack/operator/powershell-install-az-module.md). Untuk mempelajari cara melakukan migrasi ke modul Az PowerShell. lihat [Melakukan migrasi dari AzureRM ke Azure PowerShell Az di Azure Stack Hub](/azure-stack/operator/migrate-azurerm-az.md). Untuk detail tentang peningkatan fungsionalitas modul Az, yang telah diterapkan di seluruh azure global, lihat Memperkenalkan [modul PowerShell Azure Az.](/azure-stack/operator/powershell/azure/new-azureps-module-az)

## <a name="install"></a>Instal

```powershell
# Remove previous versions of AzureStack and AzureRM modules
Get-Module -Name Azs.* -ListAvailable | Uninstall-Module -Force -Verbose
Get-Module -Name Azure* -ListAvailable | Uninstall-Module -Force -Verbose

# Install and import the API Version Modules required by Azure Stack into the current PowerShell session.
Use-AzureRmProfile -Profile 2019-03-01-hybrid -Force

# Install Azure Stack Admin Module
Install-Module -Name AzureStack -RequiredVersion 1.8.3
```

## <a name="release-notes"></a>Catatan Rilis

* Didukung dengan pembaruan 1910