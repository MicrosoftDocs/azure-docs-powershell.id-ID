---
title: Masuk ke Azure dengan modul PowerShell AzureRM
description: Cara masuk ke Azure dengan modul PowerShell AzureRM sebagai pengguna, prinsipal layanan, atau dengan identitas terkelola untuk sumber daya Azure.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 10/05/2021
ms.custom: devx-track-azurepowershell
ms.openlocfilehash: 3c756da0a258938b647d29c45b2bd3afa14ad559
ms.sourcegitcommit: c489152c02cceaa5c8e284933af57f07c5350961
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/07/2021
ms.locfileid: "132429375"
---
# <a name="sign-into-azure-with-the-azurerm-powershell-module"></a>Masuk ke Azure dengan modul PowerShell AzureRM

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

Azure PowerShell mendukung beberapa metode autentikasi. Cara termudah untuk memulai adalah masuk secara interaktif di baris perintah.

## <a name="sign-in-interactively"></a>Masuk secara interaktif

Untuk masuk secara interaktif, gunakan cmdlet [Koneksi-AzureRmAccount.](/powershell/module/azurerm.profile/connect-azurermaccount)

```azurepowershell-interactive
Connect-AzureRmAccount
```

Saat dijalankan, cmdlet ini akan muncul dalam kotak dialog yang meminta alamat email dan kata sandi terkait dengan akun Azure Anda. Autentikasi ini berlangsung untuk sesi PowerShell saat ini.

> [!IMPORTANT]
> Selama Azure PowerShell 6.3.0, kredensial Anda dibagikan di antara beberapa sesi PowerShell selama Anda tetap masuk ke Windows. Untuk informasi selengkapnya, lihat artikel tentang [Kredensial Tetap.](context-persistence.md)

## <a name="sign-in-with-a-service-principal"></a>Masuk dengan prinsipal layanan

Prinsipal layanan adalah akun Azure yang tidak interaktif. Seperti akun pengguna lain, izin mereka dikelola dengan Azure Active Directory. Dengan memberikan izin yang diperlukan hanya prinsipal layanan, skrip otomatisasi Anda tetap aman.

Untuk mempelajari cara membuat prinsipal layanan untuk digunakan dengan Azure PowerShell, [lihat Membuat prinsipal layanan Azure dengan Azure PowerShell](create-azure-service-principal-azureps.md).

Untuk masuk dengan prinsipal layanan, gunakan `ServicePrincipal` argumen dengan `Connect-AzureRmAccount` cmdlet. Anda juga akan memerlukan kredensial masuk prinsipal layanan dan ID penyewa yang terkait dengan prinsipal layanan. Untuk mendapatkan kredensial prinsipal layanan sebagai objek yang tepat, gunakan cmdlet [Get-Credential.](/powershell/module/microsoft.powershell.security/get-credential) Cmdlet ini akan menampilkan kotak dialog untuk memasukkan ID pengguna dan kata sandi prinsipal layanan.

```azurepowershell
$pscredential = Get-Credential
Connect-AzureRmAccount -ServicePrincipal -Credential $pscredential -TenantId $tenantid
```

## <a name="sign-in-using-an-azure-managed-service-identity"></a>Masuk menggunakan Identitas Layanan Terkelola Azure

Identitas terkelola untuk sumber daya Azure adalah fitur penting Azure Active Directory. Anda dapat menggunakan prinsipal layanan identitas terkelola untuk masuk, dan memperoleh token akses aplikasi-saja untuk mengakses sumber daya lainnya. Identitas yang dikelola hanya tersedia pada mesin virtual yang berjalan di awan Azure.

Untuk informasi selengkapnya tentang identitas terkelola untuk sumber daya Azure, lihat Cara menggunakan identitas terkelola untuk sumber daya Azure di [Azure VM untuk memperoleh token akses.](/azure/active-directory/managed-identities-azure-resources/how-to-use-vm-token)

## <a name="sign-in-as-a-cloud-solution-provider-csp"></a>Masuk sebagai Penyedia Solusi Cloud (CSP)

Masuk [Penyedia Solusi Cloud (CSP)](https://azure.microsoft.com/offers/ms-azr-0145p/) memerlukan penggunaan `TenantId` . Biasanya, parameter ini bisa disediakan sebagai ID penyewa atau nama domain. Namun, untuk masuk CSP, id penyewa harus **disediakan.**

```azurepowershell
Connect-AzureRmAccount -TenantId '00000000-0000-0000-0000-000000000000'
```

## <a name="sign-in-to-another-cloud"></a>Masuk ke Cloud lain

Layanan cloud Azure menawarkan lingkungan yang mematuhi peraturan penanganan data kawasan. Untuk akun di awan regional, setel lingkungan ketika Anda masuk dengan `-Environment` argumen.
Misalnya, jika akun Anda berada di awan Tiongkok:

```azurepowershell
Connect-AzureRmAccount -Environment AzureChinaCloud
```

Perintah berikut ini berisi daftar lingkungan yang tersedia:

```azurepowershell
Get-AzureRmEnvironment | Select-Object -Property Name
```

## <a name="learn-more-about-managing-azure-role-based-access"></a>Pelajari selengkapnya tentang mengelola akses berbasis peran Azure

Untuk informasi selengkapnya tentang autentikasi dan manajemen langganan di Azure, [lihat Mengelola Akun, Langganan, dan Peran Administratif.](/azure/active-directory/role-based-access-control-configure)

Azure PowerShell cmdlet untuk manajemen peran:

* [Get-AzureRmRoleAssignment](/powershell/module/AzureRM.Resources/Get-AzureRmRoleAssignment)
* [Get-AzureRmRoleDefinition](/powershell/module/AzureRM.Resources/Get-AzureRmRoleDefinition)
* [New-AzureRmRoleAssignment](/powershell/module/AzureRM.Resources/New-AzureRmRoleAssignment)
* [New-AzureRmRoleDefinition](/powershell/module/AzureRM.Resources/New-AzureRmRoleDefinition)
* [Remove-AzureRmRoleAssignment](/powershell/module/AzureRM.Resources/Remove-AzureRmRoleAssignment)
* [Remove-AzureRmRoleDefinition](/powershell/module/AzureRM.Resources/Remove-AzureRmRoleDefinition)
* [Set-AzureRmRoleDefinition](/powershell/module/AzureRM.Resources/Set-AzureRmRoleDefinition)
