---
external help file: Az.Purview-help.xml
Module Name: Az.Purview
online version: https://docs.microsoft.com/powershell/module/az.Purview/new-AzPurviewAzureSqlDataWarehouseDataSourceObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/New-AzPurviewAzureSqlDataWarehouseDataSourceObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/New-AzPurviewAzureSqlDataWarehouseDataSourceObject.md
ms.openlocfilehash: df03280f433a45eb0a433fca87aa8c422175dda9
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144708850"
---
# New-AzPurviewAzureSqlDataWarehouseDataSourceObject

## SYNOPSIS
Buat objek dalam memori untuk AzureSqlDataWarehouseDataSource.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.purview/new-azpurviewazuresqldatawarehousedatasourceobject) untuk informasi terbaru.

## SYNTAX

```
New-AzPurviewAzureSqlDataWarehouseDataSourceObject -Kind <DataSourceType> [-CollectionReferenceName <String>]
 [-CollectionType <String>] [-Location <String>] [-ResourceGroup <String>] [-ResourceName <String>]
 [-ServerEndpoint <String>] [-SubscriptionId <String>] [<CommonParameters>]
```

## DESCRIPTION
Buat objek dalam memori untuk AzureSqlDataWarehouseDataSource.

## EXAMPLES

### Contoh 1: Membuat objek sumber data gudang data Azure SQL
```powershell
PS C:\> New-AzPurviewAzureSqlDataWarehouseDataSourceObject -Kind 'AzureSqlDataWarehouse' -CollectionReferenceName 'parv-brs-2' -CollectionType 'CollectionReference' -ServerEndpoint 'ause.database.windows.net'

CollectionLastModifiedAt :
CollectionReferenceName  : parv-brs-2
CollectionType           : CollectionReference
CreatedAt                :
Id                       :
Kind                     : AzureSqlDataWarehouse
LastModifiedAt           :
Location                 :
Name                     :
ResourceGroup            :
ResourceName             :
Scan                     :
ServerEndpoint           : ause.database.windows.net
SubscriptionId           :
```

Membuat objek sumber data gudang data Azure SQL

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

### -Lokasi

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

### -ResourceGroup

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

### -ResourceName

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

### -ServerEndpoint

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

### -SubscriptionId

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

### Microsoft.Azure.PowerShell.Cmdlets.Purviewdata.Models.Api20211001Preview.AzureSqlDataWarehouseDataSource

## NOTES

ALIAS

## RELATED LINKS
