---
external help file: ''
Module Name: Az.EdgeOrder
online version: https://docs.microsoft.com/powershell/module/az.EdgeOrder/new-AzEdgeOrderHierarchyInformationObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EdgeOrder/help/New-AzEdgeOrderHierarchyInformationObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EdgeOrder/help/New-AzEdgeOrderHierarchyInformationObject.md
ms.openlocfilehash: cb7d8c4d479e1348e435125adb94d39d1e3dfcab
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143337023"
---
# New-AzEdgeOrderHierarchyInformationObject

## SYNOPSIS
Membuat objek dalam memori untuk HierarchyInformation.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.edgeorder/new-azedgeorderhierarchyinformationobject) untuk informasi terbaru.

## SYNTAX

```
New-AzEdgeOrderHierarchyInformationObject [-ConfigurationName <String>] [-ProductFamilyName <String>]
 [-ProductLineName <String>] [-ProductName <String>] [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk HierarchyInformation.

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
Mewakili nama baris produk yang mengidentifikasi baris produk secara unik.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.EdgeOrder.Models.Api20211201.HierarchyInformation

## NOTES

ALIAS

## RELATED LINKS

