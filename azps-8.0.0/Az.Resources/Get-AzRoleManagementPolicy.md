---
external help file: Az.Resources-help.xml
Module Name: Az.Resources
online version: https://docs.microsoft.com/powershell/module/az.resources/get-azrolemanagementpolicy
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzRoleManagementPolicy.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzRoleManagementPolicy.md
ms.openlocfilehash: 3f1205bc4f4748414ff086440e729d4138857ed4
ms.sourcegitcommit: 5df8b100721844736630242c724da453a2168434
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/26/2022
ms.locfileid: "146621200"
---
# Get-AzRoleManagementPolicy

## SYNOPSIS
Mendapatkan kebijakan manajemen peran yang ditentukan untuk cakupan sumber daya

## SYNTAX

### Daftar (Default)
```
Get-AzRoleManagementPolicy -Scope <String> [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Dapatkan
```
Get-AzRoleManagementPolicy -Name <String> -Scope <String> [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzRoleManagementPolicy -InputObject <IAuthorizationIdentity> [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan kebijakan manajemen peran yang ditentukan untuk cakupan sumber daya

## EXAMPLES

### Contoh 1: Mencantumkan semua kebijakan manajemen peran di bawah cakupan sumber daya
```powershell
PS C:\> $scope = "/subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d/"
PS C:\> Get-AzRoleManagementPolicy -Scope $scope

Name                                 Type                                           Scope
----                                 ----                                           -----
588b80cc-f50c-4616-acc9-0003872624db Microsoft.Authorization/roleManagementPolicies /subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d
8dbbf139-4d46-4ad4-a56b-004156c117d2 Microsoft.Authorization/roleManagementPolicies /subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d
1c8bc687-402c-4e62-b38b-009d6fc244d3 Microsoft.Authorization/roleManagementPolicies /subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d
```

Mengembalikan semua `roleManagementPolicies` untuk `scope`

### Contoh 2: Mendapatkan kebijakan manajemen peran berdasarkan Cakupan dan Nama
```powershell
PS C:\> $scope = "/subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d/"
PS C:\> $name = "33b520ea-3544-4abc-8565-3588deb8e68e"
PS C:\> Get-AzRoleManagementPolicy -Scope $scope -Name $name

Name                                 Type                                           Scope
----                                 ----                                           -----
33b520ea-3544-4abc-8565-3588deb8e68e Microsoft.Authorization/roleManagementPolicies /subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d
```

`Id` Gunakan properti untuk mendapatkan `scope` dan`name`

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

### -Name
Nama (guid) dari kebijakan manajemen peran yang akan didapatkan.

```yaml
Type: System.String
Parameter Sets: Get
Aliases: RoleManagementPolicyName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Cakupan
Cakupan kebijakan manajemen peran.

```yaml
Type: System.String
Parameter Sets: List, Get
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

### Microsoft.Azure.PowerShell.Cmdlets.Resources.Authorization.Models.Api20201001Preview.IRoleManagementPolicy

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT `<IAuthorizationIdentity>`: Parameter Identitas
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
