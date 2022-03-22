---
title: Gambaran Umum Azure Stack Hub Admin PowerShell 2.2.0 | Microsoft Docs
description: Gambaran umum Azure Stack Hub Admin PowerShell dengan instruksi untuk penginstalan dan konfigurasi.
author: mattbriggs
ms.author: mabrigg
manager: femila
ms.devlang: powershell
ms.topic: conceptual
ms.manager: femila
ms.date: 12/7/2021
ms.openlocfilehash: 7822673db0b2a009006a784d79e683ccef144f0e
ms.sourcegitcommit: e109cc5320478db6aa8a52d49996b133007a65b9
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 01/12/2022
ms.locfileid: "135955069"
---
# <a name="azure-stack-hub-module-220"></a>Modul Azure Stack Hub 2.2.0

## <a name="requirements"></a>Persyaratan:

Versi Azure Stack Hub minimum yang didukung adalah versi tahun 2108.

Catatan: Untuk versi Azure Stack yang lebih lama, periksa [Menginstal Azure Stack Powershell](/azure/azure-stack/azure-stack-powershell-install#install-azure-stack-powershell)

## <a name="install"></a>Instal

Untuk petunjuk penginstalan mendetail silakan lihat [Menginstal Azure Stack Powershell](/azure/azure-stack/azure-stack-powershell-install#install-azure-stack-powershell). Jalankan cmdlet berikut dari permintaan sesi PowerShell yang ditingkatkan:

```powershell  
# Remove previous versions of AzureStack and AzureRM modules
Get-Module -Name Azure* -ListAvailable | Uninstall-Module -Force -Verbose -ErrorAction Continue
Get-Module -Name Azs.* -ListAvailable | Uninstall-Module -Force -Verbose -ErrorAction Continue
Get-Module -Name Az.* -ListAvailable | Uninstall-Module -Force -Verbose -ErrorAction Continue

[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12

Install-Module PowerShellGet -MinimumVersion 2.2.3 -Force
```

Tutup sesi PowerShell Anda, lalu buka sesi PowerShell baru sehingga pembaruan dapat berlaku. Jalankan perintah dari sesi PowerShell berikut ini:

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
* Rilis 2.2.0 ini memperbarui kemampuan dalam modul Azs.Compute.Admin. Rilis ini juga menambahkan modul baru untuk bekerja dengan Azure Container Registry di Azure Stack Hub: Azs.ContainerRegistry.Admin dan Azs.ContainerService.Admin. Modul Admin kini memiliki dependensi pada modul Az.Resources versi 0.12.0. Untuk detail tentang perubahan dalam pembaruan ini, lihat [log perubahan](https://github.com/Azure/azurestack-powershell/blob/release-2108/src/changelog.md) modul AzureStack
