---
external help file: Microsoft.Azure.PowerShell.Cmdlets.OperationalInsights.dll-Help.xml
Module Name: Az.OperationalInsights
online version: https://docs.microsoft.com/powershell/module/az.operationalinsights/update-azoperationalinsightscluster
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/OperationalInsights/OperationalInsights/help/Update-AzOperationalInsightsCluster.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/OperationalInsights/OperationalInsights/help/Update-AzOperationalInsightsCluster.md
ms.openlocfilehash: f1fad79dd45e3b9f86d0bca79360aae9e21ccd41
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136559157"
---
# Update-AzOperationalInsightsCluster

## SYNOPSIS
kluster pembaruan

## SYNTAX

### UpdateByNameParameterSet (Default)
```
Update-AzOperationalInsightsCluster -ResourceGroupName <String> -ClusterName <String> [-SkuName <String>]
 [-SkuCapacity <Int64>] [-KeyVaultUri <String>] [-KeyName <String>] [-KeyVersion <String>] [-Tag <Hashtable>]
 [-IdentityType <String>] [-BillingType <String>] [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### AllParameterSet
```
Update-AzOperationalInsightsCluster [-ResourceGroupName <String>] [-ClusterName <String>]
 [-ResourceId <String>] [-InputCluster <PSCluster>] [-SkuName <String>] [-SkuCapacity <Int64>]
 [-KeyVaultUri <String>] [-KeyName <String>] [-KeyVersion <String>] [-Tag <Hashtable>] [-IdentityType <String>]
 [-BillingType <String>] [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### UpdateByResourceIdParameterSet
```
Update-AzOperationalInsightsCluster -ResourceId <String> [-SkuName <String>] [-SkuCapacity <Int64>]
 [-KeyVaultUri <String>] [-KeyName <String>] [-KeyVersion <String>] [-Tag <Hashtable>] [-IdentityType <String>]
 [-BillingType <String>] [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### UpdateByInputObjectParameterSet
```
Update-AzOperationalInsightsCluster -InputCluster <PSCluster> [-SkuName <String>] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
kluster pembaruan

## EXAMPLES

### Contoh 1
```powershell
Update-AzOperationalInsightsCluster -ResourceGroupName azps-test-group -ClusterName yabo-cluster10 -Location eastus -SkuName CapacityReservation -SkuCapacity 1200 -KeyVaultUri {uri} -KeyName {key-name} -KeyVersion {version}

Identity                        : Microsoft.Azure.Commands.OperationalInsights.Models.PSIdentity
Sku                             : Microsoft.Azure.Commands.OperationalInsights.Models.PSClusterSku
ClusterId                       : {cluster-id}
ProvisioningState               : Succeeded
IsDoubleEncryptionEnabled       : True
IsAvailabilityZonesEnabled      : False
BillingType                     : Cluster
KeyVaultProperties              : Microsoft.Azure.Commands.OperationalInsights.Models.PSKeyVaultProperties
LastModifiedDate                : 
CreatedDate                     : 
AssociatedWorkspaces            : {workspaces}
CapacityReservationProperties   : Microsoft.Azure.Management.OperationalInsights.Models.CapacityReservationProperties
Location                        : South Central US
Id                              : /subscriptions/{subscription}/resourceGroups/{rg-name}/providers/Microsoft.OperationalInsights/clusters/{cluster-name}
Name                            : {cluster-name}
Type                            : Microsoft.OperationalInsights/clusters
Tags                            : {}
```

kluster pembaruan dengan properti dan sku kunci vault

## PARAMETERS

### -AsJob
Jalankan cmdlet di latar belakang

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

### -BillingType
Tipe tagihan dapat diatur sebagai 'Kluster' atau 'Ruang Kerja'

```yaml
Type: System.String
Parameter Sets: UpdateByNameParameterSet, AllParameterSet, UpdateByResourceIdParameterSet
Aliases:
Accepted values: Cluster, Workspaces

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClusterName
Nama kluster.

```yaml
Type: System.String
Parameter Sets: UpdateByNameParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: System.String
Parameter Sets: AllParameterSet
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

### -IdentityType
tipe identitas, nilai bisa menjadi 'SystemAssigned', 'Tidak ada'.

```yaml
Type: System.String
Parameter Sets: UpdateByNameParameterSet, AllParameterSet, UpdateByResourceIdParameterSet
Aliases:
Accepted values: SystemAssigned, None, UserAssigned

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputCluster
Menentukan kluster yang akan diperbarui.

```yaml
Type: Microsoft.Azure.Commands.OperationalInsights.Models.PSCluster
Parameter Sets: AllParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: Microsoft.Azure.Commands.OperationalInsights.Models.PSCluster
Parameter Sets: UpdateByInputObjectParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyName
Nama Kunci

```yaml
Type: System.String
Parameter Sets: UpdateByNameParameterSet, AllParameterSet, UpdateByResourceIdParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyVaultUri
Key Vault Uri, "Proteksi Pembersihan" dan "Penghapusan Sementara" harus diaktifkan untuk keyvault ini

```yaml
Type: System.String
Parameter Sets: UpdateByNameParameterSet, AllParameterSet, UpdateByResourceIdParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyVersion
Versi Utama

```yaml
Type: System.String
Parameter Sets: UpdateByNameParameterSet, AllParameterSet, UpdateByResourceIdParameterSet
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
Parameter Sets: UpdateByNameParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: System.String
Parameter Sets: AllParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
ID sumber daya tujuan.
Ini dapat disalin dari entri Properti dari sumber daya tujuan di Azure.

```yaml
Type: System.String
Parameter Sets: AllParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: System.String
Parameter Sets: UpdateByResourceIdParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkuCapacity
Kapasitas Sku

```yaml
Type: System.Int64
Parameter Sets: UpdateByNameParameterSet, AllParameterSet, UpdateByResourceIdParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkuName
Sku Nama, sekarang bisa menjadi 'CapacityReservation' saja

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: CapacityReservation

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tag
Tag kluster

```yaml
Type: System.Collections.Hashtable
Parameter Sets: UpdateByNameParameterSet, AllParameterSet, UpdateByResourceIdParameterSet
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
Default value: None
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Azure.Commands.OperationalInsights.Models.PSCluster

## OUTPUTS

### Microsoft.Azure.Commands.OperationalInsights.Models.PSCluster

## CATATAN

## RELATED LINKS
