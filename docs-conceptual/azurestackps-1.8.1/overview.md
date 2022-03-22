---
title: Gambaran Umum Azure Stack Admin PowerShell | Microsoft Docs
description: Penjelasan umum Azure Stack Admin PowerShell dengan petunjuk penginstalan dan konfigurasi.
author: sijuman
ms.author: sijuman
manager: knithinc
ms.devlang: powershell
ms.topic: conceptual
ms.manager: knithinc
ms.date: 03/04/2020
ms.openlocfilehash: 0ee905b741c9f79b4f831bb4ea628f97566b2f1d
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132427392"
---
# <a name="azure-stack-module-181"></a>Modul Azure Stack 1.8.1

## <a name="requirements"></a>Persyaratan:

Versi Azure Stack minimum yang didukung adalah versi 1910.

Catatan: Untuk versi Azure Stack yang lebih lama, periksa [Menginstal Azure Stack Powershell](/azure/azure-stack/azure-stack-powershell-install#install-azure-stack-powershell)

## <a name="install"></a>Instal

```powershell
# Remove previous versions of AzureStack and AzureRM modules
Get-Module -Name Azs.* -ListAvailable | Uninstall-Module -Force -Verbose
Get-Module -Name Azure* -ListAvailable | Uninstall-Module -Force -Verbose

# Install and import the API Version Modules required by Azure Stack into the current PowerShell session.
Use-AzureRmProfile -Profile 2019-03-01-hybrid -Force

# Install Azure Stack Admin Module
Install-Module -Name AzureStack -RequiredVersion 1.8.1
```

## <a name="release-notes"></a>Catatan Rilis

* Didukung dengan pembaruan 1910