---
external help file: ''
Module Name: Az.ManagedServices
online version: https://docs.microsoft.com/powershell/module/az.managedservices/get-azmanagedservicesdefinition
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ManagedServices/help/Get-AzManagedServicesDefinition.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ManagedServices/help/Get-AzManagedServicesDefinition.md
ms.openlocfilehash: b489d6f8d3e45078dee7d09a528f7942f19d80c9
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138276124"
---
# Get-AzManagedServicesDefinition

## SYNOPSIS
Mendapatkan detail definisi registrasi.

## SYNTAX

### Daftar (Default)
```
Get-AzManagedServicesDefinition [-Scope <String>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Dapatkan
```
Get-AzManagedServicesDefinition -Name <String> [-Scope <String>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzManagedServicesDefinition -InputObject <IManagedServicesIdentity> [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan detail definisi registrasi.

## EXAMPLES

### Contoh 1: Mencantumkan semua definisi pendaftaran Mercusuar Azure dalam langganan
```powershell
PS C:\> Get-AzManagedServicesDefinition

Name                                 Type
----                                 ----
xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx Microsoft.ManagedServices/registrationDefinitions
xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx Microsoft.ManagedServices/registrationDefinitions
```

Mencantumkan semua definisi pendaftaran Azure Lighthouse dalam langganan tertentu dalam konteks.

### Contoh 2: Dapatkan definisi pendaftaran Azure Lighthouse menurut nama dengan properti yang dipilih
```powershell
PS C:\>  Get-AzManagedServicesDefinition -Name xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx |Format-List -Property Id, Name, Type, ManagedByTenantId, Authorization, EligibleAuthorization

Id                    : /subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/providers/Microsoft.ManagedServices/registrationDefinitions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
Name                  : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
Type                  : Microsoft.ManagedServices/registrationDefinitions
ManagedByTenantId     : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
Authorization         : {Test user}
EligibleAuthorization : {Test user}
```

Dapatkan definisi pendaftaran Azure Lighthouse berdasarkan nama dengan properti yang dipilih.

### Contoh 3: Mencantumkan semua definisi pendaftaran Mercusuar Azure menurut lingkup
```powershell
PS C:\> Get-AzManagedServicesDefinition -Scope /subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx | Format-List -Property Id, Name, Type, ManagedByTenantId, Authorization, EligibleAuthorization

Id                    : /subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/providers/Microsoft.ManagedServices/registrationDefinitions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
Name                  : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
Type                  : Microsoft.ManagedServices/registrationDefinitions
ManagedByTenantId     : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
Authorization         : {Test user}
EligibleAuthorization : {Test user}

Id                    : /subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/providers/Microsoft.ManagedServices/registrationDefinitions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
Name                  : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
Type                  : Microsoft.ManagedServices/registrationDefinitions
ManagedByTenantId     : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
Authorization         : {}
EligibleAuthorization :
```

Mencantumkan semua definisi pendaftaran Azure Lighthouse dengan lingkup langganan tertentu.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases: AzureRMContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Parameter Identitas Untuk membuat, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ManagedServices.Models.IManagedServicesIdentity
Parameter Sets: GetViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nama
GUID definisi registrasi.

```yaml
Type: System.String
Parameter Sets: Get
Aliases: RegistrationDefinitionId

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lingkup
Lingkup sumber daya.

```yaml
Type: System.String
Parameter Sets: Get, List
Aliases:

Required: False
Position: Named
Default value: "subscriptions/" + (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ManagedServices.Models.IManagedServicesIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ManagedServices.Models.Api20200201Preview.IRegistrationDefinition

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IManagedServicesIdentity>: Parameter Identitas
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[MarketplaceIdentifier <String>]`: Pengidentifikasi Azure Marketplace. Format yang diharapkan: {publisher}. {product[-preview]}. {planName}. {version} atau {publisher}. {product[-preview]}. {planName} atau {publisher}. {product[-preview]} atau {publisher}).
  - `[RegistrationAssignmentId <String>]`: GUID penetapan pendaftaran.
  - `[RegistrationDefinitionId <String>]`: GUID definisi registrasi.
  - `[Scope <String>]`: Lingkup sumber daya.

## RELATED LINKS

