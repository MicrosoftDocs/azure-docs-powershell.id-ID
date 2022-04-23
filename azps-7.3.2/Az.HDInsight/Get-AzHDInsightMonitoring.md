---
external help file: Microsoft.Azure.PowerShell.Cmdlets.HDInsight.dll-Help.xml
Module Name: Az.HDInsight
online version: https://docs.microsoft.com/powershell/module/az.hdinsight/get-azhdinsightmonitoring
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/HDInsight/HDInsight/help/Get-AzHDInsightMonitoring.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/HDInsight/HDInsight/help/Get-AzHDInsightMonitoring.md
ms.openlocfilehash: b3ba78255bd013fb4548ea4fbf36dd9b0a375830
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143336537"
---
# Get-AzHDInsightMonitoring

## SYNOPSIS
Mendapatkan status integrasi log Azure Monitor Klasik di kluster HDInsight.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.hdinsight/get-azhdinsightmonitoring) untuk informasi terbaru.

## SYNTAX

```
Get-AzHDInsightMonitoring [-Name] <String> [-ResourceGroupName <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzHDInsightMonitoring** mendapatkan status integrasi log Azure Monitor Klasik pada kluster HDInsight. Jika pemantauan diaktifkan, maka juga akan mengembalikan id ruang kerja analitik log.

## EXAMPLES

### Contoh 1
```
PS C:\> Get-AzHDInsightMonitoring -Name testcluster

{'ClusterMonitoringEnabled':'true', 'workspaceId':'1d364e89-bb71-4503-aa3d-a23535aea7bd'}
```

Pemantauan diaktifkan pada kluster karena properti ClusterMonitoringEnabled adalah true. Id ruang kerja pemantauan tempat log mengalir adalah 1d364e89-bb71-4503-aa3d-a23535aea7bd

### Contoh 2
```
PS C:\> Get-AzHDInsightMonitoring -Name testcluster -ResourceGroupName testrg

{'ClusterMonitoringEnabled':'true', 'workspaceId':'1d364e89-bb71-4503-aa3d-a23535aea7bd'}
```

Pemantauan diaktifkan pada kluster karena properti ClusterMonitoringEnabled adalah true. Id ruang kerja pemantauan tempat log mengalir adalah 1d364e89-bb71-4503-aa3d-a23535aea7bd

### Contoh 3
```
PS C:\> Get-AzHDInsightMonitoring -Name testcluster

{'ClusterMonitoringEnabled':'false', 'workspaceId': null}
```

Pemantauan dinonaktifkan pada kluster karena properti ClusterMonitoringEnabled false.

### Contoh 4
```
PS C:\> Get-AzHDInsightMonitoring -Name testcluster -ResourceGroupName testrg

{'ClusterMonitoringEnabled':'false', 'workspaceId': null}
```

Pemantauan dinonaktifkan pada kluster karena properti ClusterMonitoringEnabled false.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

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

### -Nama
Nama kluster untuk mendapatkan status pemantauan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ClusterName

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Grup sumber daya kluster.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.HDInsight.Models.Management.AzureHDInsightMonitoring

## NOTES

## RELATED LINKS
