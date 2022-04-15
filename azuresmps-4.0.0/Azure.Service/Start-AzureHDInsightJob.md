---
external help file: Microsoft.WindowsAzure.Commands.HDInsight.dll-Help.xml
ms.assetid: 60A5ACF7-2637-4BDC-BF41-80E81B23F4CD
online version: ''
schema: 2.0.0
ms.openlocfilehash: 9121da87ff46d0b2cd52b114ad07c0b69a364976
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142334532"
---
# Start-AzureHDInsightJob

## SYNOPSIS
Memulai pekerjaan HDInsight.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### Memulai jobDetails di HdInsight Cluster (Default)
```
Start-AzureHDInsightJob -Cluster <String> [-Credential <PSCredential>]
 -JobDefinition <AzureHDInsightJobDefinition> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### Memulai jobDetails di Cluster HDInsight (dengan Kredensial Langganan Tertentu)
```
Start-AzureHDInsightJob [-Certificate <X509Certificate2>] [-HostedService <String>] -Cluster <String>
 [-Endpoint <Uri>] [-IgnoreSslErrors <Boolean>] -JobDefinition <AzureHDInsightJobDefinition>
 [-Subscription <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Versi Azure PowerShell HDInsight ini sudah tidak digunakan lagi.
Cmdlet ini akan dihapus pada 1 Januari 2017.
Silakan gunakan versi Azure PowerShell HDInsight yang lebih baru.

Untuk informasi tentang cara menggunakan HDInsight baru untuk membuat klaster, lihat [Membuat kluster berbasis Linux dalam HDInsight menggunakan Azure PowerShell](https://azure.microsoft.com/en-us/documentation/articles/hdinsight-hadoop-create-linux-clusters-azure-powershell/) (https://azure.microsoft.com/en-us/documentation/articles/hdinsight-hadoop-create-linux-clusters-azure-powershell/).
Untuk informasi tentang cara mengirimkan pekerjaan dengan menggunakan Azure PowerShell dan pendekatan lain, lihat [Mengirimkan pekerjaan Hadoop di HDInsight](https://azure.microsoft.com/en-us/documentation/articles/hdinsight-submit-hadoop-jobs-programmatically/) (https://azure.microsoft.com/en-us/documentation/articles/hdinsight-submit-hadoop-jobs-programmatically/).
Untuk informasi referensi tentang Azure PowerShell HDInsight, lihat [Cmdlet Azure HDInsight](/powershell/module/servicemanagement/azure.service/?view=azuresmps-4.0.0#hd-insights).

Cmdlet **Start-AzureHDInsightJob** memulai pekerjaan Azure HDInsight yang ditentukan pada kluster tertentu.
Pekerjaan untuk memulai dapat berupa pekerjaan MapReduce, pekerjaan streaming, pekerjaan Hive, atau pekerjaan Babi.

## EXAMPLES

### Contoh 1: Memulai pekerjaan HDInsight
```
PS C:\>$SubId = (Get-AzureSubscription -Current).SubscriptionId
PS C:\> $ClusterName = "Cluster01"
PS C:\> $WordCountJob = New-AzureHDInsightMapReduceJobDefinition -JarFile "/Example/Apps/Hadoop-examples.jar" -ClassName "Wordcount" -Defines @{ "mapred.map.tasks" = "3" } -Arguments "/Example/Data/Gutenberg/Davinci.txt", "/Example/Output/WordCount"
PS C:\> $WordCountJob | Start-AzureHDInsightJob -Cluster $ClusterName
    | Wait-AzureHDInsightJob -Subscription $SubId -WaitTimeoutInSeconds 3600
    | Get-AzureHDInsightJobOutput -Cluster $ClusterName -Subscription $SubId -StandardError
```

Perintah pertama mendapatkan ID langganan saat ini, lalu menyimpannya dalam variabel $SubId.

Perintah kedua menetapkan nama Cluster01 ke variabel $ClusterName.

Perintah ketiga menggunakan cmdlet **New-AzureHDInsightMapReduceJobDefinition** untuk membuat definisi pekerjaan MapReduce, lalu menyimpannya dalam variabel $WordCountJob.

Perintah terakhir menggunakan operator pipeline untuk meneruskan $WordCountJob ke cmdlet **Start-AzureHDInsightJob** untuk memulai pekerjaan.
Setelah pekerjaan dimulai, dialihkan ke cmdlet **Wait-AzureHDInsightJob** , yang menunggu pekerjaan selesai sebelum meneruskannya ke cmdlet **Get-AzureHDInsightJobOutput** untuk mendapatkan output pekerjaan.

## PARAMETERS

### -Sertifikat
Menentukan sertifikat manajemen untuk langganan Azure.

```yaml
Type: X509Certificate2
Parameter Sets: Start jobDetails on an HDInsight Cluster (with Specific Subscription Credential)
Aliases: Cert

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Cluster
Menentukan kluster.
Cmdlet ini memulai pekerjaan pada kluster yang ditentukan parameter ini.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ClusterName

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Kredensial
Menentukan kredensial kluster untuk akses HTTP langsung ke sebuah kluster.
Anda dapat menentukan parameter ini dan bukan parameter *Subscription* untuk mengautentikasi akses ke kluster.

```yaml
Type: PSCredential
Parameter Sets: Start jobDetails on an HDInsight Cluster
Aliases: Cred

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Titik akhir
Menentukan titik akhir untuk digunakan untuk menyambungkan ke Azure.
Jika Anda tidak menentukan parameter ini, cmdlet ini menggunakan titik akhir default.

```yaml
Type: Uri
Parameter Sets: Start jobDetails on an HDInsight Cluster (with Specific Subscription Credential)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HostedService
Menentukan ruang nama layanan HDInsight jika Anda tidak ingin menggunakan ruang nama default.

```yaml
Type: String
Parameter Sets: Start jobDetails on an HDInsight Cluster (with Specific Subscription Credential)
Aliases: CloudServiceName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IgnoreSslErrors
Menunjukkan apakah kesalahan Secure Sockets Layer (SSL) diabaikan.

```yaml
Type: Boolean
Parameter Sets: Start jobDetails on an HDInsight Cluster (with Specific Subscription Credential)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobDefinition
Menentukan titik akhir untuk digunakan saat menyambungkan ke Microsoft Azure jika titik akhir berbeda dari default.

```yaml
Type: AzureHDInsightJobDefinition
Parameter Sets: (All)
Aliases: jobDetails

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Profil
Menentukan profil Azure tempat cmdlet ini dibaca.
Jika Anda tidak menentukan profil, cmdlet ini akan dibaca dari profil default lokal.

```yaml
Type: AzureSMProfile
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Langganan
Menentukan langganan.
Cmdlet ini memulai pekerjaan untuk langganan yang ditentukan parameter ini.

```yaml
Type: String
Parameter Sets: Start jobDetails on an HDInsight Cluster (with Specific Subscription Credential)
Aliases: Sub

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Get-AzureHDInsightJob](./Get-AzureHDInsightJob.md)

[Get-AzureHDInsightJobOutput](./Get-AzureHDInsightJobOutput.md)

[Baru-AzureHDInsightMapReduceJobDefinition](./New-AzureHDInsightMapReduceJobDefinition.md)

[Stop-AzureHDInsightJob](./Stop-AzureHDInsightJob.md)

[Tunggu-AzureHDInsightJob](./Wait-AzureHDInsightJob.md)


