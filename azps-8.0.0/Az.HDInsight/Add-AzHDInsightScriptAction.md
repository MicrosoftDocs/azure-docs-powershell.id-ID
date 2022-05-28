---
external help file: Microsoft.Azure.PowerShell.Cmdlets.HDInsight.dll-Help.xml
Module Name: Az.HDInsight
ms.assetid: 8F0634BD-D817-4365-B6D1-924DC36AE4C9
online version: https://docs.microsoft.com/powershell/module/az.hdinsight/add-azhdinsightscriptaction
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/HDInsight/HDInsight/help/Add-AzHDInsightScriptAction.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/HDInsight/HDInsight/help/Add-AzHDInsightScriptAction.md
ms.openlocfilehash: 7e4f78990e944d29b8903c0d1789b1e7bb22fc8c
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145618825"
---
# Add-AzHDInsightScriptAction

## SYNOPSIS
Menambahkan tindakan skrip ke objek konfigurasi kluster.

## SYNTAX

```
Add-AzHDInsightScriptAction [-Config] <AzureHDInsightConfig> [-NodeType] <ClusterNodeType> [-Uri] <Uri>
 [-Name] <String> [[-Parameters] <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Add-AzHDInsightScriptAction** menambahkan tindakan skrip ke objek konfigurasi HDInsight yang dibuat oleh cmdlet New-AzHDInsightClusterConfig.
Tindakan skrip menyediakan fungsionalitas yang digunakan untuk menginstal perangkat lunak tambahan atau untuk mengubah konfigurasi aplikasi yang berjalan pada kluster Hadoop dengan menggunakan skrip Windows PowerShell atau Bash (untuk kluster Windows atau Linux).
Tindakan skrip berjalan pada node kluster ketika kluster HDInsight disebarkan, dan dijalankan setelah node di kluster menyelesaikan konfigurasi HDInsight.
Tindakan skrip berjalan di bawah hak istimewa akun administrator sistem dan memberikan hak akses penuh ke node kluster.
Anda dapat menyediakan setiap kluster dengan daftar tindakan skrip untuk dijalankan dalam urutan tertentu.

## EXAMPLES

### Contoh 1: Menambahkan tindakan skrip ke objek konfigurasi kluster
```powershell
# Primary storage account info
$storageAccountResourceGroupName = "Group"
$storageAccountResourceId = "yourstorageaccountresourceid"
$storageAccountName = "yourstorageacct001"
$storageAccountKey = (Get-AzStorageAccountKey -ResourceGroupName $storageAccountResourceGroupName -Name $storageAccountName)[0].value


$storageContainer = "container001"

# Script action info
$scriptActionName = "<script action name>"
$scriptActionURI = "<script action URI>"
$scriptActionParameters = "<script action parameters>" 

# Cluster configuration info
$location = "East US 2"
$clusterResourceGroupName = "Group"
$clusterName = "your-hadoop-001"
$clusterCreds = Get-Credential

# If the cluster's resource group doesn't exist yet, run:
#   New-AzResourceGroup -Name $clusterResourceGroupName -Location $location

# Create the cluster
New-AzHDInsightClusterConfig  `
            | Add-AzHDInsightScriptAction `
                -Name $scriptActionName `
                -Uri $scriptActionURI `
                -Parameters $scriptActionParameters `
                -NodeType Worker `
            | Add-AzHDInsightScriptAction `
                -Name $scriptActionName `
                -Uri $scriptActionURI `
                -Parameters $scriptActionParameters `
                -NodeType Head `
            | New-AzHDInsightCluster `
                -ClusterType Hadoop `
                -OSType Windows `
                -ClusterSizeInNodes 4 `
                -ResourceGroupName $clusterResourceGroupName `
                -ClusterName $clusterName `
                -HttpCredential $clusterCreds `
                -Location $location `
                -StorageAccountResourceId $storageAccountResourceId `
                -StorageAccountKey $storageAccountKey `
                -StorageContainer $storageContainer
```

Perintah ini menambahkan tindakan skrip untuk simpul Kepala dan Pekerja dari kluster your-hadoop-001, untuk dijalankan di akhir pembuatan kluster.

## PARAMETERS

### -Config
Menentukan objek konfigurasi kluster HDInsight yang dimodifikasi cmdlet ini.
Objek ini dibuat oleh cmdlet **New-AzHDInsightClusterConfig** .

```yaml
Type: Microsoft.Azure.Commands.HDInsight.Models.AzureHDInsightConfig
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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

### -Name
Menentukan nama tindakan skrip.

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

### -NodeType
Menentukan jenis node untuk menjalankan tindakan skrip.
Nilai yang dapat diterima untuk parameter ini adalah:
- HeadNode
- WorkerNode
- ZookeeperNode

```yaml
Type: Microsoft.Azure.Management.HDInsight.Models.ClusterNodeType
Parameter Sets: (All)
Aliases:
Accepted values: HeadNode, WorkerNode, ZookeeperNode, EdgeNode

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Parameters
Menentukan parameter untuk tindakan skrip.

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

### -Uri
Menentukan URI publik untuk tindakan skrip (skrip PowerShell atau Bash).

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.Commands.HDInsight.Models.AzureHDInsightConfig

## OUTPUTS

### Microsoft.Azure.Commands.HDInsight.Models.AzureHDInsightConfig

## NOTES

## RELATED LINKS

[New-AzHDInsightClusterConfig](./New-AzHDInsightClusterConfig.md)


