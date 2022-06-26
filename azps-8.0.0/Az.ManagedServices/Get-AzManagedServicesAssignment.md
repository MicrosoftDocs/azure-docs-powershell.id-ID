---
external help file: ''
Module Name: Az.ManagedServices
online version: https://docs.microsoft.com/powershell/module/az.managedservices/get-azmanagedservicesassignment
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ManagedServices/help/Get-AzManagedServicesAssignment.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ManagedServices/help/Get-AzManagedServicesAssignment.md
ms.openlocfilehash: 63cb22efef55e2163c90bbd7c2e1e6ff9cc315ab
ms.sourcegitcommit: 5df8b100721844736630242c724da453a2168434
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/26/2022
ms.locfileid: "146634916"
---
# Get-AzManagedServicesAssignment

## SYNOPSIS
Mendapatkan detail penetapan pendaftaran yang ditentukan.

## SYNTAX

### Daftar (Default)
```
Get-AzManagedServicesAssignment [-Scope <String>] [-ExpandRegistrationDefinition] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### Dapatkan
```
Get-AzManagedServicesAssignment -Name <String> [-Scope <String>] [-ExpandRegistrationDefinition]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzManagedServicesAssignment -InputObject <IManagedServicesIdentity> [-ExpandRegistrationDefinition]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan detail penetapan pendaftaran yang ditentukan.

## EXAMPLES

### Contoh 1: Mencantumkan semua penetapan pendaftaran Azure Lighthouse dalam langganan
```powershell
Get-AzManagedServicesAssignment
```

```output
Name                                 Type
----                                 ----
xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx Microsoft.ManagedServices/registrationAssignments
xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx Microsoft.ManagedServices/registrationAssignments
xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx Microsoft.ManagedServices/registrationAssignments
```

Mencantumkan semua penetapan pendaftaran Azure Lighthouse dalam langganan tertentu dalam konteks.

### Contoh 2: Mendapatkan penetapan pendaftaran Azure Lighthouse berdasarkan nama dengan properti yang dipilih
```powershell
Get-AzManagedServicesAssignment -Name xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx | Format-List -Property Id, Name, Type, RegistrationDefinitionId, ProvisioningState
```

```output
Id                       : /subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/providers/Microsoft.ManagedServices/registrationAssignments/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
Name                     : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
Type                     : Microsoft.ManagedServices/registrationAssignments
RegistrationDefinitionId : /subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/providers/Microsoft.ManagedServices/registrationDefinitions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
ProvisioningState        : Succeeded
```

Mendapatkan penetapan pendaftaran Azure Lighthouse berdasarkan nama dengan properti yang dipilih.

### Contoh 3: Mencantumkan semua penetapan pendaftaran Azure Lighthouse berdasarkan cakupan
```powershell
Get-AzManagedServicesAssignment -Scope /subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx | Format-List -Property Id, Name, Type, RegistrationDefinitionId, ProvisioningState
```

```output
Id                       : /subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/providers/Microsoft.ManagedServices/registrationAssignments/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
Name                     : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
Type                     : Microsoft.ManagedServices/registrationAssignments
RegistrationDefinitionId : /subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/providers/Microsoft.ManagedServices/registrationDefinitions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
ProvisioningState        : Succeeded

Id                       : /subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/providers/Microsoft.ManagedServices/registrationAssignments/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
Name                     : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
Type                     : Microsoft.ManagedServices/registrationAssignments
RegistrationDefinitionId : /subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/providers/Microsoft.ManagedServices/registrationDefinitions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
ProvisioningState        : Succeeded

Id                       : /subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/providers/Microsoft.ManagedServices/registrationAssignments/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
Name                     : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
Type                     : Microsoft.ManagedServices/registrationAssignments
RegistrationDefinitionId : /subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/providers/Microsoft.ManagedServices/registrationDefinitions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
ProvisioningState        : Succeeded
```

Mencantumkan semua penetapan pendaftaran Azure Lighthouse dalam cakupan langganan atau grup sumber daya tertentu.

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

### -ExpandRegistrationDefinition
Bendera yang menunjukkan apakah akan mengembalikan detail definisi pendaftaran bersama dengan detail penetapan pendaftaran.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

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
GUID penetapan pendaftaran.

```yaml
Type: System.String
Parameter Sets: Get
Aliases: RegistrationAssignmentId

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

### Microsoft.Azure.PowerShell.Cmdlets.ManagedServices.Models.Api20200201Preview.IRegistrationAssignment

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT `<IManagedServicesIdentity>`: Parameter Identitas
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[MarketplaceIdentifier <String>]`: Pengidentifikasi Marketplace Azure. Format yang diharapkan: {publisher}. {product[-preview]}. {planName}. {version} atau {publisher}. {product[-preview]}. {planName} atau {publisher}. {product[-preview]} atau {publisher}).
  - `[RegistrationAssignmentId <String>]`: GUID penetapan pendaftaran.
  - `[RegistrationDefinitionId <String>]`: GUID definisi pendaftaran.
  - `[Scope <String>]`: Cakupan sumber daya.

## RELATED LINKS

