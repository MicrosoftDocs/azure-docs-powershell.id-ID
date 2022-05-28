---
external help file: Microsoft.Azure.PowerShell.Cmdlets.CosmosDB.dll-Help.xml
Module Name: Az.CosmosDB
online version: https://docs.microsoft.com/powershell/module/az.cosmosdb/get-azcosmosdbsqlrestorableresource
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/Get-AzCosmosDBSqlRestorableResource.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/Get-AzCosmosDBSqlRestorableResource.md
ms.openlocfilehash: 97740426f48cc6d40b81ef32cb14f14ac5afd91c
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145531414"
---
# Get-AzCosmosDBSqlRestorableResource

## SYNOPSIS
Mencantumkan semua sumber daya azure Cosmos DB SQL yang dapat dipulihkan yang tersedia untuk akun database tertentu pada waktu dan lokasi tertentu.

## SYNTAX

### ByNameParameterSet (Default)
```
Get-AzCosmosDBSqlRestorableResource -Location <String> -DatabaseAccountInstanceId <String>
 -RestoreTimestampInUtc <DateTime> -RestoreLocation <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### ByParentObjectParameterSet
```
Get-AzCosmosDBSqlRestorableResource -Location <String> -DatabaseAccountInstanceId <String>
 -RestoreTimestampInUtc <DateTime> -RestoreLocation <String>
 -InputObject <PSRestorableDatabaseAccountGetResult> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Mencantumkan semua sumber daya azure Cosmos DB SQL yang dapat dipulihkan yang tersedia untuk akun database tertentu pada waktu dan lokasi tertentu.
Daftar ini berguna untuk mengetahui sumber daya apa yang ada di akun sumber pada waktu tertentu. Ini akan memberi pengguna indikasi apa yang diharapkan jika akun dipulihkan ke waktu tertentu.
Pengguna juga dapat menggunakan daftar ini dan menyediakan subset sumber daya yang dapat dipulihkan jika pengguna hanya ingin memulihkan database/kontainer tertentu.

## EXAMPLES

### Contoh 1
```powershell
Get-AzCosmosDBSqlRestorableResource -Location "location" -DatabaseAccountInstanceId "DatabaseInstanceId" -RestoreLocation "Database" -RestoreTimestampInUtc $RestoreTimestamp
```

```output
DatabaseName CollectionNames
------------ ---------------
{DBName}     {Collection names}
```

Mengembalikan daftar semua sumber daya SQL Azure Cosmos DB yang dapat dipulihkan yang tersedia untuk akun database tertentu pada waktu dan lokasi tertentu.

## PARAMETERS

### -DatabaseAccountInstanceId
Id instans akun database CosmosDB.
(Ini dikembalikan sebagai bagian dari properti akun database).

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

### -InputObject
Objek Akun Database CosmosDB yang Dapat Di-restorable

```yaml
Type: Microsoft.Azure.Management.CosmosDB.Models.PSRestorableDatabaseAccountGetResult
Parameter Sets: ByParentObjectParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Lokasi
Nama Lokasi dalam string.

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

### -RestoreLocation
Lokasi akun sumber tempat pemulihan dipicu.
Ini juga akan menjadi wilayah tulis dari akun yang dipulihkan

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

### -RestoreTimestampInUtc
Tanda waktu tempat akun sumber harus dipulihkan.

```yaml
Type: System.DateTime
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

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.CosmosDB.Models.PSDatabaseToRestore

## NOTES

## RELATED LINKS
