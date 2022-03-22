---
title: Gambaran Umum Azure Stack Admin PowerShell | Microsoft Docs
description: Gambaran umum Azure Stack Admin PowerShell dengan instruksi untuk penginstalan dan konfigurasi.
author: sijuman
ms.author: sijuman
manager: knithinc
ms.devlang: powershell
ms.topic: conceptual
ms.manager: knithinc
ms.date: 02/06/2019
ms.openlocfilehash: 72974ac2fec42da962513c161c506e83f047bfb6
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132426237"
---
# <a name="azure-stack-module-172"></a>Modul Azure Stack 1.7.2

## <a name="requirements"></a>Persyaratan:

Versi Azure Stack minimum yang didukung adalah versi tahun 1904.

Catatan: Untuk versi Azure Stack yang lebih lama, periksa [Menginstal Azure Stack Powershell](/azure/azure-stack/azure-stack-powershell-install#install-azure-stack-powershell)

## <a name="install"></a>Instal

```powershell
# Remove previous versions of AzureStack and AzureRM modules
Get-Module -Name Azs.* -ListAvailable | Uninstall-Module -Force -Verbose
Get-Module -Name Azure* -ListAvailable | Uninstall-Module -Force -Verbose

# Install and import the API Version Modules required by Azure Stack into the current PowerShell session.
Install-Module -Name AzureRM -RequiredVersion 2.5.0

# Install Azure Stack Admin Module
Install-Module -Name AzureStack -RequiredVersion 1.7.2
```

## <a name="release-notes"></a>Catatan Rilis

* Didukung dengan pembaruan 1904
* Ini adalah rilis perubahan pemecahan. Untuk detail tentang perubahan yang melanggar, lihat <https://aka.ms/azspshmigration170>
* Melanggar perubahan: Perubahan pencadangan ke mode enkripsi berbasis sertifikat. Dukungan untuk kunci simetris tidak digunakan lagi.
* Untuk detail tentang perubahan yang melanggar, lihat https://aka.ms/azspshmigration170
* Modul Azs.Storage.Admin 
* Perbaikan bug - Kuota Penyimpanan Baru menggunakan default jika tidak ada yang disediakan.