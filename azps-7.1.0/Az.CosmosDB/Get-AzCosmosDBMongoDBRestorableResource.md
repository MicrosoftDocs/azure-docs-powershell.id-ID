---
external help file: Microsoft.Azure.PowerShell.Cmdlets.CosmosDB.dll-Help.xml
Module Name: Az.CosmosDB
online version: https://docs.microsoft.com/powershell/module/az.cosmosdb/get-azcosmosdbmongodbrestorableresource
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/Get-AzCosmosDBMongoDBRestorableResource.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/Get-AzCosmosDBMongoDBRestorableResource.md
ms.openlocfilehash: 9f762cb0e98b7fd5eaa0aaba6e9c917d8406a792
ms.sourcegitcommit: e109cc5320478db6aa8a52d49996b133007a65b9
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 01/12/2022
ms.locfileid: "136711260"
---
# Get-AzCosmosDBMongoDBRestorableResource

## SYNOPSIS
Mencantumkan semua sumber daya Azure Cosmos DB Database yang dapat dikembalikan yang tersedia untuk akun database tertentu pada waktu dan lokasi tertentu.

## SYNTAX

### ByNameParameterSet (Default)
```
Get-AzCosmosDBMongoDBRestorableResource -Location <String> -DatabaseAccountInstanceId <String>
 -RestoreTimestampInUtc <DateTimeOffset> -RestoreLocation <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### ByParentObjectParameterSet
```
Get-AzCosmosDBMongoDBRestorableResource -Location <String> -DatabaseAccountInstanceId <String>
 -RestoreTimestampInUtc <DateTimeOffset> -RestoreLocation <String>
 -InputObject <PSRestorableDatabaseAccountGetResult> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Mencantumkan semua sumber daya Azure Cosmos DB Database yang dapat dikembalikan yang tersedia untuk akun database tertentu pada waktu dan lokasi tertentu.
Daftar ini berguna untuk mengetahui sumber daya apa yang ada di akun sumber pada waktu tertentu. Ini akan menyediakan petunjuk kepada pengguna tentang apa yang akan terjadi jika akun dipulihkan ke waktu tertentu.
Pengguna juga dapat menggunakan daftar ini dan menyediakan subset sumber daya yang dapat dipulihkan jika pengguna hanya ingin memulihkan database/kumpulan tertentu.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Get-AzCosmosDBMongoDBRestorableResource -Location {location} -DatabaseAccountInstanceId {DatabaseInstanceId} -RestoreLocation {Database} -RestoreTimestampInUtc {RestoreTimestamp}

DatabaseName CollectionNames
------------ ---------------
{DBName}     {Collection names}
```

Mengembalikan daftar semua sumber daya Azure Cosmos DB Database yang dapat dikembalikan yang tersedia untuk akun database tertentu pada waktu dan lokasi tertentu.

## PARAMETERS

### -DatabaseAccountInstanceId
Contoh Id dari akun database CosmosDB.
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

### -RestoreLocation
Lokasi akun sumber asal pemulihan dipicu.
Ini juga akan menjadi kawasan penulisan dari akun yang dipulihkan

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
Timestamp tempat akun sumber harus dipulihkan.

```yaml
Type: System.DateTimeOffset
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Objek Akun Database Yang Dapat Dikembalikan CosmosDB

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.CosmosDB.Models.PSDatabaseToRestore

## CATATAN

## RELATED LINKS
