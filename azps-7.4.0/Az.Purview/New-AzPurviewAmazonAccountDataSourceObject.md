---
external help file: Az.Purview-help.xml
Module Name: Az.Purview
online version: https://docs.microsoft.com/powershell/module/az.Purview/new-AzPurviewAmazonAccountDataSourceObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/New-AzPurviewAmazonAccountDataSourceObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/New-AzPurviewAmazonAccountDataSourceObject.md
ms.openlocfilehash: 7a3d645a7165b971f41dab7e6bd84fa1980aa624
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144646114"
---
# New-AzPurviewAmazonAccountDataSourceObject

## SYNOPSIS
Buat objek dalam memori untuk AmazonAccountDataSource.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.purview/new-azpurviewamazonaccountdatasourceobject) untuk informasi terbaru.

## SYNTAX

```
New-AzPurviewAmazonAccountDataSourceObject -Kind <DataSourceType> [-AwsAccountId <String>]
 [-CollectionReferenceName <String>] [-CollectionType <String>] [-RoleArn <String>] [<CommonParameters>]
```

## DESCRIPTION
Buat objek dalam memori untuk AmazonAccountDataSource.

## EXAMPLES

### Contoh 1: Membuat objek sumber data Akun Amazon
```powershell
PS C:\> New-AzPurviewAmazonAccountDataSourceObject -Kind 'AmazonAccount' -AwsAccountId 123456789012 -CollectionReferenceName parv-brs-2 -CollectionType 'CollectionReference'

AwsAccountId             : 123456789012
CollectionLastModifiedAt :
CollectionReferenceName  : parv-brs-2
CollectionType           : CollectionReference
CreatedAt                :
Id                       :
Kind                     : AmazonAccount
LastModifiedAt           :
Name                     :
RoleArn                  :
Scan                     :
```

Membuat objek sumber data Akun Amazon

## PARAMETERS

### -AwsAccountId

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

### -RoleArn

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

### Microsoft.Azure.PowerShell.Cmdlets.Purviewdata.Models.Api20211001Preview.AmazonAccountDataSource

## NOTES

ALIAS

## RELATED LINKS
