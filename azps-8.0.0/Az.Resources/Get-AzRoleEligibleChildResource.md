---
external help file: Az.Resources-help.xml
Module Name: Az.Resources
online version: https://docs.microsoft.com/powershell/module/az.resources/get-azroleeligiblechildresource
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzRoleEligibleChildResource.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzRoleEligibleChildResource.md
ms.openlocfilehash: 814129326ef2a3119378d0fab833ef05fc872974
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145555571"
---
# Get-AzRoleEligibleChildResource

## SYNOPSIS
Mendapatkan sumber daya anak dari sumber daya tempat pengguna memiliki akses yang memenuhi syarat

## SYNTAX

### Dapatkan (Default)
```
Get-AzRoleEligibleChildResource -Scope <String> [-Filter <String>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzRoleEligibleChildResource -InputObject <IAuthorizationIdentity> [-Filter <String>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan sumber daya anak dari sumber daya tempat pengguna memiliki akses yang memenuhi syarat

## EXAMPLES

### Contoh 1: Mencantumkan semua sumber daya anak
```powershell
PS C:\> $scope = "/subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d/"
PS C:\> Get-AzRoleEligibleChildResource -Scope $scope                              

Name                                               Type
----                                               ----
AnujRG                                             resourcegroup
ARPJ-TESTRG-01                                     resourcegroup
AnujRG2                                            resourcegroup
asghodke-rg                                        resourcegroup
```

Dapatkan semua sumber daya anak dari sumber daya `scope` tempat pengguna panggilan memiliki penetapan yang memenuhi syarat.

### Contoh 2: Mencantumkan semua sumber daya anak yang difilter menurut jenis sumber daya
```powershell
PS C:\> $scope = "/subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d/"
PS C:\> $filter = "resoureType eq 'resourcegroup'"
PS C:\> Get-AzRoleEligibleChildResource -Scope $scope -Filter $filter

Name                                               Type
----                                               ----
AnujRG                                             resourcegroup
ARPJ-TESTRG-01                                     resourcegroup
AnujRG2                                            resourcegroup
asghodke-rg                                        resourcegroup
```

Anda dapat memfilter berdasarkan langganan, resourceGroups, atau jenis sumber daya apa pun.

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

### -Filter
Filter yang akan diterapkan pada operasi.
Gunakan $filter=resourceType+eq+'Subscription' untuk memfilter hanya pada sumber daya jenis = 'Langganan'.
Gunakan $filter=resourceType+eq+'subscription'+or+resourceType+eq+'resourcegroup' untuk memfilter sumber daya jenis = 'Langganan' atau 'ResourceGroup'

```yaml
Type: System.String
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
Type: Microsoft.Azure.PowerShell.Cmdlets.Resources.Authorization.Models.IAuthorizationIdentity
Parameter Sets: GetViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Cakupan
Cakupan kebijakan manajemen peran.

```yaml
Type: System.String
Parameter Sets: Get
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Resources.Authorization.Models.IAuthorizationIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Resources.Authorization.Models.Api20201001Preview.IEligibleChildResource

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IAuthorizationIdentity>: Parameter Identitas
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[RoleAssignmentScheduleInstanceName <String>]`: Nama (hash nama jadwal + waktu) dari jadwal penetapan peran yang akan didapatkan.
  - `[RoleAssignmentScheduleName <String>]`: Nama (guid) dari jadwal penetapan peran yang akan didapatkan.
  - `[RoleAssignmentScheduleRequestName <String>]`: Nama penetapan peran yang akan dibuat. Ini bisa menjadi GUID yang valid.
  - `[RoleEligibilityScheduleInstanceName <String>]`: Nama (hash nama jadwal + waktu) dari jadwal kelayakan peran untuk mendapatkan.
  - `[RoleEligibilityScheduleName <String>]`: Nama (guid) dari jadwal kelayakan peran yang akan didapatkan.
  - `[RoleEligibilityScheduleRequestName <String>]`: Nama kelayakan peran untuk dibuat. Ini bisa menjadi GUID yang valid.
  - `[RoleManagementPolicyAssignmentName <String>]`: Nama format {guid_guid} penetapan kebijakan manajemen peran yang akan didapatkan.
  - `[RoleManagementPolicyName <String>]`: Nama (guid) dari kebijakan manajemen peran yang akan didapatkan.
  - `[Scope <String>]`: Cakupan kebijakan manajemen peran.

## RELATED LINKS
