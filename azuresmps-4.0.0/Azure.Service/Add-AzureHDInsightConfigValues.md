---
external help file: Microsoft.WindowsAzure.Commands.HDInsight.dll-Help.xml
ms.assetid: 6F89C297-4D3D-4DAD-A63A-FCC51A86BF43
online version: ''
schema: 2.0.0
ms.openlocfilehash: 996aa028500fb90ea3fccfc78a615cb0cdb40f96
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142095890"
---
# Add-AzureHDInsightConfigValues

## SYNOPSIS
Menambahkan kustomisasi nilai konfigurasi Hadoop atau kustomisasi pustaka bersama Hive ke konfigurasi kluster HDInsight.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Add-AzureHDInsightConfigValues -Config <AzureHDInsightConfig> [-Core <Hashtable>] [-Yarn <Hashtable>]
 [-Hdfs <Hashtable>] [-Hive <AzureHDInsightHiveConfiguration>]
 [-MapReduce <AzureHDInsightMapReduceConfiguration>] [-Oozie <AzureHDInsightOozieConfiguration>]
 [-Storm <Hashtable>] [-Spark <Hashtable>] [-HBase <AzureHDInsightHBaseConfiguration>]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Versi Azure PowerShell HDInsight ini sudah tidak digunakan lagi.
Cmdlet ini akan dihapus pada 1 Januari 2017.
Silakan gunakan versi Azure PowerShell HDInsight yang lebih baru.

