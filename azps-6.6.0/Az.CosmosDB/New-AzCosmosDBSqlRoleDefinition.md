---
external help file: Microsoft.Azure.PowerShell.Cmdlets.CosmosDB.dll-Help.xml
Module Name: Az.CosmosDB
online version: https://docs.microsoft.com/powershell/module/az.cosmosdb/new-azcosmosdbsqlroledefinition
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/New-AzCosmosDBSqlRoleDefinition.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/New-AzCosmosDBSqlRoleDefinition.md
ms.openlocfilehash: dabbf1f2b4a6469f60c44ff7391de5b5604613b4
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143031473"
---
# New-AzCosmosDBSqlRoleDefinition

## SYNOPSIS
Membuat Definisi Peran CosmosDB Sql baru.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.cosmosdb/new-azcosmosdbsqlroledefinition) untuk informasi terbaru.

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
Lingkup yang Dapat Ditetapkan dapat sepenuhnya memenuhi syarat (yaitu. /subscriptions/subId/resourceGroups/resourceGroupName/providers/Microsoft.DocumentDB/databaseAccounts/accountName/dbName) atau dimulai dengan nama database (ie. /dbs/dbName).
Untuk menentukan Izin Definisi Peran, gunakan parameter DataAction dan lolos dalam daftar string yang akan diubah menjadi objek Izin tunggal, atau gunakan cmdlet New-AzCosmosDBPermission untuk membuat objek PSPermission untuk masuk melalui parameter Izin.

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

### -AccountName
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
Kumpulan jalur sumber daya di bawah tempat Penetapan Peran dapat dilampirkan ke Definisi Peran. Misalnya. '/', '/dbs/dbname','/dbs/dbname/colls/collname'.

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
Kumpulan tindakan data yang diberikan melalui Definisi Peran. Daftar tindakan yang diperbolehkan dapat ditemukan di: https://aka.ms/cosmos-native-rbac

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

### -Izin
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
Tipe Definisi Peran, baik CustomRole atau BuiltInRole.
Nilai defaultnya adalah CustomRole.

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
Meminta konfirmasi sebelum menjalankan cmdlet.

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
Cmdlet tidak dijalankan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.CosmosDB.Models.PSSqlRoleDefinitionGetResults
## OUTPUTS

### Microsoft.Azure.Commands.CosmosDB.Models.PSSqlRoleAssignmentGetResults
## NOTES

## RELATED LINKS
