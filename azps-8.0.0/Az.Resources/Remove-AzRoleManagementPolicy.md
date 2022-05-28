---
external help file: Az.Resources-help.xml
Module Name: Az.Resources
online version: https://docs.microsoft.com/powershell/module/az.resources/remove-azrolemanagementpolicy
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Remove-AzRoleManagementPolicy.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Remove-AzRoleManagementPolicy.md
ms.openlocfilehash: 73dea47d240f43c5e028f72fc1c4c2d6de72aada
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145522735"
---
# Remove-AzRoleManagementPolicy

## SYNOPSIS
Menghapus kebijakan manajemen peran

## SYNTAX

### Hapus (Default)
```
Remove-AzRoleManagementPolicy -Name <String> -Scope <String> [-DefaultProfile <PSObject>] [-PassThru] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### DeleteViaIdentity
```
Remove-AzRoleManagementPolicy -InputObject <IAuthorizationIdentity> [-DefaultProfile <PSObject>] [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Menghapus kebijakan manajemen peran

## EXAMPLES

### Contoh 1: Menghapus kebijakan manajemen peran
```powershell
PS C:\> $scope = "/subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d/"
PS C:\> Remove-AzRoleManagementPolicy -Scope $scope -Name "0a4d3ef7-147b-4777-a958-ae9dfab3c331"

The requested resource does not support http method 'DELETE'.
```

Operasi ini saat ini tidak didukung

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
Type: Microsoft.Azure.PowerShell.Cmdlets.Resources.Authorization.Models.IAuthorizationIdentity
Parameter Sets: DeleteViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Nama (guid) dari kebijakan manajemen peran ke upsert.

```yaml
Type: System.String
Parameter Sets: Delete
Aliases: RoleManagementPolicyName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Mengembalikan true saat perintah berhasil

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

### -Cakupan
Cakupan kebijakan manajemen peran untuk upsert.

```yaml
Type: System.String
Parameter Sets: Delete
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
Cmdlet tidak dijalankan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
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

### System.Boolean

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
