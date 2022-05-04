---
external help file: Microsoft.Azure.PowerShell.Cmdlets.HDInsight.dll-Help.xml
Module Name: Az.HDInsight
online version: https://docs.microsoft.com/powershell/module/az.hdinsight/set-azhdinsightgatewaycredential
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/HDInsight/HDInsight/help/Set-AzHDInsightGatewayCredential.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/HDInsight/HDInsight/help/Set-AzHDInsightGatewayCredential.md
ms.openlocfilehash: 74a93d3f13c7cd8efe0e673e2ec66e5710b5edc8
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144656246"
---
# Set-AzHDInsightGatewayCredential

## SYNOPSIS
Mengatur kredensial HTTP gateway dari kluster Azure HDInsight.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.hdinsight/set-azhdinsightgatewaycredential) untuk informasi terbaru.

## SYNTAX

### SetByNameParameterSet (Default)
```
Set-AzHDInsightGatewayCredential [-Name] <String> [-HttpCredential] <PSCredential>
 [-ResourceGroupName <String>] [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### SetByInputObjectParameterSet
```
Set-AzHDInsightGatewayCredential [-HttpCredential] <PSCredential> [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] -InputObject <AzureHDInsightCluster> [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### SetByResourceIdParameterSet
```
Set-AzHDInsightGatewayCredential [-HttpCredential] <PSCredential> [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] -ResourceId <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzHDInsightGatewayCredential** menetapkan kredensial gateway dari kluster Azure HDInsight.

## EXAMPLES

### Contoh 1
```powershell
# Cluster info
$clusterName = "your-hadoop-001"
$clusterCreds = Get-Credential

Set-AzHDInsightGatewayCredential `
            -ClusterName $clusterName `
            -HttpCredential $clusterCreds
```

Perintah ini mengatur kredensial gateway kluster bernama your-hadoop-001 berdasarkan parameter nama yang ditetapkan.

### Contoh 2
```powershell
Set-AzHDInsightGatewayCredential `
            -ResourceId "/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.HDInsight/clusters/your-hadoop-001" `
            -HttpCredential $clusterCreds
```

Perintah ini mengatur kredensial gateway kluster bernama your-hadoop-001 oleh set parameter ResourceId.

### Contoh 3
```powershell
# Cluster info
$clusterName = "your-hadoop-001"
$clusterCreds = Get-Credential

Get-AzHDInsightCluster -ClusterName $clusterName | Set-AzHDInsightGatewayCredential `
            -HttpCredential $clusterCreds
```

Perintah ini mengatur info masuk gateway kluster bernama your-hadoop-001 oleh set parameter InputObject.

## PARAMETERS

### -AsJob
Jalankan cmdlet di latar belakang.

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

### -HttpCredential
Mendapatkan atau mengatur login untuk pengguna kluster.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -InputObject
Mendapatkan atau mengatur objek input.

```yaml
Type: Microsoft.Azure.Commands.HDInsight.Models.AzureHDInsightCluster
Parameter Sets: SetByInputObjectParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Mendapatkan atau mengatur nama kluster.

```yaml
Type: System.String
Parameter Sets: SetByNameParameterSet
Aliases: ClusterName

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Mendapatkan atau mengatur nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: SetByNameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
Mendapatkan atau mengatur id sumber daya.

```yaml
Type: System.String
Parameter Sets: SetByResourceIdParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Menunjukkan yang akan terjadi jika cmdlet dijalankan. Cmdlet tidak dijalankan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.HDInsight.Models.Management.AzureHDInsightGatewaySettings

## NOTES

## RELATED LINKS
