---
title: Gambaran Umum Admin Azure Stack Hub PowerShell 2.2.0 | Microsoft Docs
description: Gambaran umum PowerShell Admin Azure Stack Hub dengan instruksi untuk penginstalan dan konfigurasi.
author: mattbriggs
ms.author: mabrigg
manager: femila
ms.devlang: powershell
ms.topic: conceptual
ms.manager: femila
ms.date: 12/7/2021
ms.openlocfilehash: e1cae96f1bd801d0654f7d009990cfc20411734f
ms.sourcegitcommit: 1cf30f43dda849e046415dd10e55625f12ef21c4
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/09/2021
ms.locfileid: "134505401"
---
# <a name="azure-stack-hub-module-220"></a>Azure Stack Hub Module 2.2.0

## <a name="requirements"></a>Persyaratan:

Versi minimum Azure Stack Hub yang didukung adalah 2108.

Catatan: Untuk versi Lama Azure Stack, centang Instal [Powershell Tumpukan Azure](/azure/azure-stack/azure-stack-powershell-install#install-azure-stack-powershell)

## <a name="install"></a>Instal

Jalankan cmdlet berikut dari permintaan sesi PowerShell yang ditingkatkan:

```powershell  
# Remove previous versions of AzureStack and AzureRM modules
Get-Module -Name Azure* -ListAvailable | Uninstall-Module -Force -Verbose -ErrorAction Continue
Get-Module -Name Azs.* -ListAvailable | Uninstall-Module -Force -Verbose -ErrorAction Continue
Get-Module -Name Az.* -ListAvailable | Uninstall-Module -Force -Verbose -ErrorAction Continue

[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12

Install-Module PowerShellGet -MinimumVersion 2.2.3 -Force
```

Tutup sesi PowerShell, lalu buka sesi PowerShell baru agar pembaruan dapat diterapkan. Jalankan perintah berikut dari sesi PowerShell:

```powershell  
[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12
Install-Module -Name Az.BootStrapper -Force

# Install and import the API Version Modules required by Azure Stack into the current PowerShell session.
Use-AzProfile -Profile 2020-09-01-hybrid -Force

# Install Azure Stack Admin Module
Install-Module -Name AzureStack -RequiredVersion 2.2.0 -AllowPrerelease
```


## <a name="release-notes"></a>Catatan Rilis

* Didukung dengan pembaruan 2108.  

  Azure Stack Hub 2.2.0 adalah perubahan yang sedang dilakukan. Modul ini menggunakan modul Az, bukan modul AzureRM. Anda dapat menemukan panduan migrasi dan daftar perubahan yang putus dalam Melakukan migrasi dari [AzureRM ke Azure PowerShell Az di Azure Stack Hub.](/azure-stack/operator/azure-stack-powershell-install)
