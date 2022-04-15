---
external help file: Az.Resources-help.xml
Module Name: Az.Resources
online version: https://docs.microsoft.com/powershell/module/az.resources/get-azroleeligibilityschedulerequest
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzRoleEligibilityScheduleRequest.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzRoleEligibilityScheduleRequest.md
ms.openlocfilehash: c8d61a16aa943fd974e5b5c1f2066a0b22bc68f9
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142166139"
---
# Get-AzRoleEligibilityScheduleRequest

## SYNOPSIS
Dapatkan permintaan jadwal kelayakan peran tertentu.

## SYNTAX

### Daftar (Default)
```
Get-AzRoleEligibilityScheduleRequest -Scope <String> [-Filter <String>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### Mendapatkan
```
Get-AzRoleEligibilityScheduleRequest -Name <String> -Scope <String> [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzRoleEligibilityScheduleRequest -InputObject <IAuthorizationIdentity> [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Dapatkan permintaan jadwal kelayakan peran tertentu.

## EXAMPLES

### Contoh 1: Mencantumkan semua permintaan jadwal penetapan peran untuk sumber daya
```powershell
PS C:\> $scope = "/subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d"
PS C:\> Get-AzRoleEligibilityScheduleRequest -Scope $scope 

Name                                 Type                                                   Scope
----                                 ----                                                   -----
01b86d0b-2d7d-4ee2-bedb-68417ca9cc6a Microsoft.Authorization/roleEligibilityScheduleRequests /subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d
06425dd7-102c-42c2-90c4-b5c630447356 Microsoft.Authorization/roleEligibilityScheduleRequests /subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d
0988b71a-f813-467b-abc0-cef007eddbb5 Microsoft.Authorization/roleEligibilityScheduleRequests /subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d
0cbb19d3-3804-404a-b74a-2f577f8aecbc Microsoft.Authorization/roleEligibilityScheduleRequests /subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d
```

Mengembalikan semua `roleEligibilityScheduleRequests` untuk `scope`.

### Contoh 2: Mencantumkan semua permintaan jadwal penetapan peran saya untuk sumber daya
```powershell
PS C:\> $scope = "/subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d"
PS C:\> Get-AzRoleEligibilityScheduleRequest -Scope $scope -Filter "asTarget()"

Name                                 Type                                                   Scope                                                                       RoleDefinitionId
----                                 ----                                                   -----                                                                       ----------------
2cc018c2-27f8-4730-a0bc-b6a8fcee3e70 Microsoft.Authorization/roleEligibilityScheduleRequests /subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d                         /subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d/prov…
31910719-4f82-443c-9e7a-6bfe4b918e0c Microsoft.Authorization/roleEligibilityScheduleRequests /subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d                         /subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d/prov…
4cd7e26b-8eca-425c-969d-ec708c88bf18 Microsoft.Authorization/roleEligibilityScheduleRequests /subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d                         /subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d/prov…
```

Mengembalikan semua `roleEligibilityScheduleRequests` `scope` yang ditetapkan untuk pengguna panggilan.

### Contoh 3: Mencantumkan semua permintaan jadwal penetapan peran untuk sumber daya di mana pengguna panggilan adalah pemberi persetujuan
```powershell
PS C:\> $scope = "/subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d"
PS C:\> Get-AzRoleEligibilityScheduleRequest -Scope $scope -Filter "asApprover()"

Name                                 Type                                                   Scope                                                                       RoleDefinitionId
----                                 ----                                                   -----                                                                       ----------------
2cc018c2-27f8-4730-a0bc-b6a8fcee3e70 Microsoft.Authorization/roleEligibilityScheduleRequests /subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d                         /subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d/prov…
31910719-4f82-443c-9e7a-6bfe4b918e0c Microsoft.Authorization/roleEligibilityScheduleRequests /subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d                         /subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d/prov…
4cd7e26b-8eca-425c-969d-ec708c88bf18 Microsoft.Authorization/roleEligibilityScheduleRequests /subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d                         /subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d/prov…
```

Mengembalikan semua `roleEligibilitySchedules` untuk `scope` pengguna panggilan yang merupakan penyetuju.

### Contoh 4: Dapatkan permintaan jadwal penetapan peran menurut lingkup dan nama
```powershell
PS C:\> $scope = "/subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d"
PS C:\> Get-AzRoleEligibilityScheduleRequest -Scope $scope -Name "2cc018c2-27f8-4730-a0bc-b6a8fcee3e70"

Name                                 Type                                                   Scope                                               RoleDefinitionId
----                                 ----                                                   -----                                               ----------------
2cc018c2-27f8-4730-a0bc-b6a8fcee3e70 Microsoft.Authorization/roleEligibilityScheduleRequests /subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d /subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d/providers/Microsoft.Authoriz…
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
Filter untuk diterapkan pada operasi.
Gunakan $filter=atScope() untuk mengembalikan semua permintaan jadwal kelayakan peran pada atau di atas lingkup.
Gunakan $filter=principalId eq {id} untuk mengembalikan semua permintaan jadwal kelayakan peran pada, di atas atau di bawah lingkup untuk pokok yang ditentukan.
Gunakan $filter=asRequestor() untuk mengembalikan semua permintaan jadwal kelayakan peran yang diminta oleh pengguna saat ini.
Gunakan $filter=asTarget() untuk mengembalikan semua permintaan jadwal kelayakan peran yang dibuat untuk pengguna saat ini.
Gunakan $filter=asApprover() untuk mengembalikan semua permintaan jadwal kelayakan peran di mana pengguna saat ini adalah penyetuju.

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

### -Nama
Nama (guid) permintaan jadwal kelayakan peran untuk didapatkan.

```yaml
Type: System.String
Parameter Sets: Get
Aliases: RoleEligibilityScheduleRequestName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lingkup
Lingkup permintaan jadwal kelayakan peran.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Resources.Authorization.Models.IAuthorizationIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Resources.Authorization.Models.Api20201001Preview.IRoleEligibilityScheduleRequest

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IAuthorizationIdentity>: Parameter Identitas
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[RoleAssignmentScheduleInstanceName <String>]`: Nama (hash nama jadwal + waktu) dari jadwal penetapan peran yang akan didapatkan.
  - `[RoleAssignmentScheduleName <String>]`: Nama (guid) dari jadwal penetapan peran yang akan didapatkan.
  - `[RoleAssignmentScheduleRequestName <String>]`: Nama penetapan peran untuk dibuat. Ini bisa berupa GUID apa pun yang valid.
  - `[RoleEligibilityScheduleInstanceName <String>]`: Nama (hash nama jadwal + waktu) dari jadwal kelayakan peran untuk mendapatkan.
  - `[RoleEligibilityScheduleName <String>]`: Nama (guid) jadwal kelayakan peran untuk mendapatkan.
  - `[RoleEligibilityScheduleRequestName <String>]`: Nama kelayakan peran untuk dibuat. Ini bisa berupa GUID apa pun yang valid.
  - `[RoleManagementPolicyAssignmentName <String>]`: Nama format {guid_guid} penetapan kebijakan manajemen peran yang akan didapatkan.
  - `[RoleManagementPolicyName <String>]`: Nama (guid) kebijakan manajemen peran yang akan didapatkan.
  - `[Scope <String>]`: Lingkup kebijakan manajemen peran.

## RELATED LINKS
