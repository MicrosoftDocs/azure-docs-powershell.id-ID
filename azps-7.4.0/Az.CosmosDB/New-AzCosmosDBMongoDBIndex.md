---
external help file: Microsoft.Azure.PowerShell.Cmdlets.CosmosDB.dll-Help.xml
Module Name: Az.CosmosDB
online version: https://docs.microsoft.com/powershell/module/az.cosmosdb/new-azcosmosdbmongodbindex
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/New-AzCosmosDBMongoDBIndex.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/New-AzCosmosDBMongoDBIndex.md
ms.openlocfilehash: 29e7c50cb43d35902a5c2ef6c0228434ba26c8f2
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144656444"
---
# New-AzCosmosDBMongoDBIndex

## SYNOPSIS
Membuat Indeks CosmosDB MongoDB baru.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.cosmosdb/new-azcosmosdbmongodbindex) untuk informasi terbaru.

## SYNTAX

```
New-AzCosmosDBMongoDBIndex [-TtlInSeconds <Int32>] [-Unique <Boolean>] [-Key <String[]>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
**New-AzCosmosDBMongoDBIndex** membuat Indeks MongoDB CosmosDB baru.

## EXAMPLES

### Contoh 1
```powershell
New-AzCosmosDBMongoDBIndex -TtlInSeconds {val} -Unique 1 -Key "key1"
```

```output
Key                                                       Options
---                                                       -------
Microsoft.Azure.Commands.CosmosDB.Models.PSMongoIndexKeys Microsoft.Azure.Commands.CosmosDB.Models.PSMongoIndexOptions
```

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Kunci
Array nilai kunci sebagai string.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TtlInSeconds
Jumlah detik setelah indeks kedaluwarsa.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Unik
Bool untuk menunjukkan apakah indeks unik atau tidak.

```yaml
Type: System.Nullable`1[System.Boolean]
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

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.CosmosDB.Models.PSMongoIndex

## NOTES

## RELATED LINKS
