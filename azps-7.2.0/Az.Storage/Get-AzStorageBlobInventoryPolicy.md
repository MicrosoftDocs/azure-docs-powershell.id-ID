---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Storage.Management.dll-Help.xml
Module Name: Az.Storage
online version: https://docs.microsoft.com/powershell/module/az.storage/get-azstorageblobinventorypolicy
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Get-AzStorageBlobInventoryPolicy.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Get-AzStorageBlobInventoryPolicy.md
ms.openlocfilehash: 1c483e3562fdef04cc19b872a4c80dae9a7d04fa
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138165548"
---
# Get-AzStorageBlobInventoryPolicy

## SYNOPSIS
Mendapatkan kebijakan inventaris blob dari Storage Anda.

## SYNTAX

### Nama Akun (Default)
```
Get-AzStorageBlobInventoryPolicy [-ResourceGroupName] <String> [-StorageAccountName] <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### AccountResourceId
```
Get-AzStorageBlobInventoryPolicy [-StorageAccountResourceId] <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### AccountObject
```
Get-AzStorageBlobInventoryPolicy -StorageAccount <PSStorageAccount> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzStorageBlobInventoryPolicy** mendapatkan kebijakan inventaris blob dari Storage anda.

## EXAMPLES

### Contoh 1: Mendapatkan kebijakan inventaris blob dari Storage saya
```
PS C:\> $policy = Get-AzStorageBlobInventoryPolicy -ResourceGroupName "myresourcegroup" -AccountName "mystorageaccount"

PS C:\> $policy 

StorageAccountName : mystorageaccount
ResourceGroupName  : myresourcegroup
Name               : DefaultInventoryPolicy
Id                 : /subscriptions/{subscription-Id}/resourceGroups/myresourcegroup/providers/Microsoft.Storage/storageAccounts/mystorageaccount/inventoryPolicies/default
Type               : Microsoft.Storage/storageAccounts/inventoryPolicies
LastModifiedTime   : 11/4/2020 9:18:30 AM
Enabled            : True
Rules              : {Test1, Test2}

PS C:\> $policy.Rules

Name  Enabled Destination   ObjectType Format  Schedule IncludeSnapshots IncludeBlobVersions BlobTypes               PrefixMatch SchemaFields                                           
----  ------- -----------   ---------- ------  -------- ---------------- ------------------- ---------               ----------- ------------                                           
Test1 False   containername Container  Csv     Daily                                                                 {aaa, bbb}  {Name, Metadata, PublicAccess, Last-Modified...}       
Test2 True    containername Blob       Parquet Weekly   True             True                {blockBlob, appendBlob} {ccc, ddd}  {Name, Creation-Time, Last-Modified, Content-Length...}
```

Perintah ini mendapatkan kebijakan inventaris blob dari Storage pengguna, dan memperlihatkan proeprtiesnya.

## PARAMETERS

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

### -ResourceGroupName
Nama Grup Sumber Daya.

```yaml
Type: System.String
Parameter Sets: AccountName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageAccount
Storage akun

```yaml
Type: Microsoft.Azure.Commands.Management.Storage.Models.PSStorageAccount
Parameter Sets: AccountObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -StorageAccountName
Storage Akun.

```yaml
Type: System.String
Parameter Sets: AccountName
Aliases: AccountName

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageAccountResourceId
Storage Sumber Daya Akun.

```yaml
Type: System.String
Parameter Sets: AccountResourceId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Azure.Commands.Management. Storage. Models.PSStorageAccount

## OUTPUTS

### Microsoft.Azure.Commands.Management. Storage. Models.PSBlobInventoryPolicy

## CATATAN

## RELATED LINKS
