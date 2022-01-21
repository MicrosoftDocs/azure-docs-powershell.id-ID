---
external help file: ''
Module Name: Az.ContainerInstance
online version: https://docs.microsoft.com/powershell/module/az.ContainerInstance/New-AzContainerInstanceHttpHeaderObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/New-AzContainerInstanceHttpHeaderObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/New-AzContainerInstanceHttpHeaderObject.md
ms.openlocfilehash: 8d70ae92ab0614c0415090d0d895f5925979c909
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136570973"
---
# New-AzContainerInstanceHttpHeaderObject

## SYNOPSIS
Membuat objek dalam memori untuk HttpHeader

## SYNTAX

```
New-AzContainerInstanceHttpHeaderObject -Name <String> [-Value <String>] [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk HttpHeader

## EXAMPLES

### Contoh 1: Membuat objek Header HTTP
```powershell
PS C:\> New-AzContainerInstanceHttpHeaderObject -name foo -value bar

Name Value
---- -----
foo  bar
```

Buat objek HTTP Header yang akan digunakan dalam permintaan kesiapan atau kesiapan.

## PARAMETERS

### -Nama
Nama header.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Value
Nilai header..

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ContainerInstance.Models.Api20210901.HttpHeader

## CATATAN

ALIAS

## RELATED LINKS

