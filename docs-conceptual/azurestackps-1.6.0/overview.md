---
title: Gambaran Umum Azure Stack Admin PowerShell | Microsoft Docs
description: Penjelasan umum Azure Stack Admin PowerShell dengan petunjuk penginstalan dan konfigurasi.
author: bganapa
ms.author: bganapa
manager: knithinc
ms.devlang: powershell
ms.topic: conceptual
ms.manager: knithinc
ms.date: 09/21/2018
ms.openlocfilehash: b0e85bec82b9b7c876b2bbf337b603c8d68cf6a3
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132428298"
---
# <a name="azure-stack-module-160"></a>Modul Azure Stack 1.6.0

## <a name="requirements"></a>Persyaratan:
Versi Azure Stack minimum yang didukung adalah versi 1811.

Catatan: Jika Anda menggunakan versi yang lebih lama, instal versi 1.6.0

## <a name="install"></a>Instal
```
# Remove previous versions of AzureStack and AzureRM modules
Uninstall-Module -Name AzureRM -Force
Uninstall-Module -Name Azure.Storage -Force
Uninstall-Module -Name AzureStack -Force
Get-Module -Name "Azs*" -ListAvailable | Uninstall-Module  -Force 
Get-Module -Name "AzureRm*" -ListAvailable | Uninstall-Module  -Force

# Install the AzureRM.Bootstrapper module. Select Yes when prompted to install NuGet
Install-Module -Name AzureRm.BootStrapper

# Install and import the API Version Profile required by Azure Stack into the current PowerShell session.
Use-AzureRmProfile -Profile 2018-03-01-hybrid -Force

# Install Azure Stack Admin Module
Install-Module -Name AzureStack -RequiredVersion 1.6.0
```

## <a name="release-notes"></a>Catatan Rilis
* Didukung dengan pembaruan 1811
* Modul Azs.Compute.Admin
    * Memperbaiki awalan Azs yang hilang untuk New-DataDiskObject dan menambahkan alias dengan peringatan penghentian di masa mendatang.
* Modul Azs.Update.Admin
    * Menambahkan peringatan ke Test-AzureStack berjalan yang disarankan sebelum Install-AzsUpdate
* Azs.Fabric.Admin
    * Cmdlet baru (Fitur didukung oleh Azure Stack 1811+)
        * Get-AzsDrive
        * Get-AzsVolume
        * Get-AzsStorageSubSystem
    * Penghentian
        * Get-AzsInfrastructureVolume kini adalah alias untuk cmdlet Get-AzsVolume
* Azs.InfrastructureInsights.Admin
    *  Menambahkan cmdlet Repair-AzsAlert baru
* Azs.Storage.Admin
    * Perbaikan bug tempat nilai kuota default sedang tidak digunakan
* Modul Azs.Subscriptions.Admin
    * Memperbaiki awalan Azs yang hilang untuk AddonPlanDefinitionObject dan menambahkan alias dengan peringatan penghentian di masa mendatang.
