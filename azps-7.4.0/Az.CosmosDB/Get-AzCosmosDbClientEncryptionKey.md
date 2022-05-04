---
external help file: Microsoft.Azure.PowerShell.Cmdlets.CosmosDB.dll-Help.xml
Module Name: Az.CosmosDB
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/Get-AzCosmosDbClientEncryptionKey.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/Get-AzCosmosDbClientEncryptionKey.md
ms.openlocfilehash: 2b85064137afac87b499a419ec135e508b642c73
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144594736"
---
# Get-AzCosmosDbClientEncryptionKey

## SYNOPSIS
Mendapatkan Kunci Enkripsi Klien CosmosDB.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.cosmosdb/get-azcosmosdbclientencryptionkey) untuk informasi terbaru.

## SYNTAX

### ByNameParameterSet (Default)
```
Get-AzCosmosDbClientEncryptionKey -ResourceGroupName <String> [-Name <String>]
 [-DefaultProfile <IAzureContextContainer>] -AccountName <String> -DatabaseName <String> [<CommonParameters>]
```

### ByParentObjectParameterSet
```
Get-AzCosmosDbClientEncryptionKey [-Name <String>] -SqlDatabaseObject <PSSqlDatabaseGetResults>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzCosmosDbClientEncryptionKey** mendapatkan daftar semua Kunci Enkripsi Klien CosmosDB yang ada untuk ResourceGroupName, AccountName, dan DatabaseName tertentu dan mendapatkan satu Kunci Enkripsi Klien CosmosDB untuk ResourceGroupName, AccountName, DatabaseName, dan ClientEncryptionKeyName tertentu.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Get-AzCosmosDbClientEncryptionKey -AccountName myAccountName -DatabaseName myDatabaseName -ResourceGroupName myRgName

Name                     : {clientEncryptionKeyName}
Id                       : Id
Resource                 : Microsoft.Azure.Commands.CosmosDB.Models.PSSqlClientEncryptionKeyGetPropertiesResource
```

Perintah mendapatkan semua kunci enkripsi klien dalam database sebagaimana diatur dalam myRgName.

## PARAMETERS

### -AccountName
Nama akun database Cosmos DB.

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

### -DatabaseName
Nama database.

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

### -Name
Nama Kunci Enkripsi Klien.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ClientEncryptionKeyName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

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

### -SqlDatabaseObject
Objek Sql Database.

```yaml
Type: Microsoft.Azure.Commands.CosmosDB.Models.PSSqlDatabaseGetResults
Parameter Sets: ByParentObjectParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.Commands.CosmosDB.Models.PSSqlDatabaseGetResults

## OUTPUTS

### Microsoft.Azure.Commands.CosmosDB.Models.PSSqlClientEncryptionKeyGetResults

## NOTES

## RELATED LINKS

[New-AzCosmosDbClientEncryptionKey](./New-AzCosmosDbClientEncryptionKey.md)

[Update-AzCosmosDbClientEncryptionKey](./Update-AzCosmosDbClientEncryptionKey.md)
