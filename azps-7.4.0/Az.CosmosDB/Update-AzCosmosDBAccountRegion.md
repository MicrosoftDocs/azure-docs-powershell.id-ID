---
external help file: Microsoft.Azure.PowerShell.Cmdlets.CosmosDB.dll-Help.xml
Module Name: Az.CosmosDB
online version: https://docs.microsoft.com/powershell/module/az.cosmosdb/update-azcosmosdbaccountregion
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/Update-AzCosmosDBAccountRegion.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/CosmosDB/CosmosDB/help/Update-AzCosmosDBAccountRegion.md
ms.openlocfilehash: 6a29a70f445d591d937085c1944b5d85d1d6c673
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142003155"
---
# Update-AzCosmosDBAccountRegion

## SYNOPSIS
Perbarui Wilayah Akun CosmosDB.

## SYNTAX

### ByNameParameterSet (Default)
```
Update-AzCosmosDBAccountRegion -ResourceGroupName <String> -Name <String> [-Location <String[]>]
 [-LocationObject <PSLocation[]>] [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ByResourceIdParameterSet
```
Update-AzCosmosDBAccountRegion [-Location <String[]>] [-LocationObject <PSLocation[]>] -ResourceId <String>
 [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByObjectParameterSet
```
Update-AzCosmosDBAccountRegion [-Location <String[]>] [-LocationObject <PSLocation[]>]
 -InputObject <PSDatabaseAccountGetResults> [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Perbarui Wilayah Akun CosmosDB. Lokasi dapat disediakan baik sebagai objek tipe PSLocation atau sebagai string Nama Lokasi yang diurutkan berdasarkan prioritas failover.
Parameter LocationObject mengharapkan daftar lokasi saat ini (prioritas failover disertakan) ditambahkan oleh LocationObjects baru yang terkait dengan lokasi baru yang akan ditambahkan.
Parameter lokasi mengharapkan daftar lokasi saat ini(diurutkan oleh prioritas failover) dan lokasi baru. Harap diperhatikan, kami hanya mendukung Penambahan Kawasan. Harap sediakan Lokasi atau LocationObject.

## EXAMPLES

### Contoh 1
```powershell
Update-AzCosmosDBAccountRegion -ResourceGroupName rg -Name dbname -Location "location1", "location2"
```

```output
Id                            : /subscriptions/{subscriptionid}/resourceGroups/rg/providers/Microsoft.DocumentDB/databaseAccounts/dbname
Name                          : dbname
Location                      : location1
Tags                          : {}
EnableCassandraConnector      :
EnableMultipleWriteLocations  : True
VirtualNetworkRules           : {}
FailoverPolicies              : {dbname-location1, dbname-location2}
Locations                     : {dbname-location1, dbname-location2}
ReadLocations                 : {dbname-location1, dbname-location2}
WriteLocations                : {dbname-location1}
Capabilities                  : {}
ConsistencyPolicy             : Microsoft.Azure.Management.CosmosDB.Fluent.Models.ConsistencyPolicy
EnableAutomaticFailover       : False
IsVirtualNetworkFilterEnabled : False
IpRules                       : {}
DatabaseAccountOfferType      : Standard
DocumentEndpoint              : https://dbname.documents.azure.com:443/
ProvisioningState             : Succeeded
Kind                          : GlobalDocumentDB
```

## PARAMETERS

### -AsJob
Menjalankan cmdlet di latar belakang

```yaml
Type: System.Management.Automation.SwitchParameter
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

### -InputObject
ResourceId sumber daya.

```yaml
Type: Microsoft.Azure.Commands.CosmosDB.Models.PSDatabaseAccountGetResults
Parameter Sets: ByObjectParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Lokasi
Nama lokasi yang akan ditambahkan.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LocationObject
Tambahkan lokasi ke akun database Cosmos DB. Array objek PSLocation.

```yaml
Type: Microsoft.Azure.Commands.CosmosDB.Models.PSLocation[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
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

### -ResourceId
ResourceId sumber daya.

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
Default value: None
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.CosmosDB.Models.PSDatabaseAccount

## OUTPUTS

### Microsoft.Azure.Commands.CosmosDB.Models.PSDatabaseAccount

## CATATAN

## RELATED LINKS
