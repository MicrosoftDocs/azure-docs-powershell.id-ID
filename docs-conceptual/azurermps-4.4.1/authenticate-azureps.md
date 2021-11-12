---
title: Masuk dengan Azure PowerShell
description: Cara masuk dengan pengguna Azure PowerShell pengguna, prinsipal layanan, atau dengan identitas yang dikelola untuk sumber daya Azure.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 05/15/2017
ms.custom: devx-track-azurepowershell
ms.openlocfilehash: b0abbeb0eb54db010193c4676465b9359a355627
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132428307"
---
# <a name="sign-in-with-azure-powershell"></a>Masuk dengan Azure PowerShell

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

Azure PowerShell mendukung beberapa metode autentikasi. Cara termudah untuk memulai adalah masuk secara interaktif di baris perintah.

## <a name="sign-in-interactively"></a>Masuk secara interaktif

Untuk masuk secara interaktif, gunakan cmdlet [Koneksi-AzureRmAccount.](/powershell/module/azurerm.profile/connect-azurermaccount)

```azurepowershell-interactive
Connect-AzureRmAccount
```

Saat dijalankan, cmdlet ini akan muncul dalam kotak dialog yang meminta alamat email dan kata sandi terkait dengan akun Azure Anda. Saat mengautentikasi, informasi tersebut disimpan untuk sesi PowerShell saat ini, dialog ditutup, dan Anda memiliki akses ke semua cmdlet Azure PowerShell cmdlet.

> [!IMPORTANT]
> Sejak Azure PowerShell 6.3.0, kredensial Anda dibagikan di antara beberapa sesi PowerShell selama Anda tetap masuk ke Windows. Untuk informasi selengkapnya, lihat artikel tentang [Kredensial Tetap.](context-persistence.md)

## <a name="sign-in-with-a-service-principal"></a>Masuk dengan prinsipal layanan

Prinsipal layanan menyediakan cara bagi Anda untuk membuat akun non-interaktif yang bisa Anda gunakan untuk memanipulasi sumber daya. Prinsipal layanan adalah seperti akun pengguna di mana Anda bisa menerapkan aturan menggunakan Azure Active Directory. Dengan memberikan izin minimum yang diperlukan untuk prinsipal layanan, Anda dapat memastikan skrip otomatisasi jauh lebih aman.

Jika Anda perlu membuat prinsipal layanan untuk digunakan dengan Azure PowerShell, lihat [Membuat prinsipal layanan Azure dengan Azure PowerShell](create-azure-service-principal-azureps.md).

Untuk masuk dengan prinsipal layanan, gunakan `-ServicePrincipal` argumen dengan `Connect-AzureRmAccount` cmdlet. Anda juga akan memerlukan ID aplikasi princpal layanan, kredensial masuk, dan ID penyewa terkait dengan prinsipal layanan. Untuk mendapatkan kredensial prinsipal layanan sebagai objek yang sesuai, gunakan cmdlet [Get-Credential.](/powershell/module/microsoft.powershell.security/get-credential) Cmdlet ini akan menampilkan kotak dialog untuk memasukkan ID pengguna dan kata sandi prinsipal layanan.

```azurepowershell-interactive
$pscredential = Get-Credential
Connect-AzureRmAccount -ServicePrincipal -ApplicationId  "http://my-app" -Credential $pscredential -TenantId $tenantid
```

## <a name="sign-in-using-managed-identities-for-azure-resources"></a>Masuk menggunakan identitas terkelola untuk sumber daya Azure

Identitas terkelola untuk sumber daya Azure adalah fitur penting Azure Active Directory. Anda dapat menggunakan prinsipal layanan identitas terkelola untuk masuk, dan memperoleh token akses aplikasi-saja untuk mengakses sumber daya lainnya. Identitas yang dikelola hanya tersedia pada mesin virtual yang berjalan di awan Azure.

Untuk informasi selengkapnya tentang identitas terkelola untuk sumber daya Azure, lihat Cara menggunakan identitas terkelola untuk sumber daya Azure di [Azure VM untuk memperoleh token akses.](/azure/active-directory/managed-identities-azure-resources/how-to-use-vm-token)

## <a name="sign-in-to-another-cloud"></a>Masuk ke Cloud lain

Layanan cloud Azure menyediakan lingkungan berbeda yang mematuhi regulasi penanganan data di berbagai kawasan. Jika akun Azure anda berada di awan yang terkait dengan salah satu wilayah ini, Anda perlu menentukan lingkungan ketika Anda masuk. Misalnya, jika akun Anda berada di awan Tiongkok, Anda masuk menggunakan perintah berikut:

```azurepowershell-interactive
Login-AzureRmAccount -EnvironmentName AzureChinaCloud
```

Gunakan perintah berikut untuk mendapatkan daftar lingkungan yang tersedia:

```azurepowershell-interactive
Get-AzureRmEnvironment | Select-Object Name
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
