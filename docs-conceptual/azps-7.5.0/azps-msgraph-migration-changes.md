---
description: Panduan migrasi berisi daftar perubahan Azure PowerShell untuk migrasi Azure AD ke Microsoft Graph di Az.Resources 5.1.0.
ms.custom: devx-track-azurepowershell
ms.date: 05/09/2022
ms.devlang: powershell
ms.service: azure-powershell
ms.topic: conceptual
title: Migrasi Azure AD ke Microsoft Graph di Azure PowerShell
ms.openlocfilehash: 7aa13cd579a0f8286be5c994ec8c2aef0b4947dc
ms.sourcegitcommit: 97a10cac523612de4dbece96f25bd7e3f2431276
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/12/2022
ms.locfileid: "144957337"
---
# <a name="azure-ad-to-microsoft-graph-migration-changes-in-azure-powershell"></a>Migrasi Azure AD ke Microsoft Graph di Azure PowerShell

Modul `Az.Resources` PowerShell versi 5.1.0 dari Azure PowerShel memperkenalkan perubahan pada cmdlet terkait identitas. Cmdlet yang mengandalkan Azure AD Graph beralih ke Microsoft Graph. Perubahan ini terjadi untuk memastikan transisi yang mulus dalam hal [pengumuman penghentian Azure AD Graph](https://azure.microsoft.com/updates/update-your-apps-to-use-microsoft-graph-before-30-june-2022/).
Untuk informasi selengkapnya, lihat [migrasi Azure AD ke Microsoft Graph untuk alat baris perintah Azure](https://techcommunity.microsoft.com/t5/azure-tools/azure-ad-to-microsoft-graph-migration-for-azure-command-line/ba-p/2836666).

Contoh berikut menginstal versi terbaru modul `Az.Resources` Azure PowerShell.

```powershell
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

- Jenis input parameter `InputObject` telah berubah dari `Microsoft.Azure.Commands.ActiveDirectory.PSADApplication` menjadi `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphApplication`

### <a name="update-azadapplication"></a>Update-AzADApplication

- Jenis input parameter `InputObject` telah berubah dari `Microsoft.Azure.Commands.ActiveDirectory.PSADApplication` menjadi `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphApplication`

- Jenis output telah diubah dari `Microsoft.Azure.Commands.ActiveDirectory.PSADApplication` menjadi `System.Boolean`

### <a name="changes-to-application-object"></a>Perubahan pada Objek Aplikasi

- `ObjectId` telah digantikan oleh `Id`

- `HomePage` telah diganti dengan `HomepageUrl` di elemen `Web`

- `ApplicationId` telah digantikan oleh `AppId`

- `AvailableToOtherTenants` (boolean) telah diganti dengan `SignInAudience` (string dengan 4 nilai: 'AzureADMyOrg', 'AzureADMultipleOrgs', 'AzureADandPersonalMicrosoftAccount', 'PersonalMicrosoftAccount')

  - AzureADMultipleOrgs setara dengan AvailableToOtherTenants:$true

  - AzureAdMyOrg setara dengan AvailableToOtherTenants:$false atau $null

- `ApiPermissions` telah digantikan oleh `RequiredResourceAccess`

- `ReplyUrls` telah diganti dengan `RedirectUris ` di elemen `Web`

- `ObjectType` telah digantikan oleh `OdataType`

## <a name="application-credential"></a>Informasi Masuk Aplikasi

### <a name="get-azadappcredential"></a>Get-AzAdAppCredential

- Jenis input parameter `ApplicationObject` telah berubah dari `Microsoft.Azure.Commands.ActiveDirectory.PSADApplication` menjadi `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphApplication`

- Jenis output telah diubah dari `Microsoft.Azure.Commands.ActiveDirectory. PSADCredential` menjadi `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphKeyCredential`
   dan `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphPasswordCredential`

### <a name="new-azadappcredential"></a>New-AzAdAppCredential

- Jenis input parameter `ApplicationObject` telah berubah dari `Microsoft.Azure.Commands.ActiveDirectory.PSADApplication` menjadi `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphApplication`

- Jenis output telah diubah dari `Microsoft.Azure.Commands.ActiveDirectory. PSADCredential` menjadi `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphKeyCredential`
   dan `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphPasswordCredential`

- Parameter `Password` telah dihapus, kata sandi yang disesuaikan tidak didukung lagi, server akan menetapkan teks rahasia saat pembuatan

### <a name="remove-azadappcredential"></a>Remove-AzAdAppCredential

- Jenis input parameter `ApplicationObject` telah berubah dari `Microsoft.Azure.Commands.ActiveDirectory.PSADApplication` menjadi `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphApplication`

### <a name="changes-to-app-credential-object"></a>Perubahan pada Objek Informasi Masuk Aplikasi

#### <a name="password-credential"></a>Informasi Masuk Kata Sandi
- `Password` telah digantikan oleh `SecretText`

#### <a name="key-credential"></a>Informasi Masuk Kunci
- `CertValue` telah Dihapus

## <a name="serviceprincipal"></a>ServicePrincipal

### <a name="get-azadserviceprincipal"></a>Get-AzAdServicePrincipal

- Jenis output telah diubah dari `Microsoft.Azure.Commands.ActiveDirectory.PSADServicePrincipal` menjadi `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphServicePrincipal`

- Parameter `IncludeTotalCount` tidak didukung dan telah dihapus.

### <a name="new-azadserviceprincipal"></a>New-AzAdServicePrincipal

- Jenis output telah diubah dari `Microsoft.Azure.Commands.ActiveDirectory.PSADServicePrincipal` menjadi `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphServicePrincipal`

- Set parameter `ApplicationWithoutCredentialParameterSet`, `ApplicationWithPasswordPlainParameterSet`, `DisplayNameWithoutCredentialParameterSet`, `DisplayNameWithPasswordPlainParameterSet` telah dihapus karena set parameter asli tidak berfungsi.

- Peran `contributor` tidak ditetapkan sebagai default saat parameter `-Role` tidak disediakan karena pertimbangan keamanan.

- Parameter `SkipAssignment` telah dihapus.

### <a name="remove-azadserviceprincipal"></a>Remove-AzAdServicePrincipal

- Jenis input parameter `ApplicationObject` telah berubah dari `Microsoft.Azure.Commands.ActiveDirectory.PSADApplication` menjadi `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphApplication`

- Jenis input parameter `InputObject` telah berubah dari `Microsoft.Azure.Commands.ActiveDirectory.PSADServicePrincipal` menjadi `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphServicePrincipal`

### <a name="update-azadserviceprincipal"></a>Update-AzAdServicePrincipal

- Jenis input parameter `InputObject` telah berubah dari `Microsoft.Azure.Commands.ActiveDirectory.PSADServicePrincipal` menjadi `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphServicePrincipal`

- Jenis output telah diubah dari `Microsoft.Azure.Commands.ActiveDirectory.PSADServicePrincipal` menjadi `System.Boolean`

### <a name="changes-to-service-principal-object"></a>Perubahan pada Objek Perwakilan Layanan

- `ApplicationId` telah digantikan oleh `AppId`

- `ObjectType` telah digantikan oleh `OdataType`

## <a name="serviceprincipal-credential"></a>Informasi Masuk ServicePrincipal

### <a name="get-azadspcredential"></a>Get-AzAdSpCredential

- Jenis input parameter `ServicePrincipalObject` telah berubah dari `Microsoft.Azure.Commands.ActiveDirectory.PSADServicePrincipal` menjadi `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphServicePrincipal`

- Jenis output telah diubah dari `Microsoft.Azure.Commands.ActiveDirectory. PSADCredential` menjadi `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphKeyCredential`
   dan `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphPasswordCredential`

### <a name="new-azadspcredential"></a>New-AzAdSpCredential

- Jenis input parameter `ServicePrincipalObject` telah berubah dari `Microsoft.Azure.Commands.ActiveDirectory.PSADServicePrincipal` menjadi `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphServicePrincipal`

- Jenis output telah diubah dari `Microsoft.Azure.Commands.ActiveDirectory. PSADCredential` menjadi `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphKeyCredential`
   dan `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphPasswordCredential`

### <a name="remove-azadspcredential"></a>Remove-AzAdSpCredential

- Jenis input parameter `ServicePrincipalObject` telah berubah dari `Microsoft.Azure.Commands.ActiveDirectory.PSADServicePrincipal` menjadi `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphServicePrincipal`

### <a name="changes-to-serviceprincipal-credential-object"></a>Perubahan pada Objek Informasi Masuk ServicePrincipal

#### <a name="password-credential"></a>Informasi Masuk Kata Sandi
- `Password` telah digantikan oleh `SecretText`

#### <a name="key-credential"></a>Informasi Masuk Kunci
- `CertValue` telah Dihapus

## <a name="user"></a>Pengguna

### <a name="get-azaduser"></a>Get-AzAdUser

- Jenis output telah diubah dari `Microsoft.Azure.Commands.ActiveDirectory.PSADUser` menjadi `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphUser`

- Parameter `IncludeTotalCount` tidak didukung dan telah dihapus

### <a name="new-azaduser"></a>New-AzAdUser

- Jenis output telah diubah dari `Microsoft.Azure.Commands.ActiveDirectory.PSADUser` menjadi `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphUser`

### <a name="remove-azaduser"></a>Remove-AzAdUser

- Jenis input parameter `InputObject` telah berubah dari `Microsoft.Azure.Commands.ActiveDirectory.PSADUser` menjadi `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphUser`

### <a name="update-azaduser"></a>Update-AzAdUser

- Jenis input parameter `InputObject` telah berubah dari `Microsoft.Azure.Commands.ActiveDirectory.PSADUser` menjadi `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphUser`

- Jenis output telah diubah dari `Microsoft.Azure.Commands.ActiveDirectory.PSADUser` menjadi `System.Boolean`

### <a name="changes-to-user-object"></a>Perubahan pada Objek Pengguna

- `ObjectType` telah digantikan oleh `OdataType`

- `ImmutableId` telah digantikan oleh `OnpremisesImmutableId`

## <a name="group"></a>Grup

### <a name="get-azadgroup"></a>Get-AzAdGroup

- Jenis output telah diubah dari `Microsoft.Azure.Commands.ActiveDirectory.PSADGroup` menjadi `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphGroup`

- Parameter `IncludeTotalCount` tidak didukung dan telah dihapus

### <a name="new-azadgroup"></a>New-AzAdGroup

- Jenis output telah diubah dari `Microsoft.Azure.Commands.ActiveDirectory.PSADGroup` menjadi `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphGroup`

### <a name="remove-azadgroup"></a>Remove-AzAdGroup

- Jenis input parameter `InputObject` telah berubah dari `Microsoft.Azure.Commands.ActiveDirectory.PSADGroup` menjadi `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphGroup`

### <a name="changes-of-group-object"></a>Perubahan Objek Grup

- `ObjectType` telah digantikan oleh `OdataType`

## <a name="group-member"></a>Anggota grup

### <a name="get-azadgroupmember"></a>Get-AzAdGroupMember

- Jenis output telah diubah dari `Microsoft.Azure.Commands.ActiveDirectory.PSADObject` menjadi `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphDirectoryObject`

- Parameter `IncludeTotalCount` telah dihapus

- Jenis input parameter `GroupObject` telah berubah dari `Microsoft.Azure.Commands.ActiveDirectory.PSADGroup` menjadi `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphGroup`

[!INCLUDE [get-azadgroupmember-no-serviceprincipal-banner](../../includes/get-azadgroupmember-no-serviceprincipal-banner.md)]

### <a name="add-azadgroupmember"></a>Add-AzAdGroupMember

- Jenis input parameter `GroupObject` telah berubah dari `Microsoft.Azure.Commands.ActiveDirectory.PSADGroup` menjadi `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphGroup`

### <a name="remove-azadgroupmember"></a>Remove-AzAdGroupMember

- Jenis input parameter `GroupObject` telah berubah dari `Microsoft.Azure.Commands.ActiveDirectory.PSADGroup` menjadi `Microsoft.Azure.PowerShell.Cmdlets.Resources.MSGraph.Models.ApiV10.IMicrosoftGraphGroup`
