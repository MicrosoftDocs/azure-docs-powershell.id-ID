---
external help file: Az.Resources-help.xml
Module Name: Az.Resources
online version: https://docs.microsoft.com/powershell/module/az.resources/remove-azrolemanagementpolicyassignment
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Remove-AzRoleManagementPolicyAssignment.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Remove-AzRoleManagementPolicyAssignment.md
ms.openlocfilehash: 0ed985049551a31714c1346f3b9d319d3ba8489a
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142935281"
---
# Remove-AzRoleManagementPolicyAssignment

## SYNOPSIS
Menghapus penetapan kebijakan manajemen peran

## SYNTAX

### Hapus (Default)
```
Remove-AzRoleManagementPolicyAssignment -Name <String> -Scope <String> [-DefaultProfile <PSObject>] [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### DeleteViaIdentity
```
Remove-AzRoleManagementPolicyAssignment -InputObject <IAuthorizationIdentity> [-DefaultProfile <PSObject>]
 [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Menghapus penetapan kebijakan manajemen peran

## EXAMPLES

### Contoh 1: Menghapus penetapan kebijakan manajemen peran
```powershell
PS C:\> $scope = "/subscriptions/38ab2ccc-3747-4567-b36b-9478f5602f0d/"
PS C:\> Remove-AzRoleManagementPolicyAssignment -Scope $scope -Name "588b80cc-f50c-4616-acc9-0003872624db_00493d72-78f6-4148-b6c5-d3ce8e4799dd"

Remove-AzRoleManagementPolicyAssignment_Delete: The requested resource does not support http method 'DELETE'.
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
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

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

### -Nama
Nama format {guid_guid} penetapan kebijakan manajemen peran untuk dihapus.

```yaml
Type: System.String
Parameter Sets: Delete
Aliases: RoleManagementPolicyAssignmentName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Mengembalikan true ketika perintah berhasil

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

### -Lingkup
Lingkup penetapan kebijakan manajemen peran untuk dihapus.

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

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

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
  - `[RoleAssignmentScheduleRequestName <String>]`: Nama penetapan peran untuk dibuat. Ini bisa berupa GUID apa pun yang valid.
  - `[RoleEligibilityScheduleInstanceName <String>]`: Nama (hash nama jadwal + waktu) dari jadwal kelayakan peran untuk mendapatkan.
  - `[RoleEligibilityScheduleName <String>]`: Nama (guid) jadwal kelayakan peran untuk mendapatkan.
  - `[RoleEligibilityScheduleRequestName <String>]`: Nama kelayakan peran untuk dibuat. Ini bisa berupa GUID apa pun yang valid.
  - `[RoleManagementPolicyAssignmentName <String>]`: Nama format {guid_guid} penetapan kebijakan manajemen peran yang akan didapatkan.
  - `[RoleManagementPolicyName <String>]`: Nama (guid) kebijakan manajemen peran yang akan didapatkan.
  - `[Scope <String>]`: Lingkup kebijakan manajemen peran.

## RELATED LINKS
