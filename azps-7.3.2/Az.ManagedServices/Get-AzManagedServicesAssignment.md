---
external help file: ''
Module Name: Az.ManagedServices
online version: https://docs.microsoft.com/powershell/module/az.managedservices/get-azmanagedservicesassignment
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ManagedServices/help/Get-AzManagedServicesAssignment.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ManagedServices/help/Get-AzManagedServicesAssignment.md
ms.openlocfilehash: 071221525234b4ee3c2fd52a9e9d69a544f47596
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140000366"
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

### Contoh 1: Mencantumkan semua tugas pendaftaran Mercusuar Azure dalam langganan
```powershell
PS C:\> Get-AzManagedServicesAssignment

Name                                 Type
----                                 ----
xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx Microsoft.ManagedServices/registrationAssignments
xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx Microsoft.ManagedServices/registrationAssignments
xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx Microsoft.ManagedServices/registrationAssignments
```

Mencantumkan semua tugas pendaftaran Mercusuar Azure dalam langganan tertentu dalam konteks.

### Contoh 2: Dapatkan pendaftaran pendaftaran Azure Lighthouse berdasarkan nama dengan properti yang dipilih
```powershell
PS C:\> Get-AzManagedServicesAssignment -Name xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx | Format-List -Property Id, Name, Type, RegistrationDefinitionId, ProvisioningState

Id                       : /subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/providers/Microsoft.ManagedServices/registrationAssignments/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
Name                     : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
Type                     : Microsoft.ManagedServices/registrationAssignments
RegistrationDefinitionId : /subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/providers/Microsoft.ManagedServices/registrationDefinitions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
ProvisioningState        : Succeeded
```

Mendapatkan pendaftaran Azure Lighthouse berdasarkan nama dengan properti yang dipilih.

### Contoh 3: Mencantumkan semua tugas pendaftaran Mercusuar Azure menurut lingkup
```powershell
PS C:\>  Get-AzManagedServicesAssignment -Scope /subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx | Format-List -Property Id, Name, Type, RegistrationDefinitionId, ProvisioningState

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

Mencantumkan semua tugas pendaftaran Mercusuar Azure dalam lingkup grup langganan atau sumber daya tertentu.

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
Bendera menunjukkan apakah akan mengembalikan detail definisi pendaftaran bersama dengan detail penetapan pendaftaran.

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

### Microsoft.Azure.PowerShell.Cmdlets.ManagedServices.Models.Api20200201Preview.IRegistrationAssignment

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

