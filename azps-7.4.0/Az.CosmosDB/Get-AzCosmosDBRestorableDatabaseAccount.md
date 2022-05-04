---
external help file: Microsoft.Azure.PowerShell.Cmdlets.CosmosDB.dll-Help.xml
Module Name: Az.CosmosDB
online version: https://docs.microsoft.com/powershell/module/az.cosmosdb/get-azcosmosdbrestorabledatabaseaccount
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/Get-AzCosmosDBRestorableDatabaseAccount.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/Get-AzCosmosDBRestorableDatabaseAccount.md
ms.openlocfilehash: 87d26be47193bfec29ae6f3325612ef3dfb0efb3
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144617648"
---
# Get-AzCosmosDBRestorableDatabaseAccount

## SYNOPSIS
Mendapatkan objek akun database yang dapat di memulihkan

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.cosmosdb/get-azcosmosdbrestorabledatabaseaccount) untuk informasi terbaru.

## SYNTAX

```
Get-AzCosmosDBRestorableDatabaseAccount [-Location <String>] [-DatabaseAccountInstanceId <String>]
 [-DatabaseAccountName <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan daftar semua objek akun database yang dapat di memulihkan di akun tertentu, atau objek akun database tertentu yang dapat di memulihkan dengan instanceId dan lokasi yang diberikan

## EXAMPLES

### Contoh 1
```powershell
Get-AzCosmosDBRestorableDatabaseAccount
```

```output
Id                        : /subscriptions/{subscriptionId}/providers/Microsoft.DocumentDB/locations/westus/restorableDatabaseAccounts/fb8f230e-bab0-452b-81cf-e32643ccc898
DatabaseAccountInstanceId : fb8f230e-bab0-452b-81cf-e32643ccc898
Location                  : West US
DatabaseAccountName       : deleted-account-1
CreationTime              : 8/2/2020 10:23:00 PM
DeletionTime              : 8/2/2020 10:26:13 PM
ApiType                   : Sql
RestorableLocations       : {West US, East US}

Id                        : /subscriptions/{subscriptionId}/providers/Microsoft.DocumentDB/locations/eastus/restorableDatabaseAccounts/ff921125-e31c-4e8c-ae0a-20fe719baca6
DatabaseAccountInstanceId : ff921125-e31c-4e8c-ae0a-20fe719baca6
Location                  : East US
DatabaseAccountName       : deleted-account-2
CreationTime              : 8/2/2020 6:32:32 PM
DeletionTime              : 8/2/2020 6:34:48 PM
ApiType                   : Sql
RestorableLocations       : {Australia Southeast, East US, West US}

Id                        : /subscriptions/{subscriptionId}/providers/Microsoft.DocumentDB/locations/westus/restorableDatabaseAccounts/c7b27ad9-3bc0-4955-8cc2-a81790e5c3b3
DatabaseAccountInstanceId : c7b27ad9-3bc0-4955-8cc2-a81790e5c3b3
Location                  : West US
DatabaseAccountName       : live-account-1
CreationTime              : 8/2/2020 6:34:35 PM
DeletionTime              :
ApiType                   : MongoDB
RestorableLocations       : {West US}
```

Mencantumkan semua akun database yang dapat di memulihkan dalam langganan saat ini

### Contoh 1
```powershell
Get-AzCosmosDBRestorableDatabaseAccount -Location "West US" -DatabaseAccountInstanceId fb8f230e-bab0-452b-81cf-e32643ccc898
```

```output
Id                        : /subscriptions/{subscriptionId}/providers/Microsoft.DocumentDB/locations/westus/restorableDatabaseAccounts/fb8f230e-bab0-452b-81cf-e32643ccc898
DatabaseAccountInstanceId : fb8f230e-bab0-452b-81cf-e32643ccc898
Location                  : West US
DatabaseAccountName       : deleted-account-1
CreationTime              : 8/2/2020 10:23:00 PM
DeletionTime              : 8/2/2020 10:26:13 PM
ApiType                   : Sql
RestorableLocations       : {West US, East US}
```

Mendapatkan akun database yang dapat di memulihkan dengan DatabaseInstanceId yang diberikan di lokasi ARM yang diberikan  

## PARAMETERS

### -DatabaseAccountInstanceId
Id instans akun database CosmosDB.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DatabaseAccountName
Nama akun database Cosmos DB.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
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
Nama Lokasi dalam string.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
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

### Microsoft.Azure.Management.CosmosDB.Models.PSRestorableDatabaseAccountGetResult

## NOTES

## RELATED LINKS
