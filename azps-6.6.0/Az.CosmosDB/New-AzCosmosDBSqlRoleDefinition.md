---
external help file: Microsoft.Azure.PowerShell.Cmdlets.CosmosDB.dll-Help.xml
Module Name: Az.CosmosDB
online version: https://docs.microsoft.com/powershell/module/az.cosmosdb/new-azcosmosdbsqlroledefinition
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/New-AzCosmosDBSqlRoleDefinition.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/New-AzCosmosDBSqlRoleDefinition.md
ms.openlocfilehash: f27e3c47df99280994eb101cd827cdbbd4614948
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136353453"
---
# New-AzCosmosDBSqlRoleDefinition

## SYNOPSIS
Membuat Definisi Peran CosmosDB Sql baru.

## SYNTAX

### ByFieldsDataActionsParameterSet (Default)
```
New-AzCosmosDBSqlRoleDefinition -ResourceGroupName <String> -AccountName <String> [-Id <String>]
 -RoleName <String> [-Type <String>] -AssignableScope <System.Collections.Generic.List`1[System.String]>
 -DataAction <System.Collections.Generic.List`1[System.String]> [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByFieldsPermissionsParameterSet
```
New-AzCosmosDBSqlRoleDefinition -ResourceGroupName <String> -AccountName <String> [-Id <String>]
 -RoleName <String> [-Type <String>] -AssignableScope <System.Collections.Generic.List`1[System.String]>
 -Permission <System.Collections.Generic.List`1[Microsoft.Azure.Commands.CosmosDB.Models.PSPermission]>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByParentObjectDataActionsParameterSet
```
New-AzCosmosDBSqlRoleDefinition [-Id <String>] -RoleName <String> [-Type <String>]
 -AssignableScope <System.Collections.Generic.List`1[System.String]>
 -DataAction <System.Collections.Generic.List`1[System.String]> -ParentObject <PSDatabaseAccountGetResults>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByParentObjectPermissionsParameterSet
```
New-AzCosmosDBSqlRoleDefinition [-Id <String>] -RoleName <String> [-Type <String>]
 -AssignableScope <System.Collections.Generic.List`1[System.String]>
 -Permission <System.Collections.Generic.List`1[Microsoft.Azure.Commands.CosmosDB.Models.PSPermission]>
 -ParentObject <PSDatabaseAccountGetResults> [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Membuat Definisi Peran CosmosDB Sql baru.
Lingkup yang Dapat Ditetapkan bisa sepenuhnya memenuhi syarat (yaitu /subscriptions/subId/resourceGroups/resourceGroupName/providers/Microsoft.DocumentDB/databaseAccounts/accountName/dbs/dbName) atau mulai dengan nama database (yaitu. /dbs/dbName).
Untuk menentukan Izin Definisi Peran, gunakan parameter DataAction dan pass dalam daftar string yang akan diubah menjadi objek Izin tunggal, atau gunakan cmdlet New-AzCosmosDBPermission untuk membuat objek PSPermission yang melewati parameter Izin.

## EXAMPLES

### Contoh 1: Menggunakan DataAction
```
PS C:\> New-AzCosmosDBSqlRoleDefinition
    -AccountName accountName 
    -ResourceGroupName resourceGroupName 
    -Type CustomRole
    -RoleName roleName
    -DataAction "Microsoft.DocumentDB/databaseAccounts/sqlDatabases/containers/items/create"
    -AssignableScope "/"

RoleName         : roleName
Id               : /subscriptions/subId/resourceGroups/resourceGroupName/providers/Microsoft.DocumentDB/databaseAccounts/accountName/sqlRoleDefinitions/id
Type             : CustomRole
Permissions      : {Microsoft.Azure.Management.CosmosDB.Models.Permission}
AssignableScopes : {/subscriptions/subId/resourceGroups/resourceGroupName/providers/Microsoft.DocumentDB/databaseAccounts/accountName}
```

### Contoh 2: Menggunakan Izin dan ParentObject
```
PS C:\> $DatabaseAccount = Get-AzCosmosDBAccount -Name accountName -ResourceGroupName resourceGroupName
PS C:\> $Permission = New-AzCosmosDBPermission -DataAction "Microsoft.DocumentDB/databaseAccounts/sqlDatabases/containers/items/create"
PS C:\> New-AzCosmosDBSqlRoleDefinition
    -Type CustomRole
    -RoleName roleName
    -Permission $Permission
    -AssignableScope "/"
    -ParentObject $DatabaseAccount

RoleName         : roleName
Id               : /subscriptions/subId/resourceGroups/resourceGroupName/providers/Microsoft.DocumentDB/databaseAccounts/accountName/sqlRoleDefinitions/id
Type             : CustomRole
Permissions      : {Microsoft.Azure.Management.CosmosDB.Models.Permission}
AssignableScopes : {/subscriptions/subId/resourceGroups/resourceGroupName/providers/Microsoft.DocumentDB/databaseAccounts/accountName}
```

## PARAMETERS

### -Nama Akun
Nama akun database Cosmos DB.

```yaml
Type: System.String
Parameter Sets: ByFieldsDataActionsParameterSet, ByFieldsPermissionsParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AssignableScope
Kumpulan jalur sumber daya di bawah penetapan peran yang dapat dilampirkan ke Definisi Peran. Contohnya '/', '/dbs/dbname','/dbs/dbname/colls/collname'.

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DataAction
Kumpulan tindakan data yang diberikan melalui Definisi Peran. Daftar tindakan yang diperbolehkan bisa ditemukan di: https://aka.ms/cosmos-native-rbac

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: ByFieldsDataActionsParameterSet, ByParentObjectDataActionsParameterSet
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

### -Id
Id Penetapan Peran.

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

### -ParentObject
Objek definisi peran.

```yaml
Type: Microsoft.Azure.Commands.CosmosDB.Models.PSDatabaseAccountGetResults
Parameter Sets: ByParentObjectDataActionsParameterSet, ByParentObjectPermissionsParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Permission
Izin adalah kumpulan tindakan data.

```yaml
Type: System.Collections.Generic.List`1[Microsoft.Azure.Commands.CosmosDB.Models.PSPermission]
Parameter Sets: ByFieldsPermissionsParameterSet, ByParentObjectPermissionsParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: ByFieldsDataActionsParameterSet, ByFieldsPermissionsParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RoleName
Nama Definisi Peran.

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

### -Tipe
Tipe Definisi Peran, baik Peran CustomRole atau BuiltInRole.
Nilai default adalah CustomRole.

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

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak berjalan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.CosmosDB.Models.PSSqlRoleDefinitionGetResults
## OUTPUTS

### Microsoft.Azure.Commands.CosmosDB.Models.PSSqlRoleAssignmentGetResults
## CATATAN

## RELATED LINKS
