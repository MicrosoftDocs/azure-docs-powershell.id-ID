---
title: Masuk ke Azure dengan modul Azure PowerShell
description: Cara masuk ke Azure dengan modul Azure PowerShell sebagai pengguna, perwakilan layanan, atau dengan identitas terkelola atau sumber daya Azure.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 10/05/2021
ms.custom: devx-track-azurepowershell
ms.openlocfilehash: 3c756da0a258938b647d29c45b2bd3afa14ad559
ms.sourcegitcommit: c489152c02cceaa5c8e284933af57f07c5350961
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 10/07/2021
ms.locfileid: "132429375"
---
# <a name="sign-into-azure-with-the-azurerm-powershell-module"></a>Masuk ke Azure dengan modul Azure PowerShell

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

Azure PowerShell mendukung beberapa metode autentikasi. Cara termudah untuk memulai adalah masuk secara interaktif di baris perintah.

## <a name="sign-in-interactively"></a>Masuk secara interaktif

Untuk masuk secara interaktif, gunakan cmdlet [Connect-AzureRmAccount](/powershell/module/azurerm.profile/connect-azurermaccount).

```azurepowershell-interactive
Connect-AzureRmAccount
```

Saat dijalankan, cmdlet ini akan memunculkan kotak dialog yang meminta alamat email dan kata sandi Anda yang berkaitan dengan akun Azure Anda. Autentikasi ini berlangsung selama sesi PowerShell saat ini.

> [!IMPORTANT]
> Pada Azure PowerShell 6.3.0, info masuk Anda dibagikan di antara beberapa sesi PowerShell selama Anda tetap masuk di Windows. Untuk informasi selengkapnya, lihat artikel tentang [Info Masuk Persisten](context-persistence.md).

## <a name="sign-in-with-a-service-principal"></a>Masuk dengan perwakilan layanan

Perwakilan layanan adalah akun Azure non-interaktif. Seperti akun pengguna lainnya, izinnya dikelola dengan Azure Active Directory. Dengan memberikan perwakilan layanan hanya izin yang dibutuhkan, skrip otomatisasi Anda tetap aman.

Untuk mempelajari cara membuat perwakilan layanan untuk digunakan dengan Azure PowerShell, lihat [Membuat perwakilan layanan Azure dengan Azure PowerShell](create-azure-service-principal-azureps.md).

Untuk masuk dengan perwakilan layanan, gunakan argumen `ServicePrincipal` dengan cmdlet `Connect-AzureRmAccount`. Anda juga memerlukan informasi masuk perwakilan layanan dan ID penyewa yang berkaitan dengan perwakilan layanan. Untuk mendapatkan info masuk perwakilan layanan sebagai objek yang sesuai, gunakan cmdlet [Get-Credential](/powershell/module/microsoft.powershell.security/get-credential). Cmdlet ini akan menampilkan kotak dialog untuk memasukkan ID pengguna dan kata sandi perwakilan layanan.

```azurepowershell
$pscredential = Get-Credential
Connect-AzureRmAccount -ServicePrincipal -Credential $pscredential -TenantId $tenantid
```

## <a name="sign-in-using-an-azure-managed-service-identity"></a>Masuk menggunakan Identitas Layanan Terkelola Azure

Identitas terkelola untuk sumber daya Azure adalah fitur Azure Active Directory. Anda dapat menggunakan perwakilan layanan identitas terkelola untuk masuk, dan memperoleh token akses khusus aplikasi untuk mengakses sumber daya lain. Identitas terkelola hanya tersedia di mesin virtual yang berjalan di cloud Azure.

Untuk informasi selengkapnya tentang identitas terkelola untuk sumber daya Azure, lihat [Cara menggunakan identitas terkelola untuk sumber daya Azure pada Komputer Virtual Azure untuk memperoleh token akses](/azure/active-directory/managed-identities-azure-resources/how-to-use-vm-token).

## <a name="sign-in-as-a-cloud-solution-provider-csp"></a>Masuk sebagai Penyedia Solusi Cloud (CSP)

Masuk sebagai [Penyedia Solusi Cloud (CSP)](https://azure.microsoft.com/offers/ms-azr-0145p/) membutuhkan penggunaan `TenantId`. Biasanya, parameter ini dapat disediakan sebagai ID penyewa atau nama domain. Namun, untuk masuk CSP, harus disediakan sebagai **ID penyewa**.

```azurepowershell
Connect-AzureRmAccount -TenantId '00000000-0000-0000-0000-000000000000'
```

## <a name="sign-in-to-another-cloud"></a>Masuk ke Cloud lain

Layanan cloud Azure menawarkan lingkungan yang sesuai dengan peraturan penanganan data regional. Untuk akun di cloud regional, atur lingkungan saat Anda masuk dengan argumen `-Environment`.
Misalnya, jika akun Anda berada di cloud China:

```azurepowershell
Connect-AzureRmAccount -Environment AzureChinaCloud
```

Perintah berikut mendapatkan daftar lingkungan yang tersedia:

```azurepowershell
Get-AzureRmEnvironment | Select-Object -Property Name
```

## <a name="learn-more-about-managing-azure-role-based-access"></a>Mempelajari selengkapnya tentang mengelola akses berbasis peran Azure

Untuk informasi selengkapnya tentang manajemen autentikasi dan langganan di Azure, lihat [Mengelola Akun, Langganan, dan Peran Administratif](/azure/active-directory/role-based-access-control-configure).

Cmdlet Azure PowerShell untuk manajemen peran:

* [Get-AzureRmRoleAssignment](/powershell/module/AzureRM.Resources/Get-AzureRmRoleAssignment)
* [Get-AzureRmRoleDefinition](/powershell/module/AzureRM.Resources/Get-AzureRmRoleDefinition)
* [New-AzureRmRoleAssignment](/powershell/module/AzureRM.Resources/New-AzureRmRoleAssignment)
* [New-AzureRmRoleDefinition](/powershell/module/AzureRM.Resources/New-AzureRmRoleDefinition)
* [Remove-AzureRmRoleAssignment](/powershell/module/AzureRM.Resources/Remove-AzureRmRoleAssignment)
* [Remove-AzureRmRoleDefinition](/powershell/module/AzureRM.Resources/Remove-AzureRmRoleDefinition)
* [Set-AzureRmRoleDefinition](/powershell/module/AzureRM.Resources/Set-AzureRmRoleDefinition)
