---
external help file: Microsoft.Azure.Commands.HDInsight.dll-Help.xml
Module Name: AzureRM.HDInsight
ms.assetid: 87B3C102-0A8C-4FFA-8429-594D2360AC32
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.hdinsight/remove-azurermhdinsightcluster
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/HDInsight/Commands.HDInsight/help/Remove-AzureRmHDInsightCluster.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/HDInsight/Commands.HDInsight/help/Remove-AzureRmHDInsightCluster.md
ms.openlocfilehash: aba2f1d2b5162e84c4765939195ce64214161a79
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142097767"
---
# Remove-AzureRmHDInsightCluster

## SYNOPSIS
Menghapus kluster HDInsight yang ditentukan dari langganan saat ini.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Remove-AzureRmHDInsightCluster [-ClusterName] <String> [-ResourceGroupName <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzureRmHDInsightCluster** menghapus kluster layanan HDInsight yang ditentukan dari langganan.
Operasi ini juga menghapus semua data yang disimpan dalam Hadoop Distributed File System (HDFS) di kluster.
Data yang disimpan di akun Azure Storage terkait tidak dihapus.
Data yang disimpan dalam metastore eksternal tidak dihapus.

## EXAMPLES

### Contoh 1: Menghapus kluster Azure HDInsight
```
PS C:\>Remove-AzureRmHDInsightCluster -ClusterName "your-hadoop-001"
```

Perintah ini menghapus kluster bernama your-hadoop-001.

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

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### Microsoft.Azure.Management.HDInsight.Models.ClusterGetResponse

## CATATAN

## RELATED LINKS

[Get-AzureRmHDInsightCluster](./Get-AzureRmHDInsightCluster.md)

[Gunakan-AzureRmHDInsightCluster](./Use-AzureRmHDInsightCluster.md)


