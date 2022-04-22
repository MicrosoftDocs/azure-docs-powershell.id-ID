---
external help file: Microsoft.WindowsAzure.Commands.HDInsight.dll-Help.xml
ms.assetid: 2EA36090-1A45-4F77-9222-9C0E9C07656C
online version: ''
schema: 2.0.0
ms.openlocfilehash: bb8f211d762773f6ed20ed1a744d5ff0da07f940
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142915451"
---
# Wait-AzureHDInsightJob

## SYNOPSIS
Menunggu penyelesaian atau kegagalan pekerjaan HDInsight dan menampilkan kemajuan pekerjaan.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### Dapatkan jobDetails History of a HDInsight Cluster (Default)
```
Wait-AzureHDInsightJob [-Credential <PSCredential>] [-WaitTimeoutInSeconds <Double>]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### Dapatkan jobDetails History of a HDInsight Cluster (with Specific Subscription Credential)
```
Wait-AzureHDInsightJob [-Certificate <X509Certificate2>] [-HostedService <String>] [-Endpoint <Uri>]
 [-IgnoreSslErrors <Boolean>] -Job <AzureHDInsightJob> -Subscription <String> [-WaitTimeoutInSeconds <Double>]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### Tunggu Pekerjaan dengan JobId di Cluster HDInsight
```
Wait-AzureHDInsightJob -Cluster <String> [-Credential <PSCredential>] -JobId <String>
 [-WaitTimeoutInSeconds <Double>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### Tunggu Pekerjaan dengan Pekerjaan di Cluster HDInsight
```
Wait-AzureHDInsightJob [-Credential <PSCredential>] -Job <AzureHDInsightJob> [-WaitTimeoutInSeconds <Double>]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Versi Azure PowerShell HDInsight ini sudah tidak digunakan lagi.
Cmdlet ini akan dihapus pada 1 Januari 2017.
Silakan gunakan versi Azure PowerShell HDInsight yang lebih baru.

