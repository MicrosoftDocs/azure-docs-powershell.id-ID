---
title: Gambaran Umum Azure Stack Hub Admin PowerShell 2.0.2 | Microsoft Docs
description: Gambaran umum Azure Stack Hub Admin PowerShell dengan instruksi untuk penginstalan dan konfigurasi.
author: mattbriggs
ms.author: mabrigg
manager: femila
ms.devlang: powershell
ms.topic: conceptual
ms.manager: femila
ms.date: 09/23/2021
ms.openlocfilehash: c8e2f8d8cf7e17edeeb13c01c48a2d5eab8c0421
ms.sourcegitcommit: 1cf30f43dda849e046415dd10e55625f12ef21c4
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 12/09/2021
ms.locfileid: "134505238"
---
# <a name="azure-stack-hub-module-202"></a>Modul Azure Stack Hub 2.0.2

## <a name="requirements"></a>Persyaratan:

Versi Azure Stack Hub minimum yang didukung adalah versi tahun 2002.

Catatan: Untuk versi Azure Stack yang lebih lama, periksa [Menginstal Azure Stack Powershell](/azure/azure-stack/azure-stack-powershell-install#install-azure-stack-powershell)

## <a name="install"></a>Instal

```powershell
# Remove previous versions of AzureStack and AzureRM modules
Get-Module -Name Azure* -ListAvailable | Uninstall-Module -Force -Verbose -ErrorAction Continue
Get-Module -Name Azs.* -ListAvailable | Uninstall-Module -Force -Verbose -ErrorAction Continue
Get-Module -Name Az.* -ListAvailable | Uninstall-Module -Force -Verbose -ErrorAction Continue

Install-Module -Name Az.BootStrapper -Force -AllowPrerelease -SkipPublisherCheck

# Install and import the API Version Modules required by Azure Stack into the current PowerShell session.
Use-AzProfile -Profile 2019-03-01-hybrid -Force

# Install Azure Stack Admin Module
Install-Module -Name AzureStack -RequiredVersion 2.0.2-preview -AllowPrerelease
```


## <a name="release-notes"></a>Catatan Rilis

* Didukung dengan pembaruan 2002.  

  Azure Stack Hub 2.0.0 adalah perubahan pemecahan. Modul menggunakan modul Az bukan modul AzureRM. Anda dapat menemukan panduan migrasi dan daftar perubahan pemecahan di [Migrasi dari AzureRM ke Azure PowerShell Az di Azure Stack Hub](/azure-stack/operator/azure-stack-powershell-install).
