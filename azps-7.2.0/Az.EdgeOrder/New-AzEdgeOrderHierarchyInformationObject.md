---
external help file: ''
Module Name: Az.EdgeOrder
online version: https://docs.microsoft.com/powershell/module/az.EdgeOrder/new-AzEdgeOrderHierarchyInformationObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EdgeOrder/help/New-AzEdgeOrderHierarchyInformationObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EdgeOrder/help/New-AzEdgeOrderHierarchyInformationObject.md
ms.openlocfilehash: c148066457e34a67bd8841eddc8f2aed2cab6426
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138271516"
---
# New-AzEdgeOrderHierarchyInformationObject

## SYNOPSIS
Membuat objek di memori untuk HierarchyInformation.

## SYNTAX

```
New-AzEdgeOrderHierarchyInformationObject [-ConfigurationName <String>] [-ProductFamilyName <String>]
 [-ProductLineName <String>] [-ProductName <String>] [<CommonParameters>]
```

## DESCRIPTION
Membuat objek di memori untuk HierarchyInformation.

## EXAMPLES

### Contoh 1: Membuat objek informasi hierarki
```powershell
PS C:\> $HierarchyInformation=New-AzEdgeOrderHierarchyInformationObject -ProductFamilyName "azurestackedge" -ProductLineName "azurestackedge" -ProductName "azurestackedgegpu" -ConfigurationName "EdgeP_High"
PS C:\> $HierarchyInformation | fl

ConfigurationName : EdgeP_High
ProductFamilyName : azurestackedge
ProductLineName   : azurestackedge
ProductName       : azurestackedgegpu
```

Membuat objek informasi hierarki dalam memori

## PARAMETERS

### -ConfigurationName
Mewakili nama konfigurasi yang mengidentifikasi konfigurasi secara unik.

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
Mewakili nama keluarga produk yang mengidentifikasi keluarga produk secara unik.

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
Mewakili nama baris produk yang mengidentifikasi lini produk secara unik.

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
Mewakili nama produk yang mengidentifikasi produk secara unik.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.EdgeOrder.Models.Api20211201.HierarchyInformation

## CATATAN

ALIAS

## RELATED LINKS

