---
title: Membuat prinsipal layanan Azure dengan Azure PowerShell
description: Pelajari cara membuat prinsipal layanan untuk aplikasi atau layanan dengan Azure PowerShell.
keywords: Azure PowerShell, Azure Active Directory, Azure Active directory, AD, RBAC
ms.devlang: powershell
ms.topic: conceptual
ms.date: 10/05/2021
ms.custom: devx-track-azurepowershell
ms.openlocfilehash: a9c97d6e5fb071640fde01db0267762f009e03aa
ms.sourcegitcommit: c489152c02cceaa5c8e284933af57f07c5350961
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/07/2021
ms.locfileid: "132429372"
---
# <a name="create-an-azure-service-principal-with-azure-powershell"></a>Membuat prinsipal layanan Azure dengan Azure PowerShell

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

Jika berencana mengelola aplikasi atau layanan dengan Azure PowerShell, Anda harus menjalankannya di bawah prinsipal layanan Azure Active Directory (AAD), bukan kredensial Anda sendiri. Artikel ini membantu Anda membuat pokok keamanan dengan Azure PowerShell.

> [!NOTE]
> Anda juga dapat membuat prinsipal layanan melalui portal Azure. Baca [Menggunakan portal untuk membuat aplikasi Direktori Aktif dan prinsipal layanan yang bisa mengakses sumber daya](/azure/azure-resource-manager/resource-group-create-service-principal-portal) untuk detail selengkapnya.

## <a name="what-is-a-service-principal"></a>Apa itu 'prinsipal layanan'?

Prinsipal layanan Azure adalah identitas keamanan yang digunakan oleh aplikasi, layanan, dan alat otomatisasi yang dibuat pengguna untuk mengakses sumber daya Azure tertentu. Anggaplah itu sebagai 'identitas pengguna' (nama pengguna dan kata sandi atau sertifikat) dengan peran tertentu, dan izin yang dikontrol secara ketat. Prinsipal layanan seharusnya hanya perlu melakukan hal-hal tertentu, tidak seperti identitas pengguna umum. Tindakan ini meningkatkan keamanan jika Anda hanya memberikan tingkat izin minimum yang diperlukan untuk menjalankan tugas manajemennya.

## <a name="verify-your-own-permission-level"></a>Memverifikasi tingkat izin Anda sendiri

Pertama, Anda harus memiliki izin yang memadai di Azure Active Directory dan langganan Azure. Anda harus dapat membuat aplikasi di Direktori Aktif dan menetapkan peran menjadi prinsipal layanan.

