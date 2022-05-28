---
external help file: ''
Module Name: Az.Cdn
online version: https://docs.microsoft.com/powershell/module/az.Cdn/new-AzFrontDoorCdnRuleUrlFileExtensionConditionObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/help/New-AzFrontDoorCdnRuleUrlFileExtensionConditionObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/help/New-AzFrontDoorCdnRuleUrlFileExtensionConditionObject.md
ms.openlocfilehash: 852c0ff566f21c2d29aef17daec238d49fa43218
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145515490"
---
# New-AzFrontDoorCdnRuleUrlFileExtensionConditionObject

## SYNOPSIS
Buat objek dalam memori untuk DeliveryRuleUrlFileExtensionCondition.

## SYNTAX

```
New-AzFrontDoorCdnRuleUrlFileExtensionConditionObject -Name <MatchVariable>
 -ParameterOperator <UrlFileExtensionOperator> [-ParameterMatchValue <String[]>]
 [-ParameterNegateCondition <Boolean>] [-ParameterTransform <Transform[]>] [<CommonParameters>]
```

## DESCRIPTION
Buat objek dalam memori untuk DeliveryRuleUrlFileExtensionCondition.

## EXAMPLES

### Contoh 1: {{ Tambahkan judul di sini }}
```powershell
{{ Add code here }}
```

```output
{{ Add output here }}
```

{{ Tambahkan deskripsi di sini }}

### Contoh 2: {{ Tambahkan judul di sini }}
```powershell
{{ Add code here }}
```

```output
{{ Add output here }}
```

{{ Tambahkan deskripsi di sini }}

## PARAMETERS

### -Name
Nama kondisi untuk aturan pengiriman.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Support.MatchVariable
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ParameterMatchValue
Nilai kecocokan untuk kondisi aturan pengiriman.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ParameterNegateCondition
Menjelaskan apakah ini meniadakan kondisi atau tidak.

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ParameterOperator
Menjelaskan operator yang akan dicocokkan.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Support.UrlFileExtensionOperator
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ParameterTransform
Daftar transformasi.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Support.Transform[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.Api20210601.DeliveryRuleUrlFileExtensionCondition

## NOTES

ALIAS

## RELATED LINKS

