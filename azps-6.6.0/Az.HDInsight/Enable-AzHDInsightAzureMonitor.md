---
external help file: Microsoft.Azure.PowerShell.Cmdlets.HDInsight.dll-Help.xml
Module Name: Az.HDInsight
online version: https://docs.microsoft.com/powershell/module/az.hdinsight/enable-azhdinsightazuremonitor
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/HDInsight/HDInsight/help/Enable-AzHDInsightAzureMonitor.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/HDInsight/HDInsight/help/Enable-AzHDInsightAzureMonitor.md
ms.openlocfilehash: 3473b980b582a98124fbf4b35953609b87bd310e
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142966205"
---
# Enable-AzHDInsightAzureMonitor

## SYNOPSIS
Mengaktifkan Azure Monitor dalam kluster HDInsight tertentu.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.hdinsight/enable-azhdinsightazuremonitor) untuk informasi terbaru.

## SYNTAX

### EnableByNameParameterSet (Default)
```
Enable-AzHDInsightAzureMonitor [[-ResourceGroupName] <String>] [-ClusterName] <String> [-WorkspaceId] <String>
 [-PrimaryKey] <String> [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### EnableByResourceIdParameterSet
```
Enable-AzHDInsightAzureMonitor [-ResourceId] <String> [-WorkspaceId] <String> [-PrimaryKey] <String>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### EnableByInputObjectParameterSet
```
Enable-AzHDInsightAzureMonitor [-InputObject] <AzureHDInsightCluster> [-WorkspaceId] <String>
 [-PrimaryKey] <String> [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Enable-AzHDInsightAzureMonitor** ini memungkinkan Azure Monitor dalam kluster HDInsight tertentu.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> # Cluster info
PS C:\> $clusterName = "your-hadoop-001"
PS C:\> $resourceGroupName = "Group"
PS C:\> $workspaceId = "your-workspace-id"
PS C:\> $primaryKey = "your-primary-key"
PS C:\> Enable-AzHDInsightAzureMonitor -ClusterName $clusterName -ResourceGroup $resourceGroupName -WorkspaceId $workspaceId -PrimaryKey $primaryKey
```

Cmdlet ini memungkinkan monitor azure dalam kluster HDInsight tertentu.

### Contoh 2
```powershell
PS C:\> # Cluster info
PS C:\> $clusterName = "your-hadoop-001"
PS C:\> $cluster=Get-AzHDInsightCluster -ClusterName $clusterName
PS C:\> $workspaceId = "your-workspace-id"
PS C:\> $primaryKey = "your-primary-key"
PS C:\> $cluster | Enable-AzHDInsightAzureMonitor -WorkspaceId $workspaceId -PrimaryKey $primaryKey
```

Cmdlet ini memungkinkan monitor azure dalam kluster HDInsight tertentu dengan pipeline.

## PARAMETERS

### -ClusterName
Mendapatkan atau mengatur nama kluster.

```yaml
Type: System.String
Parameter Sets: EnableByNameParameterSet
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
Parameter Sets: EnableByInputObjectParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PrimaryKey
Mengatur kunci utama ruang kerja Analitik Log.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Mendapatkan atau mengatur nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: EnableByNameParameterSet
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
Parameter Sets: EnableByResourceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WorkspaceId
Mendapatkan atau mengatur ID ruang kerja Analitik Log.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
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

### System.String

### Microsoft.Azure.Commands.HDInsight.Models.AzureHDInsightCluster

## OUTPUTS

### System.Boolean

## NOTES

## RELATED LINKS

[Disable-AzHDInsightAzureMonitor](./Disable-AzHDInsightAzureMonitor.md)
 [Get-AzHDInsightAzureMonitor](./Get-AzHDInsightAzureMonitor.md)
