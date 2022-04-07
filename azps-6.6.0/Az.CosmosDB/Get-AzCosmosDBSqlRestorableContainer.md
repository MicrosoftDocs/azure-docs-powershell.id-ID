---
external help file: Microsoft.Azure.PowerShell.Cmdlets.CosmosDB.dll-Help.xml
Module Name: Az.CosmosDB
online version: https://docs.microsoft.com/powershell/module/az.cosmosdb/get-azcosmosdbsqlrestorablecontainer
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/Get-AzCosmosDBSqlRestorableContainer.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/Get-AzCosmosDBSqlRestorableContainer.md
ms.openlocfilehash: 28ceaa60bce7c8d83070044e2a2d8ae4fb19d23b
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140311369"
---
# Get-AzCosmosDBSqlRestorableContainer

## SYNOPSIS
Mencantumkan semua wadah Azure Cosmos DB SQL yang dapat dikembalikan yang tersedia untuk database tertentu.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.cosmosdb/get-azcosmosdbsqlrestorablecontainer) untuk informasi terkini.

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
Mencantumkan semua wadah Azure Cosmos DB SQL yang dapat dikembalikan yang tersedia untuk database tertentu.
Daftar akan memiliki entri yang terkait dengan membuat, mengganti dan menghapus acara dari semua wadah langsung dan dihapus di bawah database.
Daftar ini berguna untuk mengidentifikasi timestamp pemulihan berdasarkan perubahan pada wadah. Misalnya, jika pengguna ingin memulihkan akun database menjadi timestamp saat wadah tertentu dihapus, pengguna bisa menemukan acara hapus kumpulan terkait dari daftar ini, dan pilih timestamp sebelum menghapus acara untuk dipulihkan.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Get-AzCosmosDBSqlRestorableContainer -Location {location} -DatabaseAccountInstanceId {DatabaseAccountInstanceIdInstanceId} -DatabaseRId {DatabaseRId}

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

Objek sumber daya berisi properti sumber daya wadah

## PARAMETERS

### -DatabaseAccountInstanceId
Contoh Id dari akun database CosmosDB.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Management.CosmosDB.Models.PSRestorableSqlContainerGetResult

## CATATAN

## RELATED LINKS