Untuk informasi tentang cara menggunakan HDInsight baru untuk membuat kluster, lihat [Membuat kluster berbasis Linux dalam HDInsight menggunakan Azure PowerShell](https://azure.microsoft.com/en-us/documentation/articles/hdinsight-hadoop-create-linux-clusters-azure-powershell/).
Untuk informasi tentang cara mengirimkan pekerjaan dengan menggunakan Azure PowerShell dan pendekatan lain, lihat [Mengirimkan pekerjaan Hadoop di HDInsight](https://azure.microsoft.com/en-us/documentation/articles/hdinsight-submit-hadoop-jobs-programmatically/).
Untuk informasi referensi tentang Azure PowerShell HDInsight, lihat [Cmdlet Azure HDInsight](/powershell/module/servicemanagement/azure.service/?view=azuresmps-4.0.0#hd-insights).

Cmdlet **Add-AzureHDInsightConfigValues** menambahkan kustomisasi nilai konfigurasi Hadoop, seperti Core-site.xml atau Hive-site.xml, atau kustomisasi pustaka bersama Hive ke konfigurasi kluster Azure HDInsight.

Cmdlet menambahkan nilai konfigurasi kustom ke objek konfigurasi tertentu.
Pengaturan kustom ditambahkan ke file konfigurasi layanan Hadoop yang relevan ketika kluster disebarkan.

## EXAMPLES

### Contoh 1: Mengonfigurasi kluster
```
PS C:\>$HiveConfigValues = New-Object 'Microsoft.WindowsAzure.Management.HDInsight.Cmdlet.DataObjects.AzureHDInsightHiveConfiguration'
PS C:\> $HiveConfigValues.Configuration = @{ hive.exec.compress.output = true }
PS C:\> $HiveConfigValues.AdditionalLibraries = New-Object 'Microsoft.WindowsAzure.Management.HDInsight.Cmdlet.DataObjects.AzureHDInsightDefaultStorageAccount'
PS C:\> $HiveConfigValues.AdditionalLibraries.StorageAccountName = "MyStorageAccount.blob.core.windows.net"
PS C:\> $HiveConfigValues.AdditionalLibraries.StorageAccountKey = (Get-AzureStorageKey -StorageAccountName "MyStorageAccount").Primary
PS C:\> $HiveConfigValues.AdditionalLibraries.StorageContainerName = "MySharedLibContainer"
PS C:\> $OozieConfigValues = New-Object 'Microsoft.WindowsAzure.Management.HDInsight.Cmdlet.DataObjects.AzureHDInsightOozieConfiguration'
PS C:\> $OozieConfigValues.Configuration = @{ hive.exec.compress.output = true }
PS C:\> $MapredConfigValues = New-Object 'Microsoft.WindowsAzure.Management.HDInsight.Cmdlet.DataObjects.AzureHDInsightMapReduceConfiguration'
PS C:\> $MapredConfigValues.Configuration = @{ mapred.map.max.attempts = 2 }
PS C:\> $MapredConfigValues.CapacitySchedulerConfiguration = @{ mapred.capacity-scheduler.init-poll-interval = 1000 }
PS C:\> $Config = New-AzureHDInsightClusterConfig -ClusterSizeInNodes 4
    | Set-AzureHDInsightDefaultStorage -StorageAccountName MyStorageAccount.blob.core.windows.net -StorageAccountKey (Get-AzureStorageKey -StorageAccountName "MyStorageAccount").Primary -StorageContainerName "MyStorageContainer"
    | Add-AzureHDInsightConfigValues -Core @{ io.file.buffer.size = 300000 } -MapReduce $MapredConfigValues -Hive $HiveConfigValues -Oozie $OozieConfigValues
PS C:\> $Config | New-AzureHDInsightCluster -Subscription $SubId -Credential $Creds -Name "MyCluster" -Location "North Europe"
```

Perintah pertama membuat objek **AzureHDInsightHiveConfiguration** baru, lalu menyimpannya dalam variabel $HiveConfigValues.

Lima perintah berikutnya membuat nilai konfigurasi untuk Sarang dan menyimpan nilai tersebut sebagai anggota $HiveConfigValues.

Perintah ketujuh membuat objek **AzureHDInsightOozieConfiguration** , lalu menyimpannya dalam variabel $OozieConfigValues.
Perintah kedelapan membuat nilai konfigurasi untuk Oozie, lalu menyimpan nilai tersebut sebagai anggota $OozieConfigValues.

Perintah kesembilan membuat objek **AzureHDInsightMapReduceConfiguration** , lalu menyimpannya dalam variabel $MapredConfigValues.
Dua perintah berikutnya membuat nilai konfigurasi untuk MapReduce dan menyimpan nilai tersebut sebagai anggota $MapredConfigValues.

Perintah kedua belas menggunakan cmdlet **New-AzureHDInsightClusterConfig** untuk membuat konfigurasi kluster HDInsight, lalu menyimpannya dalam variabel $Config.
Perintah menggunakan operator saluran untuk meneruskan $Config ke cmdlet **Set-AzureHDInsightDefaultStorage** untuk memperbarui pengaturan penyimpanan default dan ke cmdlet **Add-AzureHDInsightConfigValues** untuk menambahkan nilai konfigurasi baru ke konfigurasi kluster.

Perintah terakhir menggunakan operator pipeline untuk mengirimkan $Config ke cmdlet **New-AzureHDInsightCluster** untuk membuat klaster HDInsight baru dengan pengaturan yang dikustomisasi.

## PARAMETERS

### -Config
Menentukan objek konfigurasi yang akan ditambahkan konfigurasi Hadoop.

```yaml
Type: AzureHDInsightConfig
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Core
Menentukan sekumpulan nilai konfigurasi Hadoop untuk Core-site.xml.

```yaml
Type: Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HBase
Menentukan sekumpulan nilai konfigurasi HBase untuk Hbase-site.xml.

```yaml
Type: AzureHDInsightHBaseConfiguration
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Hdfs
Menentukan sekumpulan nilai konfigurasi Hadoop untuk Hdfs-site.xml.

```yaml
Type: Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Sarang
Menentukan objek kustomisasi untuk layanan Hadoop Hive, termasuk sekumpulan nilai konfigurasi Hadoop untuk pustaka bersama Hive-site.xml dan Sarang.

```yaml
Type: AzureHDInsightHiveConfiguration
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MapReduce
Menentukan objek kustomisasi untuk MapReduce dan penjadwal kapasitas.

```yaml
Type: AzureHDInsightMapReduceConfiguration
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Oozie
Menentukan objek kustomisasi untuk layanan Hadoop Oozie, termasuk sekumpulan nilai konfigurasi Hadoop untuk Oozie-site.xml.

```yaml
Type: AzureHDInsightOozieConfiguration
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### -Spark
Menentukan objek kustomisasi untuk Apache Spark.

```yaml
Type: Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Badai
Menentukan objek kustomisasi untuk Apache Storm.

```yaml
Type: Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Yarn
Menentukan objek kustomisasi untuk Hadoop YARN, menentukan sekumpulan nilai konfigurasi YARN yang dikustomisasi untuk Yarn-site.xml.

```yaml
Type: Hashtable
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

## OUTPUTS

## CATATAN

## RELATED LINKS

[AzureHDInsightCluster baru](./New-AzureHDInsightCluster.md)

[Baru-AzureHDInsightClusterConfig](./New-AzureHDInsightClusterConfig.md)

[Set-AzureHDInsightDefaultStorage](./Set-AzureHDInsightDefaultStorage.md)
