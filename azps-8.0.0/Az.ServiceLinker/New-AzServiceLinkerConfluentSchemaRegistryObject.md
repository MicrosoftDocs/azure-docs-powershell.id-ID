---
external help file: ''
Module Name: Az.ServiceLinker
online version: https://docs.microsoft.com/powershell/module/az.ServiceLinker/new-azservicelinkerconfluentschemaregistryobject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceLinker/help/New-AzServiceLinkerConfluentSchemaRegistryObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceLinker/help/New-AzServiceLinkerConfluentSchemaRegistryObject.md
ms.openlocfilehash: 8ff26429c960a88fae6751beaebeb827703407e7
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145559995"
---
# New-AzServiceLinkerConfluentSchemaRegistryObject

## SYNOPSIS
Buat objek dalam memori untuk ConfluentSchemaRegistry.

## SYNTAX

```
New-AzServiceLinkerConfluentSchemaRegistryObject -Endpoint <String> [<CommonParameters>]
```

## DESCRIPTION
Buat objek dalam memori untuk ConfluentSchemaRegistry.

## EXAMPLES

### Contoh 1: Membuat objek sumber daya target untuk registri skema di confluent cloud
```powershell
New-AzServiceLinkerConfluentSchemaRegistryObject -Endpoint "https://psrc-xxxx.westus2.azure.confluent.cloud"
```

```output
Endpoint
--------
https://psrc-xxxx.westus2.azure.confluent.cloud
```

Membuat objek sumber daya target untuk registri skema di confluent cloud

## PARAMETERS

### -Titik akhir
Titik akhir layanan.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ServiceLinker.Models.Api20220501.ConfluentSchemaRegistry

## NOTES

ALIAS

## RELATED LINKS

