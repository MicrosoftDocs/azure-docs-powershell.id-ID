---
external help file: Az.Purview-help.xml
Module Name: Az.Purview
online version: https://docs.microsoft.com/powershell/module/az.Purview/new-AzPurviewPowerBIDataSourceObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/New-AzPurviewPowerBIDataSourceObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/New-AzPurviewPowerBIDataSourceObject.md
ms.openlocfilehash: ba5f7a99444c3f63cb8200da1126269235596ae0
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144737380"
---
# New-AzPurviewPowerBIDataSourceObject

## SYNOPSIS
Buat objek dalam memori untuk PowerBIDataSource.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.purview/new-azpurviewpowerbidatasourceobject) untuk informasi terbaru.

## SYNTAX

```
New-AzPurviewPowerBIDataSourceObject -Kind <DataSourceType> [-CollectionReferenceName <String>]
 [-CollectionType <String>] [-Tenant <String>] [<CommonParameters>]
```

## DESCRIPTION
Buat objek dalam memori untuk PowerBIDataSource.

## EXAMPLES

### Contoh 1: Membuat objek sumber data PowerBI
```powershell
PS C:\> New-AzPurviewPowerBIDataSourceObject -Kind 'PowerBI' -CollectionReferenceName 'parv-brs-2' -CollectionType 'CollectionReference' -Tenant 'xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxx'

CollectionLastModifiedAt :
CollectionReferenceName  : parv-brs-2
CollectionType           : CollectionReference
CreatedAt                :
Id                       :
Kind                     : PowerBI
LastModifiedAt           :
Name                     :
Scan                     :
Tenant                   : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxx
```

Membuat objek sumber data PowerBI

## PARAMETERS

### -CollectionReferenceName

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

### -CollectionType

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

### -Kind

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Purviewdata.Support.DataSourceType
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Penyewa

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

### Microsoft.Azure.PowerShell.Cmdlets.Purviewdata.Models.Api20211001Preview.PowerBiDataSource

## NOTES

ALIAS

## RELATED LINKS
