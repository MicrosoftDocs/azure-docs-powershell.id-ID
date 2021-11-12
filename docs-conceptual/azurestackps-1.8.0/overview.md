---
title: Gambaran umum tentang PowerShell Admin Tumpukan Azure | Microsoft Docs
description: Gambaran umum PowerShell Admin Tumpukan Azure dengan instruksi untuk penginstalan dan konfigurasi.
author: sijuman
ms.author: sijuman
manager: knithinc
ms.devlang: powershell
ms.topic: conceptual
ms.manager: knithinc
ms.date: 02/24/2020
ms.openlocfilehash: e19fea440025e7a00a037e360ac95ff8e0e62129
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132426234"
---
# <a name="azure-stack-module-180"></a>Azure Stack Module 1.8.0

## <a name="requirements"></a>Persyaratan:

Versi minimum Azure Stack yang didukung adalah 1910.

Catatan: Untuk versi Lama Azure Stack, centang Instal [Powershell Tumpukan Azure](/azure/azure-stack/azure-stack-powershell-install#install-azure-stack-powershell)

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

    - **Modul Admin DRP baru:** Penyedia Sumber Daya Penyebaran (DRP, Deployment Resource Provider) memungkinkan penyebaran grup dari penyedia sumber daya ke Azure Stack Hub. Perintah ini berinteraksi dengan lapisan Azure Resource Manager untuk berinteraksi dengan DRP.

    - **BRP**:
        - Mendukung pemulihan peran tunggal untuk pencadangan infrastruktur tumpukan Azure.
        - Menambahkan parameter `RoleName` ke cmdlet `estore-AzsBackup` R.

    - **FRP**: Memutus perubahan untuk Sumber daya **Drive** **dan Volume** dengan API versi 2019-05-01. Fitur tersebut didukung oleh Azure Stack Hub 1910 dan yang lebih baru:
        - Nilai ID, `Name` , `HealthStatus` , dan telah `OperationalStatus` diubah.
        - Properti baru yang `FirmwareVersion` didukung, `IsIndicationEnabled` , , dan untuk sumber `Manufacturer` `StoragePool` **daya** Drive.
        - Properti `CanPool` dan `CannotPoolReason` sumber daya **Drive** telah ditolak; gunakan sebagai `OperationalStatus` gantinya.