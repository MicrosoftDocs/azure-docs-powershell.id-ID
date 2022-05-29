---
external help file: Microsoft.Azure.PowerShell.Cmdlets.HDInsight.dll-Help.xml
Module Name: Az.HDInsight
ms.assetid: 5871C962-27D7-4EC8-927E-D4CAE5F23C58
online version: https://docs.microsoft.com/powershell/module/az.hdinsight/get-azhdinsightjoboutput
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/HDInsight/HDInsight/help/Get-AzHDInsightJobOutput.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/HDInsight/HDInsight/help/Get-AzHDInsightJobOutput.md
ms.openlocfilehash: 8a6324761ace4477aa2d808b0b2dd0ecd48103e6
ms.sourcegitcommit: 321c644cf2161807a71e1af318fc5c5311d22e25
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/25/2022
ms.locfileid: "145795670"
---
# Get-AzHDInsightJobOutput

## SYNOPSIS
Mendapatkan output log untuk pekerjaan dari akun penyimpanan yang terkait dengan kluster tertentu.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.hdinsight/get-azhdinsightjoboutput) untuk informasi terbaru.

## SYNTAX

```
Get-AzHDInsightJobOutput [-ClusterName] <String> [-JobId] <String> [[-DefaultContainer] <String>]
 [[-DefaultStorageAccountName] <String>] [[-DefaultStorageAccountKey] <String>]
 [-HttpCredential] <PSCredential> [-ResourceGroupName <String>] [-DisplayOutputType <JobDisplayOutputType>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzHDInsightJobOutput** mendapatkan output log untuk pekerjaan dari akun Storage yang terkait dengan kluster Azure HDInsight.

## EXAMPLES

### Contoh 1: Mendapatkan output log untuk pekerjaan
```powershell
# Cluster info
$clusterName = "your-hadoop-001"
$clusterCreds = Get-Credential

# Hive job details
$statusFolder = "<status folder>"
$query = "<query here>"

New-AzHDInsightHiveJobDefinition -StatusFolder $statusFolder `
            -Query $query `
        | Start-AzHDInsightJob `
            -ClusterName $clusterName `
            -ClusterCredential $clusterCreds `
        | Get-AzHDInsightJobOutput `
            -ClusterName $clusterName `
            -ClusterCredential $clusterCreds
```

Perintah ini mendapatkan output log dari kluster bernama your-hadoop-001.

## PARAMETERS

### -ClusterName
Menentukan nama kluster.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultContainer
Menentukan nama kontainer default.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -DefaultStorageAccountKey
Menentukan kunci akun Storage default.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultStorageAccountName
Menentukan nama akun Storage default.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisplayOutputType
Menentukan jenis output pekerjaan yang diminta.
Nilai yang dapat diterima untuk parameter ini adalah:
- StandardOutput
- StandardError

```yaml
Type: Microsoft.Azure.Commands.HDInsight.Models.Job.JobDisplayOutputType
Parameter Sets: (All)
Aliases:
Accepted values: StandardOutput, StandardError

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HttpCredential
Menentukan kredensial masuk kluster (HTTP) untuk kluster.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases: ClusterCredential

Required: True
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobId
Menentukan ID pekerjaan dari pekerjaan yang outputnya akan diambil.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Tidak ada

## OUTPUTS

### System.String

## NOTES

## RELATED LINKS

[New-AzHDInsightHiveJobDefinition](./New-AzHDInsightHiveJobDefinition.md)

[Start-AzHDInsightJob](./Start-AzHDInsightJob.md)


