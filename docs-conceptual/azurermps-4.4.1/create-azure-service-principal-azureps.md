---
title: Membuat prinsipal layanan Azure dengan Microsoft Azure PowerShell
description: Pelajari cara membuat prinsipal layanan untuk aplikasi atau layanan Anda dengan Azure PowerShell.
keywords: Azure PowerShell, Azure Active Directory, direktori Azure Active, AD, RBAC
ms.devlang: powershell
ms.topic: conceptual
ms.date: 05/15/2017
ms.custom: devx-track-azurepowershell
ms.openlocfilehash: 225ee512e09ccc2afbe4e632a3257d91ce9deb5c
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132428305"
---
# <a name="create-an-azure-service-principal-with-azure-powershell"></a>Membuat prinsipal layanan Azure dengan Microsoft Azure PowerShell

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

Jika Anda berencana untuk mengelola aplikasi atau layanan dengan Azure PowerShell, Anda harus menjalankannya pada prinsipal layanan Azure Active Directory (AAD), bukan kredensial Anda sendiri. Topik ini akan menjelaskan cara membuat prinsipal keamanan dengan Azure PowerShell.

> [!NOTE]
> Anda juga dapat membuat prinsipal layanan melalui portal Microsoft Azure. Untuk informasi selengkapnya, baca [Menggunakan portal untuk membuat aplikasi dan prinsipal layanan Active Directory yang dapat mengakses sumber daya](/azure/azure-resource-manager/resource-group-create-service-principal-portal).

## <a name="what-is-a-service-principal"></a>Apa itu prinsipal layanan?

Perwakilan layanan Azure adalah identitas keamanan yang digunakan oleh aplikasi, layanan, dan alat otomatisasi yang dibuat pengguna untuk mengakses sumber daya Azure tertentu. Anggaplah sebagai "identitas pengguna" (nama pengguna dan kata sandi atau sertifikat) dengan peran tertentu, dan izin yang dikontrol dengan ketat. Prinsipal layanan hanya perlu dapat melakukan hal-hal tertentu, tidak seperti identitas pengguna umum. Prinsipal layanan meningkatkan keamanan jika Anda hanya memberinya tingkat izin minimum yang diperlukan untuk melakukan tugas pengelolaan.

## <a name="verify-your-own-permission-level"></a>Memverifikasi tingkat izin Anda sendiri

Pertama, Anda harus memiliki izin yang cukup di Azure Active Directory dan langganan Azure Anda. Khususnya, Anda harus mampu membuat aplikasi diActive Directory, dan menetapkan peran ke prinsipal layanan.

