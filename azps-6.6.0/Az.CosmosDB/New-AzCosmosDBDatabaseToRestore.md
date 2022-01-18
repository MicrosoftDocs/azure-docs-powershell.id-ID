---
external help file: Microsoft.Azure.PowerShell.Cmdlets.CosmosDB.dll-Help.xml
Module Name: Az.CosmosDB
online version: https://docs.microsoft.com/powershell/module/az.cosmosdb/new-azcosmosdbdatabasetorestore
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/New-AzCosmosDBDatabaseToRestore.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/New-AzCosmosDBDatabaseToRestore.md
ms.openlocfilehash: a6f8f5f051b09232bff3a54e186fd1d6427ef596
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/02/2021
ms.locfileid: "136157339"
---
# New-AzCosmosDBDatabaseToRestore

## SYNOPSIS
Membuat Database CosmosDB baru untuk Memulihkan objek(PSDatabaseToRestore)

## SYNTAX

```
New-AzCosmosDBDatabaseToRestore -DatabaseName <String> [-CollectionName <String[]>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Membuat objek CosmosDB DatabaseToRestore baru(PSDatabaseToRestore). Objek yang dikembalikan ini dapat digunakan untuk meminta subkumpulan database dan koleksi untuk dipulihkan.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> New-AzCosmosDBDatabaseToRestore -DatabaseName database1 -CollectionName collection1,collection2,collection3

DatabaseName CollectionNames
------------ ---------------
database1    {collection1, collection2, collection3}
```

Membuat objek DatabaseToRestore baru dengan nama database1 dan koleksi dengan nama koleksi1, koleksi2 dan koleksi3.

## PARAMETERS

### -CollectionName
Nama koleksi yang akan dipulihkan.
(Jika tidak diberikan, semua koleksi akan dipulihkan)

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

### -DatabaseName
Nama database yang akan dipulihkan

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.CosmosDB.Models.PSDatabaseToRestore

## CATATAN

## RELATED LINKS
