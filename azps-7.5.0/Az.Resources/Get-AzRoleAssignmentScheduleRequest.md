---
external help file: Az.Resources-help.xml
Module Name: Az.Resources
online version: https://docs.microsoft.com/powershell/module/az.resources/get-azroleassignmentschedulerequest
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzRoleAssignmentScheduleRequest.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzRoleAssignmentScheduleRequest.md
ms.openlocfilehash: ea289660e61f713138c1ea996f13194787064bef
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145642256"
---
# Get-AzRoleAssignmentScheduleRequest

## SYNOPSIS
Dapatkan permintaan jadwal penetapan peran yang ditentukan.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.resources/get-azroleassignmentschedulerequest) untuk informasi terbaru.

## SYNTAX

### Daftar (Default)
```
Get-AzRoleAssignmentScheduleRequest -Scope <String> [-Filter <String>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### Dapatkan
```
Get-AzRoleAssignmentScheduleRequest -Name <String> -Scope <String> [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzRoleAssignmentScheduleRequest -InputObject <IAuthorizationIdentity> [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Dapatkan permintaan jadwal penetapan peran yang ditentukan.

## EXAMPLES

### Contoh 1: Mencantumkan semua permintaan jadwal penetapan peran untuk sumber daya
```powershell
PS C:\> $scope = "/subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d"
PS C:\> Get-AzRoleAssignmentScheduleRequest -Scope $scope 

Name                                 Type                                                   Scope
----                                 ----                                                   -----
01b86d0b-2d7d-4ee2-bedb-68417ca9cc6a Microsoft.Authorization/roleAssignmentScheduleRequests /subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d
06425dd7-102c-42c2-90c4-b5c630447356 Microsoft.Authorization/roleAssignmentScheduleRequests /subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d
0988b71a-f813-467b-abc0-cef007eddbb5 Microsoft.Authorization/roleAssignmentScheduleRequests /subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d
0cbb19d3-3804-404a-b74a-2f577f8aecbc Microsoft.Authorization/roleAssignmentScheduleRequests /subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d
```

Mengembalikan semua `roleAssignmentScheduleRequests` untuk `scope`.

### Contoh 2: Mencantumkan semua permintaan jadwal penetapan peran saya untuk sumber daya
```powershell
PS C:\> $scope = "/subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d"
PS C:\> Get-AzRoleAssignmentScheduleRequest -Scope $scope -Filter "asTarget()"

Name                                 Type                                                   Scope                                                                       RoleDefinitionId
----                                 ----                                                   -----                                                                       ----------------
2cc018c2-27f8-4730-a0bc-b6a8fcee3e70 Microsoft.Authorization/roleAssignmentScheduleRequests /subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d                         /subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d/prov…
31910719-4f82-443c-9e7a-6bfe4b918e0c Microsoft.Authorization/roleAssignmentScheduleRequests /subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d                         /subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d/prov…
4cd7e26b-8eca-425c-969d-ec708c88bf18 Microsoft.Authorization/roleAssignmentScheduleRequests /subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d                         /subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d/prov…
```

Mengembalikan semua `roleAssignmentScheduleRequests` `scope` yang ditetapkan untuk pengguna panggilan.

### Contoh 3: Mencantumkan semua permintaan jadwal penetapan peran untuk sumber daya di mana pengguna panggilan adalah pemberi persetujuan
```powershell
PS C:\> $scope = "/subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d"
PS C:\> Get-AzRoleAssignmentScheduleRequest -Scope $scope -Filter "asApprover()"

Name                                 Type                                                   Scope                                                                       RoleDefinitionId
----                                 ----                                                   -----                                                                       ----------------
2cc018c2-27f8-4730-a0bc-b6a8fcee3e70 Microsoft.Authorization/roleAssignmentScheduleRequests /subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d                         /subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d/prov…
31910719-4f82-443c-9e7a-6bfe4b918e0c Microsoft.Authorization/roleAssignmentScheduleRequests /subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d                         /subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d/prov…
4cd7e26b-8eca-425c-969d-ec708c88bf18 Microsoft.Authorization/roleAssignmentScheduleRequests /subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d                         /subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d/prov…
```

Mengembalikan semua `roleAssignmentScheduleRequests` untuk `scope` tempat pengguna panggilan adalah pemberi persetujuan.

### Contoh 4: Mendapatkan permintaan jadwal penetapan peran berdasarkan cakupan dan nama
```powershell
PS C:\> $scope = "/subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d"
PS C:\> Get-AzRoleAssignmentScheduleRequest -Scope $scope -Name "2cc018c2-27f8-4730-a0bc-b6a8fcee3e70"

Name                                 Type                                                   Scope                                               RoleDefinitionId
----                                 ----                                                   -----                                               ----------------
2cc018c2-27f8-4730-a0bc-b6a8fcee3e70 Microsoft.Authorization/roleAssignmentScheduleRequests /subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d /subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d/providers/Microsoft.Authoriz…
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
Gunakan $filter=atScope() untuk mengembalikan semua permintaan jadwal penetapan peran pada atau di atas cakupan.
Gunakan $filter=principalId eq {id} untuk mengembalikan semua permintaan jadwal penetapan peran pada, di atas atau di bawah cakupan untuk prinsipal yang ditentukan.
Gunakan $filter=asRequestor() untuk mengembalikan semua permintaan jadwal penetapan peran yang diminta oleh pengguna saat ini.
Gunakan $filter=asTarget() untuk mengembalikan semua permintaan jadwal penetapan peran yang dibuat untuk pengguna saat ini.
Gunakan $filter=asApprover() untuk mengembalikan semua permintaan jadwal penetapan peran di mana pengguna saat ini adalah pemberi izin.

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
Nama (guid) dari permintaan jadwal penetapan peran yang akan didapatkan.

```yaml
Type: System.String
Parameter Sets: Get
Aliases: RoleAssignmentScheduleRequestName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Cakupan
Cakupan permintaan jadwal penetapan peran.

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

### Microsoft.Azure.PowerShell.Cmdlets.Resources.Authorization.Models.Api20201001Preview.IRoleAssignmentScheduleRequest

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
