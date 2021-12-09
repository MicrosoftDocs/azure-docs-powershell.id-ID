---
title: Gambaran umum Admin Hub Azure PowerShell 2.0.1 | Microsoft Docs
description: Gambaran umum PowerShell Admin Azure Stack Hub dengan instruksi untuk penginstalan dan konfigurasi.
author: mattbriggs
ms.author: mabrigg
manager: femila
ms.devlang: powershell
ms.topic: conceptual
ms.manager: femila
ms.date: 09/23/2021
ms.openlocfilehash: ca8c3ffca2af1448ed7c45fc2e7053f5503f873f
ms.sourcegitcommit: 1cf30f43dda849e046415dd10e55625f12ef21c4
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/09/2021
ms.locfileid: "134505346"
---
# <a name="azure-stack-hub-module-201"></a>Azure Stack Hub Module 2.0.1

## <a name="requirements"></a>Persyaratan:

Versi minimum Azure Stack Hub yang didukung adalah 2002.

Catatan: Untuk versi Lama Azure Stack, centang Instal [Powershell Tumpukan Azure](/azure/azure-stack/azure-stack-powershell-install#install-azure-stack-powershell)

## <a name="install"></a>Instal

```powershell
# Remove previous versions of AzureStack and AzureRM modules
Get-Module -Name Azure* -ListAvailable | Uninstall-Module -Force -Verbose -ErrorAction Continue
Get-Module -Name Azs.* -ListAvailable | Uninstall-Module -Force -Verbose -ErrorAction Continue
Get-Module -Name Az.* -ListAvailable | Uninstall-Module -Force -Verbose -ErrorAction Continue

Install-Module -Name Az.BootStrapper -Force -AllowPrerelease

# Install and import the API Version Modules required by Azure Stack into the current PowerShell session.
Use-AzProfile -Profile 2019-03-01-hybrid -Force

# Install Azure Stack Admin Module
Install-Module -Name AzureStack -RequiredVersion 2.0.1-preview -AllowPrerelease
```


## <a name="release-notes"></a>Catatan Rilis

* Didukung dengan pembaruan 2002.  

  Azure Stack Hub 2.0.0 adalah perubahan yang sedang dilakukan. Modul ini menggunakan modul Az, bukan modul AzureRM. Anda dapat menemukan panduan migrasi dan daftar perubahan yang putus dalam Melakukan migrasi dari [AzureRM ke Azure PowerShell Az di Azure Stack Hub.](/azure-stack/operator/azure-stack-powershell-install)