---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Resources.dll-Help.xml
Module Name: Az.Resources
online version: https://docs.microsoft.com/powershell/module/az.resources/get-azmanagementgroup/
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzManagementGroupHierarchySetting.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzManagementGroupHierarchySetting.md
ms.openlocfilehash: 2e8f12b33ae83dd41566f1241435b5f23dfca3ef
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145537707"
---
# Get-AzManagementGroupHierarchySetting

## SYNOPSIS
Mendapatkan Pengaturan Hierarki di bawah penyewa saat ini

## SYNTAX

### GroupOperations (Default)
```
Get-AzManagementGroupHierarchySetting [-GroupName] <String> [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ParentGroupObject
```
Get-AzManagementGroupHierarchySetting [-GroupName] <String> [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzManagementGroupHierarchySetting** Mendapatkan semua pengaturan hierarki di bawah penyewa saat ini menggunakan parameter **GroupName** .

## EXAMPLES

### Contoh 1: Dapatkan Pengaturan Hierarki
```powershell
Get-AzManagementGroupHierarchySetting -GroupName c7a87cda-9a66-4920-b0f8-869baa04efe0
```

```output
Id          : /providers/Microsoft.Management/managementGroups/c7a87cda-9a66-4920-b0f8-869baa04efe0/settings/default
Type        : Microsoft.Management/managementGroups/settings
Name        : default
TenantId    : 6b2064b9-34bd-46e6-9092-52f2dd5f7fc0
RequireAuthorizationForGroupCreation : true
DefaultManagementGroup : TestGroup
```

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GroupName
Id Grup Manajemen dari Grup Manajemen Akar

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: GroupId

Required: True
Position: 0
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
Menunjukkan yang akan terjadi jika cmdlet dijalankan. Cmdlet tidak dijalankan.

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

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.Resources.Models.ManagementGroups.PSHierarchySettings

### Microsoft.Azure.Commands.Resources.Models.ManagementGroups.PSHierarchySettings

## NOTES

## RELATED LINKS
