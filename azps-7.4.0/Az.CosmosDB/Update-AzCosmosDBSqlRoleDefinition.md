---
external help file: Microsoft.Azure.PowerShell.Cmdlets.CosmosDB.dll-Help.xml
Module Name: Az.CosmosDB
online version: https://docs.microsoft.com/powershell/module/az.cosmosdb/update-azcosmosdbsqlroledefinition
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/Update-AzCosmosDBSqlRoleDefinition.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/Update-AzCosmosDBSqlRoleDefinition.md
ms.openlocfilehash: c1f9e76114048724a8528cd57d5392b6b23cc80e
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144646816"
---
# Update-AzCosmosDBSqlRoleDefinition

## SYNOPSIS
Memperbarui Definisi Peran CosmosDB Sql yang ada.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.cosmosdb/update-azcosmosdbsqlroledefinition) untuk informasi terbaru.

## SYNTAX

### ByFieldsParameterSet (Default)
```
Update-AzCosmosDBSqlRoleDefinition -ResourceGroupName <String> -AccountName <String> -Id <String>
 [-Type <String>] [-RoleName <String>] [-DataAction <System.Collections.Generic.List`1[System.String]>]
 [-Permission <System.Collections.Generic.List`1[Microsoft.Azure.Commands.CosmosDB.Models.PSPermission]>]
 [-AssignableScope <System.Collections.Generic.List`1[System.String]>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByParentObjectParameterSet
```
Update-AzCosmosDBSqlRoleDefinition -Id <String> [-Type <String>] [-RoleName <String>]
 [-DataAction <System.Collections.Generic.List`1[System.String]>]
 [-Permission <System.Collections.Generic.List`1[Microsoft.Azure.Commands.CosmosDB.Models.PSPermission]>]
 [-AssignableScope <System.Collections.Generic.List`1[System.String]>]
 -ParentObject <PSDatabaseAccountGetResults> [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ByObjectParameterSet
```
Update-AzCosmosDBSqlRoleDefinition -InputObject <PSSqlRoleDefinitionGetResults>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Memperbarui Definisi Peran CosmosDB Sql yang ada.
Cakupan yang Dapat Ditetapkan dapat sepenuhnya memenuhi syarat (yaitu /subscriptions/subId/resourceGroups/resourceGroupName/providers/Microsoft.DocumentDB/databaseAccounts/accountName/dbs/dbName) atau dimulai dengan nama database (yaitu. /dbs/dbName).
Id dapat sepenuhnya memenuhi syarat atau hanya Guid.
Untuk menentukan Izin Definisi Peran, gunakan parameter DataAction dan teruskan daftar string yang akan diubah menjadi objek Izin tunggal, atau gunakan cmdlet New-AzCosmosDBPermission untuk membuat objek PSPermission untuk melewati parameter Izin.

## EXAMPLES

### Contoh 1
```powershell
Update-AzCosmosDBSqlRoleDefinition
    -AccountName accountName 
    -ResourceGroupName resourceGroupName 
    -Id id
    -Type CustomRole
    -RoleName roleName
    -DataAction "Microsoft.DocumentDB/databaseAccounts/sqlDatabases/containers/items/create"
    -AssignableScope "/"
```

```output
RoleName         : roleName
Id               : /subscriptions/subId/resourceGroups/resourceGroupName/providers/Microsoft.DocumentDB/databaseAccounts/accountName/sqlRoleDefinitions/id
Type             : CustomRole
Permissions      : {Microsoft.Azure.Management.CosmosDB.Models.Permission}
AssignableScopes : {/subscriptions/subId/resourceGroups/resourceGroupName/providers/Microsoft.DocumentDB/databaseAccounts/accountName}
```

### Contoh 2: Menggunakan Izin dan ParentObject
```powershell
$DatabaseAccount = Get-AzCosmosDBAccount -Name accountName -ResourceGroupName resourceGroupName
$Permission = New-AzCosmosDBPermission -DataAction "Microsoft.DocumentDB/databaseAccounts/sqlDatabases/containers/items/create"
Update-AzCosmosDBSqlRoleDefinition
    -Type CustomRole
    -Id id
    -RoleName roleName
    -Permission $Permission
    -AssignableScope "/"
    -ParentObject $DatabaseAccount
```

```output
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
Parameter Sets: ByFieldsParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AssignableScope
Kumpulan jalur sumber daya di bawah tempat Penetapan Peran dapat dilampirkan ke Definisi Peran. Mis. '/', '/dbs/dbname','/dbs/dbname/colls/collname'.

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: ByFieldsParameterSet, ByParentObjectParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DataAction
Kumpulan tindakan data yang diberikan melalui Definisi Peran. Daftar tindakan yang diizinkan dapat ditemukan di: https://aka.ms/cosmos-native-rbac

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: ByFieldsParameterSet, ByParentObjectParameterSet
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

### -Id
Id Definisi Peran.

```yaml
Type: System.String
Parameter Sets: ByFieldsParameterSet, ByParentObjectParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Objek Akun CosmosDB

```yaml
Type: Microsoft.Azure.Commands.CosmosDB.Models.PSSqlRoleDefinitionGetResults
Parameter Sets: ByObjectParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ParentObject
Objek Akun CosmosDB

```yaml
Type: Microsoft.Azure.Commands.CosmosDB.Models.PSDatabaseAccountGetResults
Parameter Sets: ByParentObjectParameterSet
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
Parameter Sets: ByFieldsParameterSet, ByParentObjectParameterSet
Aliases:

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
Parameter Sets: ByFieldsParameterSet
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
Parameter Sets: ByFieldsParameterSet, ByParentObjectParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Type
Jenis Definisi Peran, baik CustomRole atau BuiltInRole.
Nilai defaultnya adalah CustomRole.

```yaml
Type: System.String
Parameter Sets: ByFieldsParameterSet, ByParentObjectParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

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
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.Commands.CosmosDB.Models.PSDatabaseAccount
## OUTPUTS

### Microsoft.Azure.Commands.CosmosDB.Models.PSThroughputSettingsGetResults
## NOTES

## RELATED LINKS
