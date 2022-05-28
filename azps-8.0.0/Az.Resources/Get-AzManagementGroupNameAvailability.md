---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Resources.dll-Help.xml
Module Name: Az.Resources
online version: https://docs.microsoft.com/powershell/module/az.resources/new-azmanagementgroupsubscription/
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzManagementGroupNameAvailability.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzManagementGroupNameAvailability.md
ms.openlocfilehash: 2fb2cdc5ea8f501a4eb98076424e7d87d62f1489
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145532950"
---
# Get-AzManagementGroupNameAvailability

## SYNOPSIS
Memeriksa apakah nama Grup Manajemen tersedia di Penyewa dan nama yang valid.

## SYNTAX

```
Get-AzManagementGroupNameAvailability [-GroupName] <String> [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
**Get-AzManagementGroupNameAvailability** memeriksa apakah Nama Grup Manajemen Tersedia dan Valid

## EXAMPLES

### Contoh 1: Dapatkan Ketersediaan Nama untuk Nama yang Valid
```powershell
Get-AzManagementGroupNameAvailability -GroupName "testMG"
```

```output
Message              : 
NameAvailable        : True
Reason               :
```

### Contoh 2: Dapatkan Ketersediaan Nama untuk nama yang sudah diambil
```powershell
Get-AzManagementGroupNameAvailability -GroupName "testMG3"
```

```output
Message              : The group with the specified name already exists
NameAvailable        : False
Reason               : AlreadyExists
```

### Contoh 3: Dapatkan Ketersediaan Nama untuk nama yang berisi karakter yang tidak valid
```powershell
Get-AzManagementGroupNameAvailability -GroupName "testMG!"
```

```output
Message              : The provided management group name has invalid characters
NameAvailable        : False
Reason               : Invalid
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
Nama Grup Manajemen

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

### Microsoft.Azure.Commands.Resources.Models.ManagementGroups.PSManagementGroupNameAvailabilityResult

## NOTES

## RELATED LINKS
