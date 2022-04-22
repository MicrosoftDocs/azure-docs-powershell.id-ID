---
external help file: Microsoft.Azure.PowerShell.Cmdlets.CosmosDB.dll-Help.xml
Module Name: Az.CosmosDB
online version: https://docs.microsoft.com/powershell/module/az.cosmosdb/get-azcosmosdbmongodbrestorablecollection
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/Get-AzCosmosDBMongoDBRestorableCollection.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/Get-AzCosmosDBMongoDBRestorableCollection.md
ms.openlocfilehash: 3987361af5d0a5e06522ce95b62fc7c27f0f6f1a
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143019035"
---
# Get-AzCosmosDBMongoDBRestorableCollection

## SYNOPSIS
Mencantumkan semua kumpulan Azure Cosmos DB MongoDB yang dapat dipulihkan yang tersedia untuk database tertentu.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.cosmosdb/get-azcosmosdbmongodbrestorablecollection) untuk informasi terbaru.

## SYNTAX

### ByNameParameterSet (Default)
```
Get-AzCosmosDBMongoDBRestorableCollection -Location <String> -DatabaseAccountInstanceId <String>
 -DatabaseRId <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByParentObjectParameterSet
```
Get-AzCosmosDBMongoDBRestorableCollection -InputObject <PSRestorableSqlDatabaseGetResult>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Mencantumkan semua kumpulan Azure Cosmos DB MongoDB yang dapat dipulihkan yang tersedia untuk database tertentu.
Daftar akan memiliki entri yang terkait dengan pembuatan, penggantian, dan penghapusan acara semua koleksi langsung dan dihapus di bawah database tertentu.
Daftar ini berguna untuk mengidentifikasi cap waktu pemulihan berdasarkan perubahan dalam kumpulan. Misalnya, jika pengguna ingin memulihkan akun database ke stempel waktu ketika kumpulan tertentu dihapus, pengguna dapat menemukan kejadian penghapusan koleksi terkait dari daftar ini, dan memilih cap waktu sebelum acara penghapusan untuk dipulihkan.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Get-AzCosmosDBMongoDBRestorableCollection -Location {locationName} -DatabaseAccountInstanceId {DatabaseAccountInstanceIdInstanceId} -DatabaseRId {DatabaseRId}

Id              : /subscriptions/{subscriptionId}/providers/Microsoft.DocumentDB/locations/{locationName}/restorableDatabaseAccounts
                    /{DatabaseAccountInstanceIdInstanceId}/restorableMongoDBCollections/6a0cb3e4-7d2b-4363-b585-04a3b14ada8c
Name            : 6a0cb3e4-7d2b-4363-b585-04a3b14ada8c
Type            : Microsoft.DocumentDB/locations/restorableDatabaseAccounts/restorableMongoDBCollections
_rid            : qsLuzwAAAA==
OperationType   : Create
EventTimestamp  : 01/20/2021 18:44:07
OwnerId         : foo-collection2
OwnerResourceId : Ts0YAPGKTvw=

Id              : /subscriptions/{subscriptionId}/providers/Microsoft.DocumentDB/locations/{locationName}/restorableDatabaseAccounts
                    /{DatabaseAccountInstanceIdInstanceId}/restorableMongoDBCollections/ff36d1d3-f9dc-40a0-a003-60fe349abcfb
Name            : ff36d1d3-f9dc-40a0-a003-60fe349abcfb
Type            : Microsoft.DocumentDB/locations/restorableDatabaseAccounts/restorableMongoDBCollections
_rid            : Ngu72QAAAA==
OperationType   : Replace
EventTimestamp  : 01/20/2021 18:44:07
OwnerId         : foo-collection1
OwnerResourceId : Ts0YAP+RbG0=

Id              : /subscriptions/{subscriptionId}/providers/Microsoft.DocumentDB/locations/{locationName}/restorableDatabaseAccounts
                    /{DatabaseAccountInstanceIdInstanceId}/restorableMongoDBCollections/2afb35ba-1755-4fbc-85be-ae175dd0668f
Name            : 2afb35ba-1755-4fbc-85be-ae175dd0668f
Type            : Microsoft.DocumentDB/locations/restorableDatabaseAccounts/restorableMongoDBCollections
_rid            : lSuf5gAAAA==
OperationType   : Create
EventTimestamp  : 01/20/2021 18:42:43
OwnerId         : foo-collection1
OwnerResourceId : Ts0YAP+RbG0=
```

Objek sumber daya berisi properti sumber daya kumpulan

## PARAMETERS

### -DatabaseAccountInstanceId
Id instans akun database CosmosDB.
(Ini dikembalikan sebagai bagian dari properti akun database).

```yaml
Type: System.String
Parameter Sets: ByNameParameterSet
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

### -DatabaseRId
ResourceId database.

```yaml
Type: System.String
Parameter Sets: ByNameParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Objek Database MongoDB Yang Dapat Dipulihkan CosmosDB

```yaml
Type: Microsoft.Azure.Management.CosmosDB.Models.PSRestorableSqlDatabaseGetResult
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
Parameter Sets: ByNameParameterSet
Aliases:

Required: True
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

### Microsoft.Azure.Management.CosmosDB.Models.PSRestorableMongodbCollectionGetResult

## NOTES

## RELATED LINKS
