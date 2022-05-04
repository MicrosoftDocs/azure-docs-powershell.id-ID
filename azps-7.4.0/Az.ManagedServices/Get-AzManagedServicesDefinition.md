---
external help file: ''
Module Name: Az.ManagedServices
online version: https://docs.microsoft.com/powershell/module/az.managedservices/get-azmanagedservicesdefinition
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ManagedServices/help/Get-AzManagedServicesDefinition.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ManagedServices/help/Get-AzManagedServicesDefinition.md
ms.openlocfilehash: 3a6ef892fbc57672e39d9431d2113d143d49bb5a
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144583552"
---
# Get-AzManagedServicesDefinition

## SYNOPSIS
Mendapatkan detail definisi pendaftaran.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.managedservices/get-azmanagedservicesdefinition) untuk informasi terbaru.

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
Mendapatkan detail definisi pendaftaran.

## EXAMPLES

### Contoh 1: Mencantumkan semua definisi pendaftaran Azure Lighthouse dalam langganan
```powershell
Get-AzManagedServicesDefinition
```

```output
Name                                 Type
----                                 ----
xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx Microsoft.ManagedServices/registrationDefinitions
xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx Microsoft.ManagedServices/registrationDefinitions
```

Mencantumkan semua definisi pendaftaran Azure Lighthouse dalam langganan tertentu dalam konteks.

### Contoh 2: Mendapatkan definisi pendaftaran Azure Lighthouse berdasarkan nama dengan properti yang dipilih
```powershell
Get-AzManagedServicesDefinition -Name xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx |Format-List -Property Id, Name, Type, ManagedByTenantId, Authorization, EligibleAuthorization
```

```output
Id                    : /subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/providers/Microsoft.ManagedServices/registrationDefinitions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
Name                  : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
Type                  : Microsoft.ManagedServices/registrationDefinitions
ManagedByTenantId     : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
Authorization         : {Test user}
EligibleAuthorization : {Test user}
```

Mendapatkan definisi pendaftaran Azure Lighthouse berdasarkan nama dengan properti yang dipilih.

### Contoh 3: Mencantumkan semua definisi pendaftaran Azure Lighthouse berdasarkan cakupan
```powershell
Get-AzManagedServicesDefinition -Scope /subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx | Format-List -Property Id, Name, Type, ManagedByTenantId, Authorization, EligibleAuthorization
```

```output
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

Mencantumkan semua definisi pendaftaran Azure Lighthouse berdasarkan cakupan langganan tertentu.

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
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan buat tabel hash.

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

### -Name
GUID definisi pendaftaran.

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

### -Cakupan
Cakupan sumber daya.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ManagedServices.Models.IManagedServicesIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ManagedServices.Models.Api20200201Preview.IRegistrationDefinition

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IManagedServicesIdentity>: Parameter Identitas
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[MarketplaceIdentifier <String>]`: Pengidentifikasi Marketplace Azure. Format yang diharapkan: {publisher}. {product[-preview]}. {planName}. {version} atau {publisher}. {product[-preview]}. {planName} atau {publisher}. {product[-preview]} atau {publisher}).
  - `[RegistrationAssignmentId <String>]`: GUID penugasan pendaftaran.
  - `[RegistrationDefinitionId <String>]`: GUID definisi pendaftaran.
  - `[Scope <String>]`: Cakupan sumber daya.

## RELATED LINKS

