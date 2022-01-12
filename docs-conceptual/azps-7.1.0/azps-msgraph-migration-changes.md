---
title: Perubahan migrasi Azure AD ke Microsoft Graph di Azure PowerShell
description: Panduan migrasi ini berisi daftar perubahan Azure PowerShell Azure AD ke Microsoft Graph di Az.Resources 5.1.0.
ms.devlang: powershell
ms.topic: conceptual
ms.date: 01/06/2022
ms.custom: devx-track-azurepowershell
ms.service: azure-powershell
ms.openlocfilehash: 3c1c64586f923b724596771ff87dca19c9a9b730
ms.sourcegitcommit: e109cc5320478db6aa8a52d49996b133007a65b9
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 01/12/2022
ms.locfileid: "135958390"
---
# <a name="azure-ad-to-microsoft-graph-migration-changes-in-azure-powershell"></a>Perubahan migrasi Azure AD ke Microsoft Graph di Azure PowerShell

Modul `Az.Resources` PowerShell versi 5.1.0 dari Azure PowerShell memperkenalkan perubahan pada cmdlet yang terkait dengan identitas. Cmdlet yang mengandalkan Azure AD Graph akan beralih ke Microsoft Graph. Perubahan ini terjadi untuk memastikan transisi yang lancar ketika pengumuman pensiun [Azure AD Graph](https://azure.microsoft.com/updates/update-your-apps-to-use-microsoft-graph-before-30-june-2022/).
Untuk informasi selengkapnya, lihat [Azure AD ke Microsoft Graph migrasi untuk alat baris perintah Azure.](https://techcommunity.microsoft.com/t5/azure-tools/azure-ad-to-microsoft-graph-migration-for-azure-command-line/ba-p/2836666)

Contoh berikut ini menginstal versi terbaru modul `Az.Resources` Azure PowerShell.

```azurepowershell
Install-Module -Name Az.Resources -Repository PSGallery -Scope CurrentUser
```

Lihat informasi berikut ini untuk daftar perubahan.

## <a name="application"></a>Aplikasi

### <a name="get-azadapplication"></a>Get-AzAdApplication

- Tipe output telah diubah `Microsoft.Azure.Commands.ActiveDirectory.PSADApplication` dari ke `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphApplication`

- Parameter `IncludeTotalCount` tidak didukung dan telah dihapus

### <a name="new-azadapplication"></a>New-AzAdApplication

- Tipe output telah diubah `Microsoft.Azure.Commands.ActiveDirectory.PSADApplication` dari ke `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphApplication`

- Parameter `Password` telah dihapus, kata sandi yang dikustomisasi tidak lagi didukung, server menetapkan teks rahasia saat pembuatan

### <a name="remove-azadapplication"></a>Remove-AzAdApplication

- Tipe input parameter `InputObject` telah diubah `Microsoft.Azure.Commands.ActiveDirectory.PSADApplication` ke `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphApplication`

### <a name="update-azadapplication"></a>Update-AzAdApplication

- Tipe input parameter `InputObject` telah diubah `Microsoft.Azure.Commands.ActiveDirectory.PSADApplication` ke `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphApplication`

- Tipe output telah diubah `Microsoft.Azure.Commands.ActiveDirectory.PSADApplication` dari ke `System.Boolean`

### <a name="changes-to-application-object"></a>Perubahan pada Objek Aplikasi

- `ObjectId` telah diganti dengan `Id`

- `HomePage` telah digantikan oleh `HomepageUrl` dalam `Web` elemen

- `ApplicationId` telah diganti dengan `AppId`

- `AvailableToOtherTenants` (boolean) telah diganti dengan (string dengan `SignInAudience` 4 nilai: 'AzureADMyOrg', 'AzureADMultipleOrgs', 'AzureADandPersonalMicrosoftAccount', 'PersonalMicrosoftAccount')

  - AzureADMultipleOrgs setara dengan AvailableToOtherTenants:$true

  - AzureAdMyOrg setara dengan AvailableToOtherTenants:$false atau $null

- `ApiPermissions` telah diganti dengan `RequiredResourceAccess`

- `ReplyUrls` telah digantikan oleh `RedirectUris ` dalam `Web` elemen

- `ObjectType` telah diganti dengan `OdataType`

## <a name="application-credential"></a>Kredensial Aplikasi

### <a name="get-azadappcredential"></a>Get-AzAdAppCredential

- Tipe input parameter `ApplicationObject` telah diubah `Microsoft.Azure.Commands.ActiveDirectory.PSADApplication` ke `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphApplication`

- Tipe output telah diubah `Microsoft.Azure.Commands.ActiveDirectory. PSADCredential` dari ke `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphKeyCredential`
  dan `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphPasswordCredential`

### <a name="new-azadappcredential"></a>New-AzAdAppCredential

- Tipe input parameter `ApplicationObject` telah diubah `Microsoft.Azure.Commands.ActiveDirectory.PSADApplication` ke `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphApplication`

- Tipe output telah diubah `Microsoft.Azure.Commands.ActiveDirectory. PSADCredential` dari ke `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphKeyCredential`
  dan `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphPasswordCredential`

- Parameter `Password` telah dihapus, kata sandi yang dikustomisasi tidak lagi didukung, server akan menetapkan teks rahasia saat pembuatan

### <a name="remove-azadappcredential"></a>Remove-AzAdAppCredential

- Tipe input parameter `ApplicationObject` telah diubah `Microsoft.Azure.Commands.ActiveDirectory.PSADApplication` ke `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphApplication`

### <a name="changes-to-app-credential-object"></a>Perubahan pada objek Kredensial Aplikasi

#### <a name="password-credential"></a>Kredensial Kata Sandi
- `Password` telah diganti dengan `SecretText`

#### <a name="key-credential"></a>Kredensial Kunci
- `CertValue` telah Dihapus

## <a name="serviceprincipal"></a>ServicePrincipal

### <a name="get-azadserviceprincipal"></a>Get-AzAdServicePrincipal

- Tipe output telah diubah `Microsoft.Azure.Commands.ActiveDirectory.PSADServicePrincipal` dari ke `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphServicePrincipal`

- Parameter `IncludeTotalCount` tidak didukung dan telah dihapus.

### <a name="new-azadserviceprincipal"></a>New-AzAdServicePrincipal

- Tipe output telah diubah `Microsoft.Azure.Commands.ActiveDirectory.PSADServicePrincipal` dari ke `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphServicePrincipal`

- Kumpulan parameter `ApplicationWithoutCredentialParameterSet` , , telah dihapus karena kumpulan parameter asli tersebut tidak `ApplicationWithPasswordPlainParameterSet` `DisplayNameWithoutCredentialParameterSet` `DisplayNameWithPasswordPlainParameterSet` berfungsi.

- Peran `contributor` tidak ditetapkan sebagai default ketika parameter tidak diberikan karena pertimbangan `-Role` keamanan.

- Parameter `SkipAssignment` telah dihapus.

### <a name="remove-azadserviceprincipal"></a>Remove-AzAdServicePrincipal

- Tipe input parameter `ApplicationObject` telah diubah `Microsoft.Azure.Commands.ActiveDirectory.PSADApplication` ke `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphApplication`

- Tipe input parameter `InputObject` telah diubah `Microsoft.Azure.Commands.ActiveDirectory.PSADServicePrincipal` ke `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphServicePrincipal`

### <a name="update-azadserviceprincipal"></a>Update-AzAdServicePrincipal

- Tipe input parameter `InputObject` telah diubah `Microsoft.Azure.Commands.ActiveDirectory.PSADServicePrincipal` ke `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphServicePrincipal`

- Tipe output telah diubah `Microsoft.Azure.Commands.ActiveDirectory.PSADServicePrincipal` dari ke `System.Boolean`

### <a name="changes-to-service-principal-object"></a>Perubahan pada Objek Prinsipal Layanan

- `ApplicationId` telah diganti dengan `AppId`

- `ObjectType` telah diganti dengan `OdataType`

## <a name="serviceprincipal-credential"></a>Kredensial ServicePrincipal

### <a name="get-azadspcredential"></a>Get-AzAdSpCredential

- Tipe input parameter `ServicePrincipalObject` telah diubah `Microsoft.Azure.Commands.ActiveDirectory.PSADServicePrincipal` ke `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphServicePrincipal`

- Tipe output telah diubah `Microsoft.Azure.Commands.ActiveDirectory. PSADCredential` dari ke `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphKeyCredential`
  dan `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphPasswordCredential`

### <a name="new-azadspcredential"></a>New-AzAdSpCredential

- Tipe input parameter `ServicePrincipalObject` telah diubah `Microsoft.Azure.Commands.ActiveDirectory.PSADServicePrincipal` ke `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphServicePrincipal`

- Tipe output telah diubah `Microsoft.Azure.Commands.ActiveDirectory. PSADCredential` dari ke `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphKeyCredential`
  dan `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphPasswordCredential`

### <a name="remove-azadspcredential"></a>Remove-AzAdSpCredential

- Tipe input parameter `ServicePrincipalObject` telah diubah `Microsoft.Azure.Commands.ActiveDirectory.PSADServicePrincipal` ke `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphServicePrincipal`

### <a name="changes-to-serviceprincipal-credential-object"></a>Perubahan pada objek ServicePrincipal Credential

#### <a name="password-credential"></a>Kredensial Kata Sandi
- `Password` telah diganti dengan `SecretText`

#### <a name="key-credential"></a>Kredensial Kunci
- `CertValue` telah Dihapus

## <a name="user"></a>Pengguna

### <a name="get-azaduser"></a>Get-AzAdUser

- Tipe output telah diubah `Microsoft.Azure.Commands.ActiveDirectory.PSADUser` dari ke `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphUser`

- Parameter `IncludeTotalCount` tidak didukung dan telah dihapus

### <a name="new-azaduser"></a>New-AzAdUser

- Tipe output telah diubah `Microsoft.Azure.Commands.ActiveDirectory.PSADUser` dari ke `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphUser`

### <a name="remove-azaduser"></a>Remove-AzAdUser

- Tipe input parameter `InputObject` telah diubah `Microsoft.Azure.Commands.ActiveDirectory.PSADUser` ke `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphUser`

### <a name="update-azaduser"></a>Update-AzAdUser

- Tipe input parameter `InputObject` telah diubah `Microsoft.Azure.Commands.ActiveDirectory.PSADUser` ke `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphUser`

- Tipe output telah diubah `Microsoft.Azure.Commands.ActiveDirectory.PSADUser` dari ke `System.Boolean`

### <a name="changes-to-user-object"></a>Perubahan pada Objek Pengguna

- `ObjectType` telah diganti dengan `OdataType`

- `ImmutableId` telah diganti dengan `OnpremisesImmutableId`

## <a name="group"></a>Grup

### <a name="get-azadgroup"></a>Get-AzAdGroup

- Tipe output telah diubah `Microsoft.Azure.Commands.ActiveDirectory.PSADGroup` dari ke `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphGroup`

- Parameter `IncludeTotalCount` tidak didukung dan telah dihapus

### <a name="new-azadgroup"></a>New-AzAdGroup

- Tipe output telah diubah `Microsoft.Azure.Commands.ActiveDirectory.PSADGroup` dari ke `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphGroup`

### <a name="remove-azadgroup"></a>Remove-AzAdGroup

- Tipe input parameter `InputObject` telah diubah `Microsoft.Azure.Commands.ActiveDirectory.PSADGroup` ke `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphGroup`

### <a name="changes-of-group-object"></a>Perubahan Objek Grup

- `ObjectType` telah diganti dengan `OdataType`

## <a name="group-member"></a>Anggota grup

### <a name="get-azadgroupmember"></a>Get-AzAdGroupMember

- Tipe output telah diubah `Microsoft.Azure.Commands.ActiveDirectory.PSADObject` dari ke `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphDirectoryObject`

- Parameter `IncludeTotalCount` telah dihapus

- Tipe input parameter `GroupObject` telah diubah `Microsoft.Azure.Commands.ActiveDirectory.PSADGroup` ke `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphGroup`

### <a name="add-azadgroupmember"></a>Add-AzAdGroupMember

- Tipe input parameter `GroupObject` telah diubah `Microsoft.Azure.Commands.ActiveDirectory.PSADGroup` ke `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphGroup`

### <a name="remove-azadgroupmember"></a>Remove-AzAdGroupMember

- Tipe input parameter `GroupObject` telah diubah `Microsoft.Azure.Commands.ActiveDirectory.PSADGroup` ke `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphGroup`
