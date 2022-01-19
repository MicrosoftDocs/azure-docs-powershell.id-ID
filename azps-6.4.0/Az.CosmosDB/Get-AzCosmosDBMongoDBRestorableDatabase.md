---
external help file: Microsoft.Azure.PowerShell.Cmdlets.CosmosDB.dll-Help.xml
Module Name: Az.CosmosDB
online version: https://docs.microsoft.com/powershell/module/az.cosmosdb/get-azcosmosdbmongodbrestorabledatabase
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/Get-AzCosmosDBMongoDBRestorableDatabase.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/Get-AzCosmosDBMongoDBRestorableDatabase.md
ms.openlocfilehash: 732e23019567e6a4d8daa75faa78dfe8edb90969
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136208609"
---
# Get-AzCosmosDBMongoDBRestorableDatabase

## SYNOPSIS
Dapatkan daftar semua database Azure Cosmos DBDb yang dapat dikembalikan yang tersedia di bawah akun yang dapat dikembalikan.

## SYNTAX

### ByNameParameterSet (Default)
```
Get-AzCosmosDBMongoDBRestorableDatabase -Location <String> -DatabaseAccountInstanceId <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByParentObjectParameterSet
```
Get-AzCosmosDBMongoDBRestorableDatabase -InputObject <PSRestorableDatabaseAccountGetResult>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Dapatkan daftar semua acara database Azure Cosmos DB Azure Cosmos DB yang dapat dikembalikan yang tersedia di bawah akun yang dapat dikembalikan.
Daftar akan memiliki entri yang terkait dengan membuat, mengganti dan menghapus acara semua database langsung dan dihapus.
Daftar ini berguna untuk mengidentifikasi timestamp pemulihan berdasarkan perubahan di database. Misalnya, jika pengguna ingin memulihkan akun database menjadi timestamp saat database bernama foo dihapus, pengguna dapat menemukan kejadian penghapusan database yang terkait dari daftar ini, lalu memilihmp waktu sebelum kejadian penghapusan untuk dipulihkan.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Get-AzCosmosDBMongoDBRestorableDatabase -Location {location} -DatabaseAccountInstanceId {DatabaseAccountInstanceIdInstanceId}

Name            : cb04fbfc-4142-413d-b2c5-c91723a17e28
Id              : /subscriptions/{subscriptionId}/providers/Microsoft.DocumentDB/locations/{location}/restorableDatabaseAccounts/{DatabaseAccountInstanceIdInstanceId}/restorableMongoDBDatabases/cb04fbfc-4142-413d-b2c5-c91723
                  a17e28
Type            : Microsoft.DocumentDB/locations/restorableDatabaseAccounts/restorableMongoDBDatabases
_rid            : a+35ZwAAAA==
OperationType   : Create
EventTimestamp  : 01/20/2021 18:42:37
OwnerId         : foo-db1
OwnerResourceId : Ts0YAA==
```

Objek sumber daya berisi properti sumber daya database

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
Parameter Sets: ByNameParameterSet
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

### Microsoft.Azure.Management.CosmosDB.Models.PSRestorableMongodbDatabaseGetResult

## CATATAN

## RELATED LINKS
