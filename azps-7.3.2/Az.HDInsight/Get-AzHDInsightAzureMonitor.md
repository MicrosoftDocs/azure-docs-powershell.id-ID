---
external help file: Microsoft.Azure.PowerShell.Cmdlets.HDInsight.dll-Help.xml
Module Name: Az.HDInsight
online version: https://docs.microsoft.com/powershell/module/az.hdinsight/get-azhdinsightazuremonitor
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/HDInsight/HDInsight/help/Get-AzHDInsightAzureMonitor.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/HDInsight/HDInsight/help/Get-AzHDInsightAzureMonitor.md
ms.openlocfilehash: a4339410af14dacbdfe1bc973ddab186822f5966
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143336573"
---
# Get-AzHDInsightAzureMonitor

## SYNOPSIS
Mendapatkan status azure monitor dari kluster HDInsight tertentu.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.hdinsight/get-azhdinsightazuremonitor) untuk informasi terbaru.

## SYNTAX

### GetByNameParameterSet (Default)
```
Get-AzHDInsightAzureMonitor [[-ResourceGroupName] <String>] [-ClusterName] <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### GetByResourceIdParameterSet
```
Get-AzHDInsightAzureMonitor [-ResourceId] <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### GetByInputObjectParameterSet
```
Get-AzHDInsightAzureMonitor [-InputObject] <AzureHDInsightCluster> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzHDInsightAzureMonitor** mendapatkan status azure monitor dari kluster HDInsight yang ditentukan.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> # Cluster info
PS C:\> $clusterName = "your-hadoop-001"
PS C:\> $resourceGroupName = "Group"
PS C:\> Get-AzHDInsightAzureMonitor -ClusterName $clusterName -ResourceGroup $resourceGroupName
```

Cmdlet ini mendapatkan status azure monitor dari kluster HDInsight yang ditentukan.

### Contoh 2
```powershell
PS C:\> # Cluster info
PS C:\> $clusterName = "your-hadoop-001"
PS C:\> $cluster=Get-AzHDInsightCluster -ClusterName $clusterName
PS C:\> $cluster | Get-AzHDInsightAzureMonitor
```

Cmdlet ini mendapatkan azure monitor dengan pipeline.

## PARAMETERS

### -ClusterName
Mendapatkan atau mengatur nama kluster.

```yaml
Type: System.String
Parameter Sets: GetByNameParameterSet
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
Parameter Sets: GetByInputObjectParameterSet
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
Parameter Sets: GetByNameParameterSet
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
Parameter Sets: GetByResourceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Azure.Commands.HDInsight.Models.AzureHDInsightCluster

## OUTPUTS

### Microsoft.Azure.Commands.HDInsight.Models.Management.AzureHDInsightMonitoring

## NOTES

## RELATED LINKS

[Enable-AzHDInsightAzureMonitor](./Enable-AzHDInsightAzureMonitor.md)
 [Disable-AzHDInsightAzureMonitor](./Disable-AzHDInsightAzureMonitor.md)
