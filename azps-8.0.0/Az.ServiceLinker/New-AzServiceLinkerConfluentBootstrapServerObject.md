---
external help file: ''
Module Name: Az.ServiceLinker
online version: https://docs.microsoft.com/powershell/module/az.ServiceLinker/new-azservicelinkerconfluentbootstrapserverobject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceLinker/help/New-AzServiceLinkerConfluentBootstrapServerObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceLinker/help/New-AzServiceLinkerConfluentBootstrapServerObject.md
ms.openlocfilehash: b760cb9c50b6773bdd96019b93432123318a8c58
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145531867"
---
# New-AzServiceLinkerConfluentBootstrapServerObject

## SYNOPSIS
Buat objek dalam memori untuk ConfluentBootstrapServer.

## SYNTAX

```
New-AzServiceLinkerConfluentBootstrapServerObject -Endpoint <String> [<CommonParameters>]
```

## DESCRIPTION
Buat objek dalam memori untuk ConfluentBootstrapServer.

## EXAMPLES

### Contoh 1: Membuat objek sumber daya target untuk server Kafka di cloud Confluent
```powershell
New-AzServiceLinkerConfluentBootstrapServerObject -Endpoint "pkc-xxxx.eastus.azure.confluent.cloud:9092"
```

```output
Endpoint
--------
pkc-xxxx.eastus.azure.confluent.cloud:9092
```

Membuat objek sumber daya target untuk server Kafka di cloud Confluent

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

### Microsoft.Azure.PowerShell.Cmdlets.ServiceLinker.Models.Api20220501.ConfluentBootstrapServer

## NOTES

ALIAS

## RELATED LINKS

