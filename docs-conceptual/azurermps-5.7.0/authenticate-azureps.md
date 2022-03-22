---
title: Masuk dengan Azure PowerShell
description: Cara masuk dengan Azure PowerShell sebagai pengguna, perwakilan layanan, atau dengan identitas terkelola untuk sumber daya Azure.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 05/15/2017
ms.custom: devx-track-azurepowershell
ms.openlocfilehash: 326d4402b4f58f29c14129f32f5b5ffda2d762fa
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132428302"
---
# <a name="sign-in-with-azure-powershell"></a>Masuk dengan Azure PowerShell

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

Azure PowerShell mendukung beberapa metode autentikasi. Cara termudah untuk memulai adalah masuk secara interaktif di baris perintah.

## <a name="sign-in-interactively"></a>Masuk secara interaktif

Untuk masuk secara interaktif, gunakan cmdlet [Connect-AzureRmAccount](/powershell/module/azurerm.profile/connect-azurermaccount).

```azurepowershell-interactive
Connect-AzureRmAccount
```

Saat dijalankan, cmdlet ini akan memunculkan kotak dialog yang meminta alamat email dan kata sandi Anda yang berkaitan dengan akun Azure Anda. Saat mengautentikasi, informasi tersebut disimpan untuk sesi PowerShell saat ini, dialog ditutup, dan Anda memiliki akses ke semua cmdlet Azure PowerShell.

> [!IMPORTANT]
> Proses masuk ini _hanya_ untuk sesi PowerShell saat ini. Untuk mempertahankan autentikasi di beberapa sesi, lihat artikel tentang [Informasi Masuk Persisten](context-persistence.md).

## <a name="sign-in-with-a-service-principal"></a>Masuk dengan perwakilan layanan

Perwakilan layanan menyediakan cara untuk membuat akun non-interaktif yang dapat Anda gunakan untuk memanipulasi sumber daya. Perwakilan layanan seperti akun pengguna tempat Anda dapat menerapkan aturan menggunakan Azure Active Directory. Dengan memberikan izin minimum yang diperlukan untuk perwakilan layanan, Anda dapat memastikan skrip otomatisasi Anda bahkan lebih aman.

Jika Anda harus membuat perwakilan layanan untuk digunakan dengan Azure PowerShell, lihat [Membuat perwakilan layanan Azure dengan Azure PowerShell](create-azure-service-principal-azureps.md).

Untuk masuk dengan perwakilan layanan, gunakan argumen `-ServicePrincipal` dengan cmdlet `Connect-AzureRmAccount`. Anda juga memerlukan ID aplikasi perwakilan layanan, info masuk, dan mengaitkan ID penyewa dengan perwakilan layanan. Untuk mendapatkan informasi masuk perwakilan layanan sebagai objek yang sesuai, gunakan cmdlet [Get-Credential](/powershell/module/microsoft.powershell.security/get-credential). Cmdlet ini akan menampilkan kotak dialog untuk memasukkan ID pengguna dan kata sandi perwakilan layanan.

```azurepowershell-interactive
$pscredential = Get-Credential
Connect-AzureRmAccount -ServicePrincipal -ApplicationId  "http://my-app" -Credential $pscredential -TenantId $tenantid
```

## <a name="sign-in-using-managed-identities-for-azure-resources"></a>Masuk menggunakan identitas terkelola untuk sumber daya Azure

Identitas terkelola untuk sumber daya Azure adalah fitur Azure Active Directory. Anda dapat menggunakan perwakilan layanan identitas terkelola untuk masuk, dan memperoleh token akses khusus aplikasi untuk mengakses sumber daya lain. Identitas terkelola hanya tersedia di mesin virtual yang berjalan di cloud Azure.

Untuk informasi selengkapnya tentang identitas terkelola untuk sumber daya Azure, lihat [Cara menggunakan identitas terkelola untuk sumber daya Azure pada Komputer Virtual Azure untuk memperoleh token akses](/azure/active-directory/managed-identities-azure-resources/how-to-use-vm-token).

## <a name="sign-in-to-another-cloud"></a>Masuk ke Cloud lain

Layanan cloud Azure menyediakan lingkungan yang berbeda yang mematuhi peraturan penanganan data berbagai wilayah. Jika akun Azure Anda ada di cloud yang berkaitan dengan salah satu wilayah ini, Anda harus menentukan lingkungan ketika masuk. Misalnya, jika akun Anda ada di cloud Tiongkok, Anda masuk menggunakan perintah berikut:

```azurepowershell-interactive
Connect-AzureRmAccount -Environment AzureChinaCloud
```

Gunakan perintah berikut untuk mendapatkan daftar lingkungan yang tersedia:

```azurepowershell-interactive
Get-AzureRmEnvironment | Select-Object Name
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
