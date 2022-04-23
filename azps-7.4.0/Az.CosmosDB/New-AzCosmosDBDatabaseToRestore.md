---
external help file: Microsoft.Azure.PowerShell.Cmdlets.CosmosDB.dll-Help.xml
Module Name: Az.CosmosDB
online version: https://docs.microsoft.com/powershell/module/az.cosmosdb/new-azcosmosdbdatabasetorestore
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/New-AzCosmosDBDatabaseToRestore.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/New-AzCosmosDBDatabaseToRestore.md
ms.openlocfilehash: 5021e40e2d35949f5d13f41bc6e51a718ead817c
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143064701"
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
Membuat objek CosmosDB DatabaseToRestore baru(PSDatabaseToRestore). Objek yang dikembalikan ini dapat digunakan untuk menyempurnakan subset database dan kumpulan untuk dipulihkan.

## EXAMPLES

### Contoh 1
```powershell
New-AzCosmosDBDatabaseToRestore -DatabaseName database1 -CollectionName collection1,collection2,collection3
```

```output
DatabaseName CollectionNames
------------ ---------------
database1    {collection1, collection2, collection3}
```

Membuat objek DatabaseToRestore baru dengan database nama1 dan koleksi dengan koleksi nama1, koleksi2, dan koleksi3.

## PARAMETERS

### -CollectionName
Nama koleksi yang akan dipulihkan.
(Jika tidak disediakan, semua koleksi akan dipulihkan)

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### Microsoft.Azure.Commands.CosmosDB.Models.PSDatabaseToRestore

## NOTES

## RELATED LINKS
