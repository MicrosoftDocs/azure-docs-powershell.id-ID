---
external help file: Microsoft.Azure.PowerShell.Cmdlets.HDInsight.dll-Help.xml
Module Name: Az.HDInsight
ms.assetid: B9BA5FD1-A4F8-4E24-8FCB-847649B82AB6
online version: https://docs.microsoft.com/powershell/module/az.hdinsight/new-azhdinsightpigjobdefinition
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/HDInsight/HDInsight/help/New-AzHDInsightPigJobDefinition.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/HDInsight/HDInsight/help/New-AzHDInsightPigJobDefinition.md
ms.openlocfilehash: 8d46569142d95dd3a548e0e94c44d2ed4bacc383
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144682050"
---
# New-AzHDInsightPigJobDefinition

## SYNOPSIS
Membuat objek pekerjaan Pig.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.hdinsight/new-azhdinsightpigjobdefinition) untuk informasi terbaru.

## SYNTAX

```
New-AzHDInsightPigJobDefinition [-Arguments <String[]>] [-Files <String[]>] [-StatusFolder <String>]
 [-File <String>] [-Query <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzHDInsightPigJobDefinition mendefinisikan** objek pekerjaan Pig untuk digunakan dengan kluster Azure HDInsight.

## EXAMPLES

### Contoh 1: Membuat definisi kerja Pig
```powershell
# Cluster info
$clusterName = "your-hadoop-001"
$clusterCreds = Get-Credential

# Pig job details
$statusFolder = "tempStatusFolder/"
$query = "SHOW TABLES"

New-AzHDInsightPigJobDefinition -StatusFolder $statusFolder `
            -Query $query `
        | Start-AzHDInsightJob `
            -ClusterName $clusterName `
            -ClusterCredential $clusterCreds
```

Perintah ini membuat definisi kerja Pig.

## PARAMETERS

### -Argumen
Menentukan array argumen untuk pekerjaan tersebut.
Argumen diteruskan sebagai argumen baris-perintah untuk tiap pekerjaan.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
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

### -File
Menentukan jalur ke file yang berisi kueri yang akan dijalankan.
File harus tersedia di akun penyimpanan yang terkait dengan kluster.
Anda bisa menggunakan parameter ini alih-alih parameter *Kueri* .

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

### -Files
Menentukan kumpulan file yang terkait dengan pekerjaan Apache Hive.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Kueri
Menentukan kueri Pig.

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

### -StatusFolder
Menentukan lokasi folder yang berisi output standar dan output kesalahan untuk pekerjaan.

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

### Microsoft.Azure.Commands.HDInsight.Models.AzureHDInsightPigJobDefinition

## NOTES

## RELATED LINKS

[Start-AzHDInsightJob](./Start-AzHDInsightJob.md)


