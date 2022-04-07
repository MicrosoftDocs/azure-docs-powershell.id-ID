---
external help file: Microsoft.Azure.PowerShell.Cmdlets.CosmosDB.dll-Help.xml
Module Name: Az.CosmosDB
online version: https://docs.microsoft.com/powershell/module/az.cosmosdb/get-azcosmosdbmongodbcollectionbackupinformation
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/Get-AzCosmosDBMongoDBCollectionBackupInformation.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/Get-AzCosmosDBMongoDBCollectionBackupInformation.md
ms.openlocfilehash: ee4722e73d6f4358a16221a953a3c4bf0807a1af
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140334599"
---
# Get-AzCosmosDBMongoDBCollectionBackupInformation

## SYNOPSIS
Mengambil timestamp terbaru yang dapat dikembalikan untuk koleksidbdb.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.cosmosdb/get-azcosmosdbmongodbcollectionbackupinformation) untuk informasi terkini.

## SYNTAX

```
Get-AzCosmosDBMongoDBCollectionBackupInformation -ResourceGroupName <String> -AccountName <String>
 -DatabaseName <String> -Name <String> -Location <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Mengambil timestamp terbaru yang dapat dikembalikan untuk koleksidbdb. This is the latest timestamp upto which user can successfully restore this collection.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Get-AzCosmosDBMongoDBCollectionBackupInformation -ResourceGroupName CosmosDBResourceGroup3668 -AccountName pitr-sql-stage-source -DatabaseName TestDB1 -Name TestCollectionInDB1 -Location "EAST US 2"

LatestRestorableTimestamp
-------------------------
1623042210
```

Mengambil timestamp terbaru yang dapat dikembalikan untuk koleksidbdb. This is the latest timestamp upto which user can successfully restore this collection.

## PARAMETERS

### -Nama Akun
Nama akun database Cosmos DB.

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

### -DatabaseName
Nama database.

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

### -Lokasi
-Nama Lokasi dalam string.

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

### -Nama
Nama koleksi.

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

### -ResourceGroupName
Nama grup sumber daya.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.CosmosDB.Models.Restore.Database.PSMongoDBBackupInformation

## CATATAN

## RELATED LINKS
