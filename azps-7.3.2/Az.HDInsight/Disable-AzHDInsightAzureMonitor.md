---
external help file: Microsoft.Azure.PowerShell.Cmdlets.HDInsight.dll-Help.xml
Module Name: Az.HDInsight
online version: https://docs.microsoft.com/powershell/module/az.hdinsight/disable-azhdinsightazuremonitor
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/HDInsight/HDInsight/help/Disable-AzHDInsightAzureMonitor.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/HDInsight/HDInsight/help/Disable-AzHDInsightAzureMonitor.md
ms.openlocfilehash: a202bd4ec87c023da5283a502ae113c1cfd1a8fa
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140571377"
---
# Disable-AzHDInsightAzureMonitor

## SYNOPSIS
Menonaktifkan Azure Monitor dalam kluster HDInsight yang ditentukan.

## SYNTAX

### DisableByNameParameterSet (Default)
```
Disable-AzHDInsightAzureMonitor [[-ResourceGroupName] <String>] [-ClusterName] <String>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### DisableByResourceIdParameterSet
```
Disable-AzHDInsightAzureMonitor [-ResourceId] <String> [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### DisableByInputObjectParameterSet
```
Disable-AzHDInsightAzureMonitor [-InputObject] <AzureHDInsightCluster>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Disable-AzHDInsightAzureMonitor** menonaktifkan Azure Monitor dalam kluster HDInsight tertentu.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> # Cluster info
PS C:\> $clusterName = "your-hadoop-001"
PS C:\> $resourceGroupName = "Group"
PS C:\> Disable-AzHDInsightAzureMonitor -ClusterName $clusterName -ResourceGroup $resourceGroupName
```

Cmdlet ini menonaktifkan monitor Azure dalam kluster HDInsight yang ditentukan.

### Contoh 2
```powershell
PS C:\> # Cluster info
PS C:\> $clusterName = "your-hadoop-001"
PS C:\> $cluster=Get-AzHDInsightCluster -ClusterName $clusterName
PS C:\> $cluster | Disable-AzHDInsightAzureMonitor
```

Cmdlet ini menonaktifkan monitor Azure dalam kluster HDInsight tertentu dengan pipeline.

## PARAMETERS

### -ClusterName
Mendapatkan atau mengatur nama kluster.

```yaml
Type: System.String
Parameter Sets: DisableByNameParameterSet
Aliases:

Required: True
Position: 1
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
Mendapatkan atau mengatur objek input.

```yaml
Type: Microsoft.Azure.Commands.HDInsight.Models.AzureHDInsightCluster
Parameter Sets: DisableByInputObjectParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ResourceGroupName
Mendapatkan atau mengatur nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: DisableByNameParameterSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
Mendapatkan atau mengatur id sumber daya.

```yaml
Type: System.String
Parameter Sets: DisableByResourceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Azure.Commands.HDInsight.Models.AzureHDInsightCluster

## OUTPUTS

### System.Boolean

## CATATAN

## RELATED LINKS

[Enable-AzHDInsightAzureMonitor](./Enable-AzHDInsightAzureMonitor.md)
 [Get-AzHDInsightAzureMonitor](./Get-AzHDInsightAzureMonitor.md)
