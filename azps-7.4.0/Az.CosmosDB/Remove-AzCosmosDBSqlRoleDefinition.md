---
external help file: Microsoft.Azure.PowerShell.Cmdlets.CosmosDB.dll-Help.xml
Module Name: Az.CosmosDB
online version: https://docs.microsoft.com/powershell/module/az.cosmosdb/remove-azcosmosdbsqlroledefinition
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/Remove-AzCosmosDBSqlRoleDefinition.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/Remove-AzCosmosDBSqlRoleDefinition.md
ms.openlocfilehash: 91c99931110d0c4ddb3f9e205e32a5aa7027f1cd
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141839296"
---
# Remove-AzCosmosDBSqlRoleDefinition

## SYNOPSIS
Menghapus Definisi Peran CosmosDB Sql.

## SYNTAX

### ByResourceIdParameterSet (Default)
```
Remove-AzCosmosDBSqlRoleDefinition -ResourceGroupName <String> -AccountName <String> -Id <String> [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByParentObjectParameterSet
```
Remove-AzCosmosDBSqlRoleDefinition -Id <String> -ParentObject <PSDatabaseAccountGetResults> [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByObjectParameterSet
```
Remove-AzCosmosDBSqlRoleDefinition -InputObject <PSSqlRoleDefinitionGetResults> [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet Remove-AzCosmosDBSqlRoleDefinition menghapus Definisi Peran CosmosDB Sql yang terkait dengan ResourceGroupName, AccountName, dan Id. Id dapat sepenuhnya memenuhi syarat atau hanya Guid.

## EXAMPLES

### Contoh 1
```powershell
Remove-AzCosmosDBSqlRoleDefinition -ResourceGroupName resourceGroupName -AccountName accountName -Id id -PassThru
```

```output
true
```

## PARAMETERS

### -AccountName
Nama akun database Cosmos DB.

```yaml
Type: System.String
Parameter Sets: ByResourceIdParameterSet
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
Id Definisi Peran.

```yaml
Type: System.String
Parameter Sets: ByResourceIdParameterSet, ByParentObjectParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Objek definisi peran.

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

### -PassThru
Untuk diatur ke true jika pengguna ingin menerima output.
Output adalah true jika operasi berhasil dan kesalahan dilemparkan jika tidak.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: ByResourceIdParameterSet
Aliases:

Required: True
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

### System.Void
## CATATAN

## RELATED LINKS
