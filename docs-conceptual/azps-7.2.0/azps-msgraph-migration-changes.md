---
title: Azure AD ke Microsoft Graph perubahan migrasi di Azure PowerShell
description: Panduan migrasi ini berisi daftar perubahan Azure PowerShell untuk migrasi Azure AD ke Microsoft Graph di Az.Resources 5.1.0.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 01/06/2022
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
ms.openlocfilehash: bdf942543539bcf00cd01d8274cb0ada7b90aa70
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138335042"
---
# <a name="azure-ad-to-microsoft-graph-migration-changes-in-azure-powershell"></a>Azure AD ke Microsoft Graph perubahan migrasi di Azure PowerShell

Modul `Az.Resources` PowerShell versi 5.1.0 dari Azure PowerShell memperkenalkan perubahan pada cmdlet terkait identitas. Cmdlet yang mengandalkan Graph Azure AD beralih ke Microsoft Graph. Perubahan ini terjadi untuk memastikan transisi yang lancar mengingat [pengumuman pensiunnya Azure AD Graph](https://azure.microsoft.com/updates/update-your-apps-to-use-microsoft-graph-before-30-june-2022/).
Untuk informasi selengkapnya, lihat [Azure AD ke Microsoft Graph migrasi untuk alat baris perintah Azure](https://techcommunity.microsoft.com/t5/azure-tools/azure-ad-to-microsoft-graph-migration-for-azure-command-line/ba-p/2836666).

Contoh berikut menginstal versi terbaru dari `Az.Resources` modul Azure PowerShell.

```azurepowershell
Install-Module -Name Az.Resources -Repository PSGallery -Scope CurrentUser
```

Lihat informasi berikut untuk daftar perubahan.

## <a name="application"></a>Aplikasi

### <a name="get-azadapplication"></a>Get-AzAdApplication

- Jenis output telah diubah dari `Microsoft.Azure.Commands.ActiveDirectory.PSADApplication` ke `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphApplication`

- Parameter `IncludeTotalCount` tidak didukung dan telah dihapus

### <a name="new-azadapplication"></a>New-AzAdApplication

- Jenis output telah diubah dari `Microsoft.Azure.Commands.ActiveDirectory.PSADApplication` ke `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphApplication`

- Parameter `Password` telah dihapus, kata sandi yang disesuaikan tidak didukung lagi, server menetapkan teks rahasia saat pembuatan

### <a name="remove-azadapplication"></a>Remove-AzAdApplication

- Jenis parameter input `InputObject` telah diubah dari `Microsoft.Azure.Commands.ActiveDirectory.PSADApplication` ke `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphApplication`

### <a name="update-azadapplication"></a>Update-AzAdApplication

- Jenis parameter input `InputObject` telah diubah dari `Microsoft.Azure.Commands.ActiveDirectory.PSADApplication` ke `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphApplication`

- Jenis output telah diubah dari `Microsoft.Azure.Commands.ActiveDirectory.PSADApplication` ke `System.Boolean`

### <a name="changes-to-application-object"></a>Perubahan pada Objek Aplikasi

- `ObjectId` telah digantikan oleh `Id`

- `HomePage` telah digantikan oleh `HomepageUrl` dalam `Web` elemen

- `ApplicationId` telah digantikan oleh `AppId`

- `AvailableToOtherTenants` (boolean) telah digantikan oleh `SignInAudience` (string dengan 4 nilai: 'AzureADMyOrg', 'AzureADMultipleOrgs', 'AzureADandPersonalMicrosoftAccount', 'PersonalMicrosoftAccount')

  - AzureADMultipleOrgs setara dengan AvailableToOtherTenants:$true

  - AzureAdMyOrg setara dengan AvailableToOtherTenants:$false atau $null

- `ApiPermissions` telah digantikan oleh `RequiredResourceAccess`

- `ReplyUrls` telah digantikan oleh `RedirectUris ` dalam `Web` elemen

- `ObjectType` telah digantikan oleh `OdataType`

## <a name="application-credential"></a>Kredensial Aplikasi

### <a name="get-azadappcredential"></a>Get-AzAdAppCredential

- Jenis parameter input `ApplicationObject` telah diubah dari `Microsoft.Azure.Commands.ActiveDirectory.PSADApplication` ke `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphApplication`

- Jenis output telah diubah dari `Microsoft.Azure.Commands.ActiveDirectory. PSADCredential` ke `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphKeyCredential`
  dan `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphPasswordCredential`

### <a name="new-azadappcredential"></a>New-AzAdAppCredential

- Jenis parameter input `ApplicationObject` telah diubah dari `Microsoft.Azure.Commands.ActiveDirectory.PSADApplication` ke `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphApplication`

- Jenis output telah diubah dari `Microsoft.Azure.Commands.ActiveDirectory. PSADCredential` ke `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphKeyCredential`
  dan `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphPasswordCredential`

- Parameter `Password` telah dihapus, kata sandi yang disesuaikan tidak didukung lagi, server akan menetapkan teks rahasia saat pembuatan

### <a name="remove-azadappcredential"></a>Remove-AzAdAppCredential

- Jenis parameter input `ApplicationObject` telah diubah dari `Microsoft.Azure.Commands.ActiveDirectory.PSADApplication` ke `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphApplication`

### <a name="changes-to-app-credential-object"></a>Perubahan pada Objek Kredensial Aplikasi

#### <a name="password-credential"></a>Kredensial Kata Sandi
- `Password` telah digantikan oleh `SecretText`

#### <a name="key-credential"></a>Kredensial Kunci
- `CertValue` telah dihapus

## <a name="serviceprincipal"></a>ServicePrincipal

### <a name="get-azadserviceprincipal"></a>Get-AzAdServicePrincipal

- Jenis output telah diubah dari `Microsoft.Azure.Commands.ActiveDirectory.PSADServicePrincipal` ke `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphServicePrincipal`

- Parameter `IncludeTotalCount` tidak didukung dan telah dihapus.

### <a name="new-azadserviceprincipal"></a>New-AzAdServicePrincipal

- Jenis output telah diubah dari `Microsoft.Azure.Commands.ActiveDirectory.PSADServicePrincipal` ke `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphServicePrincipal`

- Parameter set `ApplicationWithoutCredentialParameterSet`, `ApplicationWithPasswordPlainParameterSet`, `DisplayNameWithoutCredentialParameterSet`, , telah `DisplayNameWithPasswordPlainParameterSet` dihapus karena set parameter asli tidak berfungsi.

- Peran `contributor` tidak ditetapkan sebagai default ketika parameter `-Role` tidak disediakan karena pertimbangan keamanan.

- Parameter `SkipAssignment` telah dihapus.

### <a name="remove-azadserviceprincipal"></a>Remove-AzAdServicePrincipal

- Jenis parameter input `ApplicationObject` telah diubah dari `Microsoft.Azure.Commands.ActiveDirectory.PSADApplication` ke `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphApplication`

- Jenis parameter input `InputObject` telah diubah dari `Microsoft.Azure.Commands.ActiveDirectory.PSADServicePrincipal` ke `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphServicePrincipal`

### <a name="update-azadserviceprincipal"></a>Update-AzAdServicePrincipal

- Jenis parameter input `InputObject` telah diubah dari `Microsoft.Azure.Commands.ActiveDirectory.PSADServicePrincipal` ke `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphServicePrincipal`

- Jenis output telah diubah dari `Microsoft.Azure.Commands.ActiveDirectory.PSADServicePrincipal` ke `System.Boolean`

### <a name="changes-to-service-principal-object"></a>Perubahan pada Objek Utama Layanan

- `ApplicationId` telah digantikan oleh `AppId`

- `ObjectType` telah digantikan oleh `OdataType`

## <a name="serviceprincipal-credential"></a>Kredensial ServicePrincipal

### <a name="get-azadspcredential"></a>Get-AzAdSpCredential

- Jenis parameter input `ServicePrincipalObject` telah diubah dari `Microsoft.Azure.Commands.ActiveDirectory.PSADServicePrincipal` ke `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphServicePrincipal`

- Jenis output telah diubah dari `Microsoft.Azure.Commands.ActiveDirectory. PSADCredential` ke `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphKeyCredential`
  dan `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphPasswordCredential`

### <a name="new-azadspcredential"></a>New-AzAdSpCredential

- Jenis parameter input `ServicePrincipalObject` telah diubah dari `Microsoft.Azure.Commands.ActiveDirectory.PSADServicePrincipal` ke `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphServicePrincipal`

- Jenis output telah diubah dari `Microsoft.Azure.Commands.ActiveDirectory. PSADCredential` ke `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphKeyCredential`
  dan `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphPasswordCredential`

### <a name="remove-azadspcredential"></a>Remove-AzAdSpCredential

- Jenis parameter input `ServicePrincipalObject` telah diubah dari `Microsoft.Azure.Commands.ActiveDirectory.PSADServicePrincipal` ke `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphServicePrincipal`

### <a name="changes-to-serviceprincipal-credential-object"></a>Perubahan pada Objek Kredensial ServicePrincipal

#### <a name="password-credential"></a>Kredensial Kata Sandi
- `Password` telah digantikan oleh `SecretText`

#### <a name="key-credential"></a>Kredensial Kunci
- `CertValue` telah dihapus

## <a name="user"></a>Pengguna

### <a name="get-azaduser"></a>Get-AzAdUser

- Jenis output telah diubah dari `Microsoft.Azure.Commands.ActiveDirectory.PSADUser` ke `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphUser`

- Parameter `IncludeTotalCount` tidak didukung dan telah dihapus

### <a name="new-azaduser"></a>New-AzAdUser

- Jenis output telah diubah dari `Microsoft.Azure.Commands.ActiveDirectory.PSADUser` ke `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphUser`

### <a name="remove-azaduser"></a>Remove-AzAdUser

- Jenis parameter input `InputObject` telah diubah dari `Microsoft.Azure.Commands.ActiveDirectory.PSADUser` ke `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphUser`

### <a name="update-azaduser"></a>Update-AzAdUser

- Jenis parameter input `InputObject` telah diubah dari `Microsoft.Azure.Commands.ActiveDirectory.PSADUser` ke `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphUser`

- Jenis output telah diubah dari `Microsoft.Azure.Commands.ActiveDirectory.PSADUser` ke `System.Boolean`

### <a name="changes-to-user-object"></a>Perubahan pada Objek Pengguna

- `ObjectType` telah digantikan oleh `OdataType`

- `ImmutableId` telah digantikan oleh `OnpremisesImmutableId`

## <a name="group"></a>Grup

### <a name="get-azadgroup"></a>Get-AzAdGroup

- Jenis output telah diubah dari `Microsoft.Azure.Commands.ActiveDirectory.PSADGroup` ke `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphGroup`

- Parameter `IncludeTotalCount` tidak didukung dan telah dihapus

### <a name="new-azadgroup"></a>New-AzAdGroup

- Jenis output telah diubah dari `Microsoft.Azure.Commands.ActiveDirectory.PSADGroup` ke `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphGroup`

### <a name="remove-azadgroup"></a>Remove-AzAdGroup

- Jenis parameter input `InputObject` telah diubah dari `Microsoft.Azure.Commands.ActiveDirectory.PSADGroup` ke `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphGroup`

### <a name="changes-of-group-object"></a>Perubahan Objek Grup

- `ObjectType` telah digantikan oleh `OdataType`

## <a name="group-member"></a>Anggota grup

### <a name="get-azadgroupmember"></a>Get-AzAdGroupMember

- Jenis output telah diubah dari `Microsoft.Azure.Commands.ActiveDirectory.PSADObject` ke `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphDirectoryObject`

- Parameter `IncludeTotalCount` telah dihapus

- Jenis parameter input `GroupObject` telah diubah dari `Microsoft.Azure.Commands.ActiveDirectory.PSADGroup` ke `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphGroup`

[!INCLUDE [get-azadgroupmember-no-serviceprincipal-banner](../../includes/get-azadgroupmember-no-serviceprincipal-banner.md)]

### <a name="add-azadgroupmember"></a>Add-AzAdGroupMember

- Jenis parameter input `GroupObject` telah diubah dari `Microsoft.Azure.Commands.ActiveDirectory.PSADGroup` ke `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphGroup`

### <a name="remove-azadgroupmember"></a>Remove-AzAdGroupMember

- Jenis parameter input `GroupObject` telah diubah dari `Microsoft.Azure.Commands.ActiveDirectory.PSADGroup` ke `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphGroup`
