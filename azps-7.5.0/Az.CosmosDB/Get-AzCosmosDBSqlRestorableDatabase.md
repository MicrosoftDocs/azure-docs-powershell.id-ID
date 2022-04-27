---
external help file: Microsoft.Azure.PowerShell.Cmdlets.CosmosDB.dll-Help.xml
Module Name: Az.CosmosDB
online version: https://docs.microsoft.com/powershell/module/az.cosmosdb/get-azcosmosdbsqlrestorabledatabase
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/Get-AzCosmosDBSqlRestorableDatabase.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/Get-AzCosmosDBSqlRestorableDatabase.md
ms.openlocfilehash: 9c9c444a4987c8dce6c7f43ecb9845cf435ac473
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144207623"
---
# Get-AzCosmosDBSqlRestorableDatabase

## SYNOPSIS
Mendapatkan daftar semua database Azure Cosmos DB Sql yang dapat dipulihkan yang tersedia di bawah akun yang dapat dipulihkan.

## SYNTAX

### ByNameParameterSet (Default)
```
Get-AzCosmosDBSqlRestorableDatabase -Location <String> -DatabaseAccountInstanceId <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByParentObjectParameterSet
```
Get-AzCosmosDBSqlRestorableDatabase -InputObject <PSRestorableDatabaseAccountGetResult>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan daftar semua database Azure Cosmos DB Sql yang dapat dipulihkan yang tersedia di bawah akun yang dapat dipulihkan.
Daftar ini akan memiliki entri yang sesuai untuk membuat, mengganti, dan menghapus peristiwa semua database langsung dan dihapus.
Daftar ini berguna untuk mengidentifikasi tanda waktu pemulihan berdasarkan perubahan dalam database. Misalnya, jika pengguna ingin memulihkan akun database ke tanda waktu saat database bernama foo dihapus, pengguna dapat menemukan peristiwa penghapusan database yang sesuai dari daftar ini, dan memilih tanda waktu sebelum peristiwa penghapusan untuk dipulihkan.

## EXAMPLES

### Contoh 1
```powershell
Get-AzCosmosDBSqlRestorableDatabase -Location {location} -DatabaseAccountInstanceId {DatabaseAccountInstanceIdInstanceId}
```

```output
Name            : cb04fbfc-4142-413d-b2c5-c91723a17e28
Id              : /subscriptions/{subscriptionId}/providers/Microsoft.DocumentDB/locations/{location}/restorableDatabaseAccounts/{DatabaseAccountInstanceIdInstanceId}/restorableSqlDatabases/cb04fbfc-4142-413d-b2c5-c91723
                  a17e28
Type            : Microsoft.DocumentDB/locations/restorableDatabaseAccounts/restorableSqlDatabases
_rid            : a+35ZwAAAA==
OperationType   : Create
EventTimestamp  : 01/20/2021 18:42:37
OwnerId         : foo-db1
OwnerResourceId : Ts0YAA==
Database        : Microsoft.Azure.Management.CosmosDB.Models.PSRestorableSqlDatabasePropertiesResourceDatabase
```

Objek sumber daya berisi properti sumber daya database

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

### Microsoft.Azure.Management.CosmosDB.Models.PSRestorableSqlDatabaseGetResult

## NOTES

## RELATED LINKS