Cara termudah untuk memeriksa apakah akun Anda memiliki izin yang memadai adalah melalui portal. Lihat [Memeriksa izin yang diperlukan di portal](/azure/azure-resource-manager/resource-group-create-service-principal-portal#required-permissions).

## <a name="create-a-service-principal-for-your-app"></a>Membuat prinsipal layanan untuk aplikasi Anda

Setelah Anda masuk ke akun Azure, Anda dapat membuat prinsipal layanan. Anda harus memiliki salah satu cara berikut untuk mengidentifikasi aplikasi yang disebarkan:

* Nama unik aplikasi yang Anda sebarkan, seperti "MyDemoWebApp" dalam contoh berikut, atau
* ID Aplikasi, GUID unik yang terkait dengan aplikasi, layanan, atau objek yang disebarkan

### <a name="get-information-about-your-application"></a>Mendapatkan informasi tentang aplikasi Anda

Cmdlet `Get-AzureRmADApplication` dapat digunakan untuk menemukan informasi tentang aplikasi Anda.

```powershell-interactive
Get-AzureRmADApplication -DisplayNameStartWith MyDemoWebApp
```

```output
DisplayName             : MyDemoWebApp
ObjectId                : 775f64cd-0ec8-4b9b-b69a-8b8946022d9f
IdentifierUris          : {http://MyDemoWebApp}
HomePage                : http://www.contoso.com
Type                    : Application
ApplicationId           : 00c01aaa-1603-49fc-b6df-b78c4e5138b4
AvailableToOtherTenants : False
AppPermissions          :
ReplyUrls               : {}
```

### <a name="create-a-service-principal-for-your-application"></a>Membuat prinsipal layanan untuk aplikasi Anda

Cmdlet `New-AzureRmADServicePrincipal` digunakan untuk membuat prinsipal layanan.

```powershell-interactive
Add-Type -Assembly System.Web
$password = [System.Web.Security.Membership]::GeneratePassword(16,3)
New-AzureRmADServicePrincipal -ApplicationId 00c01aaa-1603-49fc-b6df-b78c4e5138b4 -Password $password
```

```output
DisplayName                    Type                           ObjectId
-----------                    ----                           --------
MyDemoWebApp                   ServicePrincipal               698138e7-d7b6-4738-a866-b4e3081a69e4
```

### <a name="get-information-about-the-service-principal"></a>Mendapatkan informasi tentang prinsipal layanan

```powershell-interactive
$svcprincipal = Get-AzureRmADServicePrincipal -ObjectId 698138e7-d7b6-4738-a866-b4e3081a69e4
$svcprincipal | Select-Object *
```

```output
ServicePrincipalNames : {http://MyDemoWebApp, 00c01aaa-1603-49fc-b6df-b78c4e5138b4}
ApplicationId         : 00c01aaa-1603-49fc-b6df-b78c4e5138b4
DisplayName           : MyDemoWebApp
Id                    : 698138e7-d7b6-4738-a866-b4e3081a69e4
Type                  : ServicePrincipal
```

### <a name="sign-in-using-the-service-principal"></a>Masuk menggunakan prinsipal layanan

Anda sekarang dapat masuk sebagai prinsipal layanan baru untuk aplikasi Anda menggunakan *appId* dan *kata sandi* yang Anda berikan. Anda perlu memberikan ID Penyewa untuk akun Anda. ID Penyewa ditampilkan saat Anda masuk ke Azure dengan kredensial pribadi Anda.

```powershell-interactive
$cred = Get-Credential -UserName $svcprincipal.ApplicationId -Message "Enter Password"
Login-AzureRmAccount -Credential $cred -ServicePrincipal -TenantId XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX
```

Jalankan perintah ini dari sesi PowerShell baru. Setelah berhasil masuk, Anda melihat output seperti ini:

```output
Environment           : AzureCloud
Account               : 00c01aaa-1603-49fc-b6df-b78c4e5138b4
TenantId              : XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX
SubscriptionId        :
SubscriptionName      :
CurrentStorageAccount :
```

Selamat! Anda dapat menggunakan kredensial ini untuk menjalankan aplikasi Anda. Selanjutnya, Anda perlu menyesuaikan izin prinsipal layanan.

## <a name="managing-roles"></a>Mengelola peran

> [!NOTE]
> Azure Role-Based Access Control (RBAC) adalah model untuk menentukan dan mengelola peran pengguna dan prinsipal layanan. Peran memiliki serangkaian izin yang terkait dengannya, yang menentukan sumber daya yang dapat dibaca, diakses, ditulis, atau dikelola oleh prinsipal. Untuk informasi selengkapnya tentang RBAC dan peran, lihat [RBAC: Peran bawaan](/azure/active-directory/role-based-access-built-in-roles).

Azure PowerShell menyediakan cmdlet berikut untuk mengelola penetapan peran:

* [Get-AzureRmRoleAssignment](/powershell/module/azurerm.resources/get-azurermroleassignment)
* [New-AzureRmRoleAssignment](/powershell/module/azurerm.resources/new-azurermroleassignment)
* [Remove-AzureRmRoleAssignment](/powershell/module/azurerm.resources/remove-azurermroleassignment)

Peran default untuk prinsipal layanan adalah **Kontributor**. Peran ini mungkin bukan pilihan terbaik tergantung pada ruang lingkup interaksi aplikasi Anda dengan layanan Azure, mengingat izinnya yang luas.
Peran **Pembaca** lebih ketat dan dapat menjadi pilihan yang baik untuk aplikasi baca-saja. Anda dapat melihat detail tentang izin khusus peran atau membuat peran khusus melalui portal Azure.

Dalam contoh ini, kami menambahkan peran **Pembaca** ke contoh sebelumnya, dan menghapus **Kontributor**:

```powershell-interactive
New-AzureRmRoleAssignment -ResourceGroupName myRG -ObjectId 698138e7-d7b6-4738-a866-b4e3081a69e4 -RoleDefinitionName Reader
```

```output
RoleAssignmentId   : /subscriptions/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX/resourceGroups/myRG/providers/Microsoft.Authorization/roleAssignments/818892f2-d075-46a1-a3a2-3a4e1a12fcd5
Scope              : /subscriptions/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX/resourceGroups/myRG
DisplayName        : MyDemoWebApp
SignInName         :
RoleDefinitionName : Reader
RoleDefinitionId   : b24988ac-6180-42a0-ab88-20f7382dd24c
ObjectId           : 698138e7-d7b6-4738-a866-b4e3081a69e4
ObjectType         : ServicePrincipal
```

```powershell-interactive
Remove-AzureRmRoleAssignment -ResourceGroupName myRG -ObjectId 698138e7-d7b6-4738-a866-b4e3081a69e4 -RoleDefinitionName Contributor
```

Untuk melihat peran yang ditetapkan saat ini:

```powershell-interactive
Get-AzureRmRoleAssignment -ResourceGroupName myRG -ObjectId 698138e7-d7b6-4738-a866-b4e3081a69e4
```

```output
RoleAssignmentId   : /subscriptions/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX/resourceGroups/myRG/providers/Microsoft.Authorization/roleAssignments/0906bbd8-9982-4c03-8dae-aeaae8b13f9e
Scope              : /subscriptions/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX/resourceGroups/myRG
DisplayName        : MyDemoWebApp
SignInName         :
RoleDefinitionName : Reader
RoleDefinitionId   : acdd72a7-3385-48ef-bd42-f606fba81ae7
ObjectId           : 698138e7-d7b6-4738-a866-b4e3081a69e4
ObjectType         : ServicePrincipal
```

Cmdlet Azure PowerShell lainnya untuk manajemen peran:

* [Get-AzureRmRoleDefinition](/powershell/module/azurerm.resources/Get-AzureRmRoleDefinition)
* [New-AzureRmRoleDefinition](/powershell/module/azurerm.resources/New-AzureRmRoleDefinition)
* [Remove-AzureRmRoleDefinition](/powershell/module/azurerm.resources/Remove-AzureRmRoleDefinition)
* [Set-AzureRmRoleDefinition](/powershell/module/azurerm.resources/Set-AzureRmRoleDefinition)

## <a name="change-the-credentials-of-the-security-principal"></a>Mengubah kredensial prinsipal keamanan

Meninjau izin dan memperbarui kata sandi secara berkala merupakan praktik keamanan yang baik. Sebaiknya Anda juga mengelola dan mengubah kredensial keamanan saat aplikasi Anda berubah. Misalnya, kita dapat mengubah kata sandi prinsipal layanan dengan membuat kata sandi baru dan menghapus yang lama.

### <a name="add-a-new-password-for-the-service-principal"></a>Menambahkan kata sandi baru untuk prinsipal layanan

```powershell-interactive
$password = [System.Web.Security.Membership]::GeneratePassword(16,3)
New-AzureRmADSpCredential -ServicePrincipalName http://MyDemoWebApp -Password $password
```

```output
StartDate           EndDate             KeyId                                Type
---------           -------             -----                                ----
3/8/2017 5:58:24 PM 3/8/2018 5:58:24 PM 6f801c3e-6fcd-42b9-be8e-320b17ba1d36 Password
```

### <a name="get-a-list-of-credentials-for-the-service-principal"></a>Mendapatkan daftar kredensial untuk prinsipal layanan

```powershell-interactive
Get-AzureRmADSpCredential -ServicePrincipalName http://MyDemoWebApp
```

```output
StartDate           EndDate             KeyId                                Type
---------           -------             -----                                ----
3/8/2017 5:58:24 PM 3/8/2018 5:58:24 PM 6f801c3e-6fcd-42b9-be8e-320b17ba1d36 Password
5/5/2016 4:55:27 PM 5/5/2017 4:55:27 PM ca9d4846-4972-4c70-b6f5-a4effa60b9bc Password
```

### <a name="remove-the-old-password-from-the-service-principal"></a>Menghapus kata sandi lama dari prinsipal layanan

```powershell-interactive
Remove-AzureRmADSpCredential -ServicePrincipalName http://MyDemoWebApp -KeyId ca9d4846-4972-4c70-b6f5-a4effa60b9bc
```

```output
Confirm
Are you sure you want to remove credential with keyId '6f801c3e-6fcd-42b9-be8e-320b17ba1d36' for
service principal objectId '698138e7-d7b6-4738-a866-b4e3081a69e4'.
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): Y
```

### <a name="verify-the-list-of-credentials-for-the-service-principal"></a>Memverifikasi daftar kredensial untuk prinsipal layanan

```powershell-interactive
Get-AzureRmADSpCredential -ServicePrincipalName http://MyDemoWebApp
```

```output
StartDate           EndDate             KeyId                                Type
---------           -------             -----                                ----
3/8/2017 5:58:24 PM 3/8/2018 5:58:24 PM 6f801c3e-6fcd-42b9-be8e-320b17ba1d36 Password
```
