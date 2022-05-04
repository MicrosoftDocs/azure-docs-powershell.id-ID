---
external help file: Microsoft.Azure.PowerShell.Cmdlets.HDInsight.dll-Help.xml
Module Name: Az.HDInsight
ms.assetid: 86276DF3-95E2-405F-BA46-F188B7AE3B9B
online version: https://docs.microsoft.com/powershell/module/az.hdinsight/new-azhdinsightclusterautoscaleschedulecondition
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/HDInsight/HDInsight/help/New-AzHDInsightClusterAutoscaleScheduleCondition.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/HDInsight/HDInsight/help/New-AzHDInsightClusterAutoscaleScheduleCondition.md
ms.openlocfilehash: ec78f705f04ebbf12a62d161087bf0c5bf704f81
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144664630"
---
# New-AzHDInsightClusterAutoscaleScheduleCondition

## SYNOPSIS
Membuat kondisi skala otomatis berbasis Jadwal.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.hdinsight/new-azhdinsightclusterautoscaleschedulecondition) untuk informasi terbaru.

## SYNTAX

```
New-AzHDInsightClusterAutoscaleScheduleCondition -Time <DateTime> -WorkerNodeCount <Int32>
 -Day <AzureHDInsightDaysOfWeek[]> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzHDInsightClusterAutoscaleScheduleCondition** membuat kondisi skala otomatis berbasis Jadwal.

## EXAMPLES

### Contoh 1
```powershell
New-AzHDInsightClusterAutoscaleScheduleCondition -Time 09:00 -WorkerNodeCount 5 -Day Monday,Wednesday
```

Perintah ini membuat kondisi di mana skala otomatis kluster menjadi 5 simpul pekerja pada pukul 09:00 setiap hari Senin, Rabu.

### Contoh 2: Aktifkan skala otomatis berbasis jadwal kluster dengan kondisi skala otomatis.
```powershell
# create a autoscale condition
$condition=New-AzHDInsightClusterAutoscaleScheduleCondition -Time 09:00 -WorkerNodeCount 5 -Day Monday,Wednesday

# Set the cluster autoscale configuration
$clusterResourceGroup="group"
$clusterName="MyCluster"
Set-AzHDInsightClusterAutoscaleConfiguration -ResourceGroupName $clusterResourceGroup -ClusterName $clusterName -Schedule -TimeZone "Pacific Standard Time" -Condition $condition
```

Perintah ini membuat kondisi di mana skala otomatis kluster menjadi 5 simpul pekerja pada pukul 09:00 setiap hari Senin, Rabu.

## PARAMETERS

### -Hari
Mendapatkan atau mengatur hari kondisi jadwal Autoscale.

```yaml
Type: Microsoft.Azure.Commands.HDInsight.Models.AzureHDInsightDaysOfWeek[]
Parameter Sets: (All)
Aliases:
Accepted values: Monday, Tuesday, Wednesday, Thursday, Friday, Saturday, Sunday

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

### -Waktu
Mendapatkan atau mengatur waktu kondisi jadwal Autoscale.

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WorkerNodeCount
Mendapatkan atau mengatur jumlah simpul pekerja jadwal kondisi jadwal Autoscale.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.HDInsight.Models.AzureHDInsightAutoscaleCondition

## NOTES

## RELATED LINKS

[New-AzHDInsightClusterAutoscaleConfiguration](./New-AzHDInsightClusterAutoscaleConfiguration.md)
 [Set-AzHDInsightClusterAutoscaleConfiguration](./Set-AzHDInsightClusterAutoscaleConfiguration.md)
