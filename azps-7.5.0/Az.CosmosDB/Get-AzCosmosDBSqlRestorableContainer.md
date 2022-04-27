---
external help file: Microsoft.Azure.PowerShell.Cmdlets.CosmosDB.dll-Help.xml
Module Name: Az.CosmosDB
online version: https://docs.microsoft.com/powershell/module/az.cosmosdb/get-azcosmosdbsqlrestorablecontainer
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/Get-AzCosmosDBSqlRestorableContainer.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/Get-AzCosmosDBSqlRestorableContainer.md
ms.openlocfilehash: be0c2e5e383abd01768ec6707d26df9f8fb608c6
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144207614"
---
# Get-AzCosmosDBSqlRestorableContainer

## SYNOPSIS
Mencantumkan semua kontainer azure Cosmos DB SQL yang dapat dipulihkan yang tersedia untuk database tertentu.

## SYNTAX

### ByNameParameterSet (Default)
```
Get-AzCosmosDBSqlRestorableContainer -Location <String> -DatabaseAccountInstanceId <String>
 -DatabaseRId <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByParentObjectParameterSet
```
Get-AzCosmosDBSqlRestorableContainer -InputObject <PSRestorableSqlDatabaseGetResult>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Mencantumkan semua kontainer azure Cosmos DB SQL yang dapat dipulihkan yang tersedia untuk database tertentu.
Daftar ini akan memiliki entri yang sesuai untuk membuat, mengganti, dan menghapus peristiwa dari semua kontainer langsung dan dihapus di bawah database.
Daftar ini berguna untuk mengidentifikasi tanda waktu pemulihan berdasarkan perubahan dalam kontainer. Misalnya, jika pengguna ingin memulihkan akun database ke tanda waktu saat kontainer tertentu dihapus, pengguna dapat menemukan peristiwa penghapusan koleksi yang sesuai dari daftar ini, dan memilih tanda waktu sebelum peristiwa penghapusan untuk pemulihan.

## EXAMPLES

### Contoh 1
```powershell
Get-AzCosmosDBSqlRestorableContainer -Location {location} -DatabaseAccountInstanceId {DatabaseAccountInstanceIdInstanceId} -DatabaseRId {DatabaseRId}
```

```output
Id              : /subscriptions/{subscriptionId}/providers/Microsoft.DocumentDB/locations/{location}/restorableDatabaseAccounts
                    /{DatabaseAccountInstanceIdInstanceId}/restorableSqlContainers/6a0cb3e4-7d2b-4363-b585-04a3b14ada8c
Name            : 6a0cb3e4-7d2b-4363-b585-04a3b14ada8c
Type            : Microsoft.DocumentDB/locations/restorableDatabaseAccounts/restorableSqlContainers
_rid            : qsLuzwAAAA==
OperationType   : Create
EventTimestamp  : 01/20/2021 18:44:07
OwnerId         : foo-container2
OwnerResourceId : Ts0YAPGKTvw=
Container       : Microsoft.Azure.Management.CosmosDB.Models.PSRestorableSqlContainerPropertiesResourceContainer

Id              : /subscriptions/{subscriptionId}/providers/Microsoft.DocumentDB/locations/{location}/restorableDatabaseAccounts
                    /{DatabaseAccountInstanceIdInstanceId}/restorableSqlContainers/ff36d1d3-f9dc-40a0-a003-60fe349abcfb
Name            : ff36d1d3-f9dc-40a0-a003-60fe349abcfb
Type            : Microsoft.DocumentDB/locations/restorableDatabaseAccounts/restorableSqlContainers
_rid            : Ngu72QAAAA==
OperationType   : Replace
EventTimestamp  : 01/20/2021 18:44:07
OwnerId         : foo-container1
OwnerResourceId : Ts0YAP+RbG0=
Container       : Microsoft.Azure.Management.CosmosDB.Models.PSRestorableSqlContainerPropertiesResourceContainer

Id              : /subscriptions/{subscriptionId}/providers/Microsoft.DocumentDB/locations/{location}/restorableDatabaseAccounts
                    /{DatabaseAccountInstanceIdInstanceId}/restorableSqlContainers/2afb35ba-1755-4fbc-85be-ae175dd0668f
Name            : 2afb35ba-1755-4fbc-85be-ae175dd0668f
Type            : Microsoft.DocumentDB/locations/restorableDatabaseAccounts/restorableSqlContainers
_rid            : lSuf5gAAAA==
OperationType   : Create
EventTimestamp  : 01/20/2021 18:42:43
OwnerId         : foo-container1
OwnerResourceId : Ts0YAP+RbG0=
Container       : Microsoft.Azure.Management.CosmosDB.Models.PSRestorableSqlContainerPropertiesResourceContainer
```

Objek sumber daya berisi properti sumber daya kontainer

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
Objek CosmosDB Restorable Sql Database

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Management.CosmosDB.Models.PSRestorableSqlContainerGetResult

## NOTES

## RELATED LINKS