Untuk informasi tentang cara menggunakan HDInsight baru untuk membuat klaster, lihat [Membuat kluster berbasis Linux dalam HDInsight menggunakan Azure PowerShell](https://azure.microsoft.com/en-us/documentation/articles/hdinsight-hadoop-create-linux-clusters-azure-powershell/) (https://azure.microsoft.com/en-us/documentation/articles/hdinsight-hadoop-create-linux-clusters-azure-powershell/).
Untuk informasi tentang cara mengirimkan pekerjaan dengan menggunakan Azure PowerShell dan pendekatan lain, lihat [Mengirimkan pekerjaan Hadoop di HDInsight](https://azure.microsoft.com/en-us/documentation/articles/hdinsight-submit-hadoop-jobs-programmatically/) (https://azure.microsoft.com/en-us/documentation/articles/hdinsight-submit-hadoop-jobs-programmatically/).
Untuk informasi referensi tentang Azure PowerShell HDInsight, lihat [Cmdlet Azure HDInsight](/powershell/module/servicemanagement/azure.service/?view=azuresmps-4.0.0#hd-insights).

Cmdlet **Wait-AzureHDInsightJob** menunggu penyelesaian atau kegagalan pekerjaan Azure HDInsight dan menampilkan kemajuan pekerjaan.

## EXAMPLES

### Contoh 1: Jalankan pekerjaan dan tunggu hingga selesai
```
PS C:\>$SubId = (Get-AzureSubscription -Current).SubscriptionId
PS C:>\ $ClusterName = "MyCluster"
PS C:>\ $WordCountJob = New-AzureHDInsightMapReduceJobDefinition -JarFile "/Example/Apps/Hadoop-examples.jar" -ClassName "Wordcount" -Defines @{ "mapred.map.tasks" = "3" } -Arguments "/Example/Data/Gutenberg/Davinci.txt", "/Example/Output/WordCount"
PS C:>\ $WordCountJob | Start-AzureHDInsightJob -Subscription $SubId -Cluster $ClusterName
    | Wait-AzureHDInsightJob -Subscription $SubId -WaitTimeoutInSeconds 3600
    | Get-AzureHDInsightJobOutput -Cluster $ClusterName -Subscription $SubId -StandardError
```

Perintah pertama mendapatkan ID langganan Azure saat ini, lalu menyimpannya dalam variabel $SubId.

Perintah kedua mendapatkan kluster yang ditentukan, lalu menyimpannya dalam variabel $ClusterName.

Perintah ketiga menggunakan cmdlet **New-AzureHDInsightMapReduceJobDefinition** untuk membuat definisi pekerjaan MapReduce, lalu menyimpannya dalam variabel $WordCountJob.

Perintah keempat menggunakan beberapa cmdlet secara berurutan:

- Operator ini menggunakan operator pipeline untuk mengirim $WordCountJob ke cmdlet **Start-AzureHDInsightJob** untuk memulai pekerjaan.
- Pekerjaan diteruskan ke cmdlet **Wait-AzureHDInsightJob** untuk menunggu 3600 detik agar pekerjaan selesai.
- Jika pekerjaan selesai, perintah menggunakan cmdlet **Get-AzureHDInsightJobOutput** untuk mendapatkan output pekerjaan.

## PARAMETERS

### -Sertifikat
Menentukan sertifikat manajemen untuk langganan Azure.

```yaml
Type: X509Certificate2
Parameter Sets: Get jobDetails History of a HDInsight Cluster (with Specific Subscription Credential)
Aliases: Cert

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Cluster
Menentukan kluster.
Cmdlet ini menunggu pekerjaan pada kluster yang ditentukan parameter ini.

```yaml
Type: String
Parameter Sets: Wait Job with JobId on an HDInsight Cluster
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Kredensial
Menentukan kredensial yang digunakan untuk akses HTTP langsung ke sebuah kluster.
Anda dapat menentukan parameter ini dan bukan parameter *Subscription* untuk mengautentikasi akses ke kluster.

```yaml
Type: PSCredential
Parameter Sets: Get jobDetails History of a HDInsight Cluster, Wait Job with JobId on an HDInsight Cluster, Wait Job with Job on an HDInsight Cluster
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
Parameter Sets: Get jobDetails History of a HDInsight Cluster (with Specific Subscription Credential)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HostedService
Menentukan ruang nama layanan HDInsight.
Jika Anda tidak menentukan parameter ini, ruang nama default digunakan.

```yaml
Type: String
Parameter Sets: Get jobDetails History of a HDInsight Cluster (with Specific Subscription Credential)
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
Parameter Sets: Get jobDetails History of a HDInsight Cluster (with Specific Subscription Credential)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Job
Menentukan pekerjaan Azure HDInsight.

```yaml
Type: AzureHDInsightJob
Parameter Sets: Get jobDetails History of a HDInsight Cluster (with Specific Subscription Credential), Wait Job with Job on an HDInsight Cluster
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -JobId
Menentukan ID pekerjaan yang harus ditunggu.

```yaml
Type: String
Parameter Sets: Wait Job with JobId on an HDInsight Cluster
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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
Cmdlet ini menunggu pekerjaan untuk langganan yang ditentukan parameter ini.

```yaml
Type: String
Parameter Sets: Get jobDetails History of a HDInsight Cluster (with Specific Subscription Credential)
Aliases: Sub

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WaitTimeoutInSeconds
Menentukan waktu habis, dalam detik, untuk operasi tunggu.
Jika waktu habis sebelum pekerjaan selesai, cmdlet berhenti berjalan.

```yaml
Type: Double
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureHDInsightJob](./Get-AzureHDInsightJob.md)

[Get-AzureHDInsightJobOutput](./Get-AzureHDInsightJobOutput.md)

[Start-AzureHDInsightJob](./Start-AzureHDInsightJob.md)

[Stop-AzureHDInsightJob](./Stop-AzureHDInsightJob.md)