Cara termudah untuk memeriksa apakah akun Anda memiliki izin yang tepat adalah melalui portal. Lihat [Memeriksa izin yang diperlukan di portal](/azure/azure-resource-manager/resource-group-create-service-principal-portal#required-permissions).

## <a name="create-a-service-principal-for-your-app"></a>Membuat prinsipal layanan untuk aplikasi Anda

Setelah masuk ke akun Azure, Anda dapat membuat prinsipal layanan. Anda harus memiliki salah satu cara berikut untuk mengidentifikasi aplikasi yang Anda gunakan:

* Nama unik aplikasi yang Anda gunakan, seperti "MyDemoWebApp" dalam contoh berikut ini, atau
* ID Aplikasi, GUID unik yang terkait dengan aplikasi, layanan, atau objek yang disebarkan

### <a name="get-information-about-your-application"></a>Dapatkan informasi tentang aplikasi Anda

Cmdlet `Get-AzureRmADApplication` bisa digunakan untuk mendapatkan informasi tentang aplikasi Anda.

```azurepowershell
Get-AzureRmADApplication -DisplayNameStartWith MyDemoWebApp
```

```Output
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

```azurepowershell
$servicePrincipal = New-AzureRmADServicePrincipal -ApplicationId 00c01aaa-1603-49fc-b6df-b78c4e5138b4
```

```Output
Secret                : System.Security.SecureString
ServicePrincipalNames : {00c01aaa-1603-49fc-b6df-b78c4e5138b4, http://MyDemoWebApp}
ApplicationId         : 00c01aaa-1603-49fc-b6df-b78c4e5138b4
DisplayName           : MyDemoWebApp
Id                    : 698138e7-d7b6-4738-a866-b4e3081a69e4
AdfsId                :
Type                  : ServicePrincipal
```

Dari sini, Anda dapat menggunakan properti $servicePrincipal.Secret di Connect-AzureRmAccount (lihat "Masuk menggunakan prinsipal layanan" di bawah), atau dapat mengonversi String Aman ini menjadi string teks biasa untuk penggunaan nanti:

```powershell
$BSTR = [System.Runtime.InteropServices.Marshal]::SecureStringToBSTR($servicePrincipal.Secret)
$password = [System.Runtime.InteropServices.Marshal]::PtrToStringAuto($BSTR)
[Runtime.InteropServices.Marshal]::ZeroFreeBSTR($BSTR)
```

### <a name="sign-in-using-the-service-principal"></a>Masuk menggunakan prinsipal layanan

Anda kini dapat masuk sebagai prinsipal layanan baru untuk aplikasi menggunakan *appId yang* disediakan dan kata *sandi* yang dihasilkan secara otomatis. Anda juga memerlukan ID Penyewa untuk prinsipal layanan.
ID Penyewa Anda ditampilkan saat Anda masuk ke Azure dengan kredensial pribadi. Untuk masuk dengan prinsipal layanan, gunakan perintah berikut:

```azurepowershell-interactive
$cred = New-Object System.Management.Automation.PSCredential ("00c01aaa-1603-49fc-b6df-b78c4e5138b4", $servicePrincipal.Secret)
Connect-AzureRmAccount -Credential $cred -ServicePrincipal -TenantId 00000000-0000-0000-0000-000000000000
```

Setelah berhasil masuk, Anda akan melihat output seperti:

```Output
Environment           : AzureCloud
Account               : 00c01aaa-1603-49fc-b6df-b78c4e5138b4
TenantId              : 00000000-0000-0000-0000-000000000000
SubscriptionId        :
SubscriptionName      :
CurrentStorageAccount :
```

Selamat! Anda bisa menggunakan kredensial ini untuk menjalankan aplikasi Anda. Berikutnya, Anda perlu menyesuaikan izin prinsipal layanan.

## <a name="managing-roles"></a>Mengelola peran

> [!NOTE]
> Azure Role-Based Access Control (RBAC) adalah model untuk menetapkan dan mengelola peran bagi prinsipal pengguna dan layanan. Peran memiliki kumpulan izin yang terkait dengannya, yang menentukan sumber daya yang bisa dibaca, diakses, ditulis, atau dikelola oleh suatu prinsipal. Untuk informasi selengkapnya tentang RBAC dan peran, lihat [RBAC: Peran bawaan](/azure/active-directory/role-based-access-built-in-roles).

Azure PowerShell cmdlet berikut untuk mengelola penetapan peran:

* [Get-AzureRmRoleAssignment](/powershell/module/azurerm.resources/get-azurermroleassignment)
* [New-AzureRmRoleAssignment](/powershell/module/azurerm.resources/new-azurermroleassignment)
* [Remove-AzureRmRoleAssignment](/powershell/module/azurerm.resources/remove-azurermroleassignment)

Peran default untuk prinsipal layanan adalah **Kontributor.** Artikel ini mungkin bukan pilihan terbaik, tergantung pada lingkup interaksi aplikasi Anda dengan layanan Azure, dengan izin yang luas.
Peran **Pembaca** menjadi lebih terbatas dan dapat menjadi pilihan tepat untuk aplikasi baca-saja. Anda dapat menampilkan detail tentang izin khusus peran atau membuat izin kustom melalui portal Azure.

Dalam contoh ini, kami menambahkan **peran Pembaca** ke contoh kami sebelumnya, dan menghapus **kontributor:**

```azurepowershell
New-AzureRmRoleAssignment -ResourceGroupName myRG -ObjectId 698138e7-d7b6-4738-a866-b4e3081a69e4 -RoleDefinitionName Reader
```

```Output
RoleAssignmentId   : /subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/myRG/providers/Microsoft.Authorization/roleAssignments/818892f2-d075-46a1-a3a2-3a4e1a12fcd5
Scope              : /subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/myRG
DisplayName        : MyDemoWebApp
SignInName         :
RoleDefinitionName : Reader
RoleDefinitionId   : b24988ac-6180-42a0-ab88-20f7382dd24c
ObjectId           : 698138e7-d7b6-4738-a866-b4e3081a69e4
ObjectType         : ServicePrincipal
```

```azurepowershell
Remove-AzureRmRoleAssignment -ResourceGroupName myRG -ObjectId 698138e7-d7b6-4738-a866-b4e3081a69e4 -RoleDefinitionName Contributor
```

Untuk melihat peran saat ini ditetapkan:

```azurepowershell
Get-AzureRmRoleAssignment -ResourceGroupName myRG -ObjectId 698138e7-d7b6-4738-a866-b4e3081a69e4
```

```Output
RoleAssignmentId   : /subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/myRG/providers/Microsoft.Authorization/roleAssignments/0906bbd8-9982-4c03-8dae-aeaae8b13f9e
Scope              : /subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/myRG
DisplayName        : MyDemoWebApp
SignInName         :
RoleDefinitionName : Reader
RoleDefinitionId   : acdd72a7-3385-48ef-bd42-f606fba81ae7
ObjectId           : 698138e7-d7b6-4738-a866-b4e3081a69e4
ObjectType         : ServicePrincipal
```

Cmdlet Azure PowerShell cmdlet untuk manajemen peran:

* [Get-AzureRmRoleDefinition](/powershell/module/azurerm.resources/Get-AzureRmRoleDefinition)
* [New-AzureRmRoleDefinition](/powershell/module/azurerm.resources/New-AzureRmRoleDefinition)
* [Remove-AzureRmRoleDefinition](/powershell/module/azurerm.resources/Remove-AzureRmRoleDefinition)
* [Set-AzureRmRoleDefinition](/powershell/module/azurerm.resources/Set-AzureRmRoleDefinition)

## <a name="change-the-credentials-of-the-security-principal"></a>Mengubah kredensial prinsipal keamanan

Merupakan praktik keamanan yang baik untuk meninjau izin dan memperbarui kata sandi secara teratur. Anda mungkin juga ingin mengelola dan mengubah kredensial keamanan saat aplikasi berubah. Misalnya, kami dapat mengubah kata sandi prinsipal layanan dengan membuat kata sandi baru dan menghapus yang lama.

### <a name="add-a-new-password-for-the-service-principal"></a>Menambahkan kata sandi baru untuk prinsipal layanan

```azurepowershell
New-AzureRmADSpCredential -ServicePrincipalName http://MyDemoWebApp
```

```Output
Secret    : System.Security.SecureString
StartDate : 11/16/2018 12:38:23 AM
EndDate   : 11/16/2019 12:38:23 AM
KeyId     : 6f801c3e-6fcd-42b9-be8e-320b17ba1d36
Type      : Password
```

### <a name="get-a-list-of-credentials-for-the-service-principal"></a>Mendapatkan daftar kredensial untuk prinsipal layanan

```azurepowershell
Get-AzureRmADSpCredential -ServicePrincipalName http://MyDemoWebApp
```

```Output
StartDate           EndDate             KeyId                                Type
---------           -------             -----                                ----
3/8/2017 5:58:24 PM 3/8/2018 5:58:24 PM 6f801c3e-6fcd-42b9-be8e-320b17ba1d36 Password
5/5/2016 4:55:27 PM 5/5/2017 4:55:27 PM ca9d4846-4972-4c70-b6f5-a4effa60b9bc Password
```

### <a name="remove-the-old-password-from-the-service-principal"></a>Menghapus kata sandi lama dari prinsipal layanan

```azurepowershell
Remove-AzureRmADSpCredential -ServicePrincipalName http://MyDemoWebApp -KeyId ca9d4846-4972-4c70-b6f5-a4effa60b9bc
```

```Output
Confirm
Are you sure you want to remove credential with keyId '6f801c3e-6fcd-42b9-be8e-320b17ba1d36' for
service principal objectId '698138e7-d7b6-4738-a866-b4e3081a69e4'.
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): Y
```

### <a name="verify-the-list-of-credentials-for-the-service-principal"></a>Memverifikasi daftar kredensial untuk prinsipal layanan

```azurepowershell
Get-AzureRmADSpCredential -ServicePrincipalName http://MyDemoWebApp
```

```output
StartDate           EndDate             KeyId                                Type
---------           -------             -----                                ----
3/8/2017 5:58:24 PM 3/8/2018 5:58:24 PM 6f801c3e-6fcd-42b9-be8e-320b17ba1d36 Password
```

### <a name="get-information-about-the-service-principal"></a>Dapatkan informasi tentang prinsipal layanan

```azurepowershell
$svcprincipal = Get-AzureRmADServicePrincipal -ObjectId 698138e7-d7b6-4738-a866-b4e3081a69e4
$svcprincipal | Select-Object -Property *
```

```Output
ServicePrincipalNames : {http://MyDemoWebApp, 00c01aaa-1603-49fc-b6df-b78c4e5138b4}
ApplicationId         : 00c01aaa-1603-49fc-b6df-b78c4e5138b4
DisplayName           : MyDemoWebApp
Id                    : 698138e7-d7b6-4738-a866-b4e3081a69e4
Type                  : ServicePrincipal
```
