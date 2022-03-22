---
title: Gambaran Umum Azure Stack Admin PowerShell | Microsoft Docs
description: Penjelasan umum Azure Stack Admin PowerShell dengan petunjuk penginstalan dan konfigurasi.
author: sijuman
ms.author: sijuman
manager: knithinc
ms.devlang: powershell
ms.topic: conceptual
ms.manager: knithinc
ms.date: 02/24/2020
ms.openlocfilehash: e19fea440025e7a00a037e360ac95ff8e0e62129
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132426234"
---
# <a name="azure-stack-module-180"></a>Modul Azure Stack 1.8.0

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
Install-Module -Name AzureStack -RequiredVersion 1.8.0
```

## <a name="release-notes"></a>Catatan Rilis

* Didukung dengan pembaruan 1910
* Perubahan meliputi:

    - **Modul Admin DRP baru**: Penyedia Sumber Daya Penyebaran (DRP) memungkinkan penyebaran penyedia sumber daya yang diatur ke Azure Stack Hub. Perintah ini berinteraksi dengan lapisan Azure Resource Manager untuk berinteraksi dengan DRP.

    - **BRP**: 
        - Mendukung pemulihan peran tunggal untuk pencadangan infrastruktur tumpukan Azure.
        - Menambahkan parameter `RoleName` ke cmdlet R`estore-AzsBackup`.

    - **FRP**: Melanggar perubahan untuk sumber daya **Drive** dan **Volume** dengan API versi 2019-05-01. Fitur ini didukung oleh Azure Stack Hub 1910 dan yang lebih baru: 
        - Nilai ID, `Name`, `HealthStatus`, dan `OperationalStatus` telah berubah.
        - Mendukung properti `FirmwareVersion`, `IsIndicationEnabled`, `Manufacturer`, dan `StoragePool` yang baru untuk sumber daya **Drive**.
        - Properti `CanPool` dan `CannotPoolReason` dari sumber daya **Drive** telah tidak digunakan lagi; gunakan `OperationalStatus` sebagai gantinya.