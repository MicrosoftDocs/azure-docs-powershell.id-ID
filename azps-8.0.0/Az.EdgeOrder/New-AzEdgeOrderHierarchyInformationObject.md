---
external help file: ''
Module Name: Az.EdgeOrder
online version: https://docs.microsoft.com/powershell/module/az.EdgeOrder/new-AzEdgeOrderHierarchyInformationObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EdgeOrder/help/New-AzEdgeOrderHierarchyInformationObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EdgeOrder/help/New-AzEdgeOrderHierarchyInformationObject.md
ms.openlocfilehash: 5caa08dc23ca4a6d7889e75fee78be713f82065a
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145544682"
---
# New-AzEdgeOrderHierarchyInformationObject

## SYNOPSIS
Buat objek dalam memori untuk HierarchyInformation.

## SYNTAX

```
New-AzEdgeOrderHierarchyInformationObject [-ConfigurationName <String>] [-ProductFamilyName <String>]
 [-ProductLineName <String>] [-ProductName <String>] [<CommonParameters>]
```

## DESCRIPTION
Buat objek dalam memori untuk HierarchyInformation.

## EXAMPLES

### Contoh 1: Membuat objek informasi hierarki
```powershell
$HierarchyInformation=New-AzEdgeOrderHierarchyInformationObject -ProductFamilyName "azurestackedge" -ProductLineName "azurestackedge" -ProductName "azurestackedgegpu" -ConfigurationName "EdgeP_High"
$HierarchyInformation | Format-List
```

```output
ConfigurationName : EdgeP_High
ProductFamilyName : azurestackedge
ProductLineName   : azurestackedge
ProductName       : azurestackedgegpu
```

Membuat objek informasi hierarki dalam memori

## PARAMETERS

### -ConfigurationName
Mewakili nama konfigurasi yang secara unik mengidentifikasi konfigurasi.

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

### -ProductFamilyName
Mewakili nama keluarga produk yang secara unik mengidentifikasi keluarga produk.

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

### -ProductLineName
Mewakili nama baris produk yang secara unik mengidentifikasi lini produk.

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

### -ProductName
Mewakili nama produk yang secara unik mengidentifikasi produk.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.EdgeOrder.Models.Api20211201.HierarchyInformation

## NOTES

ALIAS

## RELATED LINKS

