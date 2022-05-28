---
external help file: Az.Resources-help.xml
Module Name: Az.Resources
online version: https://docs.microsoft.com/powershell/module/az.resources/get-azroleassignmentschedule
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzRoleAssignmentSchedule.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzRoleAssignmentSchedule.md
ms.openlocfilehash: e572ed6b1e1250ff801ab058bfe02dfa53027b06
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145545844"
---
# Get-AzRoleAssignmentSchedule

## SYNOPSIS
Mendapatkan jadwal penetapan peran yang ditentukan untuk cakupan sumber daya

## SYNTAX

### Daftar (Default)
```
Get-AzRoleAssignmentSchedule -Scope <String> [-Filter <String>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### Dapatkan
```
Get-AzRoleAssignmentSchedule -Name <String> -Scope <String> [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzRoleAssignmentSchedule -InputObject <IAuthorizationIdentity> [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan jadwal penetapan peran yang ditentukan untuk cakupan sumber daya

## EXAMPLES

### Contoh 1: Mencantumkan semua jadwal penetapan peran untuk sumber daya
```powershell
PS C:\> $scope = "/subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d"
PS C:\> Get-AzRoleAssignmentSchedule -Scope $scope 

Name                                 Type                                            Scope
----                                 ----                                            -----
986d4ad8-f513-4a21-92e5-7163486e9e7c Microsoft.Authorization/roleAssignmentSchedules /subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d
2066f412-e9bf-406a-962c-df8c16c9f9a0 Microsoft.Authorization/roleAssignmentSchedules /subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d/resourceGroups/UTSept3/providers/Microsoft.Compute/virtualMachines/vmtest123
f402cab4-83ab-4361-8725-2190bbe1ea6b Microsoft.Authorization/roleAssignmentSchedules /subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d/resourceGroups/sbo-test/providers/Microsoft.Web/connections/office365-1
5a12ea85-419e-426b-81f8-20e53808a14c Microsoft.Authorization/roleAssignmentSchedules /providers/Microsoft.Management/managementGroups/PrimaryMG1
```

Mengembalikan semua `roleAssignmentSchedules` untuk `scope`.
Untuk memanggil API, Anda harus memiliki akses ke `Microsoft.Authorization/roleAssignments/read` operasi pada cakupan yang ditentukan.

### Contoh 2: Mencantumkan semua jadwal penetapan peran saya untuk sumber daya
```powershell
PS C:\> $scope = "/" # "/" stands for tenant level resource
PS C:\> Get-AzRoleAssignmentSchedule -Scope $scope -Filter "asTarget()"

Name                                 Type                                            Scope                                                 RoleDefinitionId
----                                 ----                                            -----                                                 ----------------                                                                      
4cd7e26b-8eca-425c-969d-ec708c88bf18 Microsoft.Authorization/roleAssignmentSchedules /subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d   /subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d/providers/Microsoft.Authorizatio… 
a1f32976-b8f4-4606-a91d-af097a2473a2 Microsoft.Authorization/roleAssignmentSchedules /providers/Microsoft.Management/managementGroups/MG-3 /providers/Microsoft.Authorization/roleDefinitions/8e3af657-a8ff-443c-a75c-2fe8c4bcb… 
4f9bdc29-3bb9-4ad7-9c1d-3f3f5ba3e1d9 Microsoft.Authorization/roleAssignmentSchedules /providers/Microsoft.Management/managementGroups/MG-2 /providers/Microsoft.Authorization/roleDefinitions/8e3af657-a8ff-443c-a75c-2fe8c4bcb… 
529e4bba-621c-4309-a4b2-73e3364d4dd3 Microsoft.Authorization/roleAssignmentSchedules /providers/Microsoft.Management/managementGroups/MG-1 /providers/Microsoft.Authorization/roleDefinitions/8e3af657-a8ff-443c-a75c-2fe8c4bcb…
```

Mengembalikan semua `roleAssignmentSchedules` `scope` yang ditetapkan untuk pengguna panggilan.

### Contoh 3: Mencantumkan semua jadwal penetapan peran untuk sumber daya dengan filter
```powershell
PS C:\> $scope = "/subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d"
PS C:\> $filter = "roleDefinitionId eq '/providers/Microsoft.Authorization/roleDefinitions/8e3af657-a8ff-443c-a75c-2fe8c4bcb635'"
PS C:\> Get-AzRoleAssignmentSchedule -Scope $scope -Filter $filter

Name                                 Type                                            Scope                                                                                 RoleDefinitionId
----                                 ----                                            -----                                                                                 ----------------                                      
314aa57e-064d-46c3-964e-a0d20989c1a2 Microsoft.Authorization/roleAssignmentSchedules /subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d                                   /subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d/… 
496794ce-4465-4621-83aa-0b73b3c6fe17 Microsoft.Authorization/roleAssignmentSchedules /subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d                                   /subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d/… 
6461530a-4d10-400e-9eb0-ff7cb73c4ffd Microsoft.Authorization/roleAssignmentSchedules /subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d                                   /subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d/… 
d8daef6c-75da-42eb-9291-7cbc466d5b4b Microsoft.Authorization/roleAssignmentSchedules /subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d                                   /subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d/…
```

Filter yang didukung:
| Filter | Deskripsi |
| --- | --- |
| `atScope()` | Cantumkan penetapan peran hanya untuk cakupan yang ditentukan, tidak termasuk penetapan peran pada sub-cakupan.
|
| `principalId eq '{objectId}'` | Mencantumkan penetapan peran untuk pengguna, grup, atau perwakilan layanan tertentu.
|
| `roleDefinitionId eq '{roleDefinitionId}'` | Mencantumkan penetapan peran untuk definisi peran tertentu.
|
| `status eq '{status}'` | Mencantumkan penetapan peran untuk status tertentu.
|
| `assignedTo('{objectId}')` | Mencantumkan penetapan peran untuk pengguna tertentu, termasuk yang diwarisi dari grup.
|
| `asTarget()` | Mencantumkan penetapan peran untuk pengguna atau perwakilan layanan saat ini, termasuk yang diwarisi dari grup.
|
| `assignedTo('{objectId}')+and+atScope()` | Mencantumkan penetapan peran untuk pengguna tertentu, termasuk yang diwarisi dari grup hanya untuk cakupan yang ditentukan, tidak termasuk penetapan peran pada sub-cakupan.|

### Contoh 4: Mendapatkan jadwal penetapan peran berdasarkan cakupan dan nama
```powershell
PS C:\> $scope = "/subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d"
PS C:\> Get-AzRoleAssignmentSchedule -Scope $scope -Name "4cd7e26b-8eca-425c-969d-ec708c88bf18"

Name                                 Type                                            Scope                                               RoleDefinitionId
----                                 ----                                            -----                                               ----------------                                                                        
4cd7e26b-8eca-425c-969d-ec708c88bf18 Microsoft.Authorization/roleAssignmentSchedules /subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d /subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d/providers/Microsoft.Authorization/…
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

### -Filter
Filter yang akan diterapkan pada operasi.
Gunakan $filter=atScope() untuk mengembalikan semua jadwal penetapan peran pada atau di atas cakupan.
Gunakan $filter=principalId eq {id} untuk mengembalikan semua jadwal penetapan peran pada, di atas atau di bawah cakupan untuk prinsipal yang ditentukan.
Gunakan $filter=assignedTo('{userId}') untuk mengembalikan semua jadwal penetapan peran untuk pengguna saat ini.
Gunakan $filter=asTarget() untuk mengembalikan semua jadwal penetapan peran yang dibuat untuk pengguna saat ini.

```yaml
Type: System.String
Parameter Sets: List
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan buat tabel hash.

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
Nama (guid) dari jadwal penetapan peran yang akan didapatkan.

```yaml
Type: System.String
Parameter Sets: Get
Aliases: RoleAssignmentScheduleName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Cakupan
Cakupan jadwal penetapan peran.

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

### Microsoft.Azure.PowerShell.Cmdlets.Resources.Authorization.Models.Api20201001Preview.IRoleAssignmentSchedule

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
  - `[Scope <String>]`: Ruang lingkup kebijakan manajemen peran.

## RELATED LINKS
