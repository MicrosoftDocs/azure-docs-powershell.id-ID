---
external help file: Az.Purview-help.xml
Module Name: Az.Purview
online version: https://docs.microsoft.com/powershell/module/az.Purview/new-AzPurviewAmazonAccountDataSourceObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/New-AzPurviewAmazonAccountDataSourceObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/New-AzPurviewAmazonAccountDataSourceObject.md
ms.openlocfilehash: b6af8d579ca679d3f49d6e3cda295afb2bcff6cc
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142674748"
---
# New-AzPurviewAmazonAccountDataSourceObject

## SYNOPSIS
Membuat objek dalam memori untuk AmazonAccountDataSource.

## SYNTAX

```
New-AzPurviewAmazonAccountDataSourceObject -Kind <DataSourceType> [-AwsAccountId <String>]
 [-CollectionReferenceName <String>] [-CollectionType <String>] [-RoleArn <String>] [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk AmazonAccountDataSource.

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

### -Jenis

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Purviewdata.Models.Api20211001Preview.AmazonAccountDataSource

## NOTES

ALIAS

## RELATED LINKS
