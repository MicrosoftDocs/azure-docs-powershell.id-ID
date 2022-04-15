---
external help file: Microsoft.Azure.PowerShell.Cmdlets.HDInsight.dll-Help.xml
Module Name: Az.HDInsight
ms.assetid: 6BF6F9A7-BED3-4CCE-9E0A-46ECBFF55DA9
online version: https://docs.microsoft.com/powershell/module/az.hdinsight/new-azhdinsightmapreducejobdefinition
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/HDInsight/HDInsight/help/New-AzHDInsightMapReduceJobDefinition.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/HDInsight/HDInsight/help/New-AzHDInsightMapReduceJobDefinition.md
ms.openlocfilehash: 8faa411e1fbc8e6923f9a3bc02b0e477877d8e2f
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142474271"
---
# New-AzHDInsightMapReduceJobDefinition

## SYNOPSIS
Membuat objek pekerjaan MapReduce.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.hdinsight/new-azhdinsightmapreducejobdefinition) untuk informasi terbaru.

## SYNTAX

```
New-AzHDInsightMapReduceJobDefinition [-Arguments <String[]>] [-Files <String[]>] [-StatusFolder <String>]
 -ClassName <String> [-Defines <Hashtable>] -JarFile <String> [-JobName <String>] [-LibJars <String[]>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzHDInsightMapReduceJobDefinition** menentukan pekerjaan MapReduce baru untuk digunakan dengan cluster Azure HDInsight.

## EXAMPLES

### Contoh 1: Membuat definisi pekerjaan MapReduce
```
PS C:\># Cluster info
PS C:\>$clusterName = "your-hadoop-001"
PS C:\>$clusterCreds = Get-Credential

PS C:\>New-AzHDInsightMapReduceJobDefinition -StatusFolder $statusFolder `
            -ClassName $className `
            -JarFile $jarFilePath `
        | Start-AzHDInsightJob `
            -ClusterName $clusterName `
            -ClusterCredential $clusterCreds
```

Perintah ini membuat definisi pekerjaan MapReduce.

## PARAMETERS

### -Argumen
Menentukan array argumen untuk pekerjaan tersebut.
Argumen dikirim sebagai argumen baris perintah ke setiap tugas.

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

### -ClassName
Menentukan kelas pekerjaan dalam file JAR.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
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

### -Defines
Menentukan nilai konfigurasi Hadoop untuk diatur saat pekerjaan berjalan.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Files
Menentukan kumpulan file yang terkait dengan pekerjaan Hive.

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

### -JarFile
Menentukan file JAR yang akan digunakan untuk pekerjaan tersebut.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobName
Menentukan nama pekerjaan.

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

### -LibJars
Menentukan JARS lib untuk pekerjaan tersebut.

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

### -StatusFolder
Menentukan lokasi folder yang berisi output standar dan output kesalahan untuk suatu pekerjaan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### Microsoft.Azure.Commands.HDInsight.Models.AzureHDInsightMapReduceJobDefinition

## CATATAN

## RELATED LINKS

[Start-AzHDInsightJob](./Start-AzHDInsightJob.md)


