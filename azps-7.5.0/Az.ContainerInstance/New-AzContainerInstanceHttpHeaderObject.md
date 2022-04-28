---
external help file: ''
Module Name: Az.ContainerInstance
online version: https://docs.microsoft.com/powershell/module/az.ContainerInstance/New-AzContainerInstanceHttpHeaderObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/New-AzContainerInstanceHttpHeaderObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/New-AzContainerInstanceHttpHeaderObject.md
ms.openlocfilehash: 1ebb0e15412452666048b183cdc63ab41bb75b39
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144219374"
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
New-AzContainerInstanceHttpHeaderObject -name foo -value bar
```

```output
Name Value
---- -----
foo  bar
```

Buat objek Header HTTP yang akan digunakan dalam pemeriksaan keaktifan atau kesiapan.

## PARAMETERS

### -Name
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

### -Nilai
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ContainerInstance.Models.Api20210901.HttpHeader

## NOTES

ALIAS

## RELATED LINKS

