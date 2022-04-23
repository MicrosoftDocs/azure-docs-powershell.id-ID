---
external help file: Microsoft.WindowsAzure.Commands.HDInsight.dll-Help.xml
ms.assetid: FF41DDBA-6D4B-47A5-BCFF-3D0BB1D375C5
online version: ''
schema: 2.0.0
ms.openlocfilehash: b021f120f202f1754e14005629d7a119cdaa7463
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143103311"
---
# Set-AzureHDInsightDefaultStorage

## SYNOPSIS
Mengatur akun penyimpanan default untuk kluster HDInsight.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Set-AzureHDInsightDefaultStorage -Config <AzureHDInsightConfig> -StorageAccountKey <String>
 -StorageAccountName <String> -StorageContainerName <String> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Versi Azure PowerShell HDInsight ini sudah tidak digunakan lagi.
Cmdlet ini akan dihapus pada 1 Januari 2017.
Silakan gunakan versi Azure PowerShell HDInsight yang lebih baru.

Untuk informasi tentang cara menggunakan HDInsight baru untuk membuat klaster, lihat [Membuat kluster berbasis Linux dalam HDInsight menggunakan Azure PowerShell](https://azure.microsoft.com/en-us/documentation/articles/hdinsight-hadoop-create-linux-clusters-azure-powershell/) (https://azure.microsoft.com/en-us/documentation/articles/hdinsight-hadoop-create-linux-clusters-azure-powershell/).
Untuk informasi tentang cara mengirimkan pekerjaan dengan menggunakan Azure PowerShell dan pendekatan lain, lihat [Mengirimkan pekerjaan Hadoop di HDInsight](https://azure.microsoft.com/en-us/documentation/articles/hdinsight-submit-hadoop-jobs-programmatically/) (https://azure.microsoft.com/en-us/documentation/articles/hdinsight-submit-hadoop-jobs-programmatically/).
Untuk informasi referensi tentang Azure PowerShell HDInsight, lihat [Cmdlet Azure HDInsight](/powershell/module/servicemanagement/azure.service/?view=azuresmps-4.0.0#hd-insights).

Cmdlet **Set-AzureHDInsightDefaultStorage** mengatur akun penyimpanan default untuk konfigurasi kluster HDInsight.

## EXAMPLES

### Contoh 1: Mengatur akun penyimpanan default
```
PS C:\>$SubId = (Get-AzureSubscription -Current).SubscriptionId
PS C:\> $Key1 = Get-AzureStorageKey -StorageAccountName "MyBlobStorage" | %{ $_.Primary }
PS C:\> $Key2 = Get-AzureStorageKey -StorageAccountName "MySecondBlobStorage" | %{ $_.Primary }
PS C:\> $Creds = Get-Credential
PS C:\> $OozieCreds = Get-Credential
PS C:\> $HiveCreds = Get-Credential
PS C:\> New-AzureHDInsightClusterConfig -ClusterSizeInNodes 4
    | Set-AzureHDInsightDefaultStorage -StorageAccountName "MyBlobStorage.blob.core.windows.net" -StorageAccountKey $Key1 -StorageContainerName "MyContainer"
    | Add-AzureHDInsightStorage -StorageAccountName "MySecondBlobStorage.blob.core.windows.net" -StorageAccountKey $Key2
    | Add-AzureHDInsightMetastore -SqlAzureServerName "MySqlServer.database.windows.net" -DatabaseName "MyOozieDatabaseName" -Credential $OozieCreds -MetastoreType OozieMetastore
    | Add-AzureHDInsightMetastore -SqlAzureServerName "MySqlServer.database.widows.net" -DatabaseName "MyHiveDatabaseName" -Credential $HiveCreds -MetastoreType HiveMetastore
    | New-AzureHDInsightCluster -Subscription $SubId -Credential $Creds
```

Perintah pertama menggunakan cmdlet **Get-AzureSubscription** untuk mendapatkan ID langganan saat ini, lalu menyimpannya dalam variabel $SubId.

Perintah kedua dan ketiga menggunakan cmdlet **Get-AzureStorageKey** untuk mendapatkan kunci penyimpanan utama untuk MyBlobStorage dan MySecondBlobStorage, lalu menyimpan kunci dalam variabel $Key 1 dan $Key 2.

Perintah keempat, kelima, dan keenam menggunakan cmdlet **Get-Credential** untuk mendapatkan kredensial untuk langganan saat ini, lalu menyimpan kredensial dalam variabel $Creds, $OozieCreds, dan $HiveCreds.

Perintah akhir melakukan serangkaian operasi dengan menggunakan cmdlet ini:

- **New-AzureHDInsightClusterConfig** untuk membuat konfigurasi kluster HDInsight.
- **Set-AzureHDInsightDefaultStorage** untuk mengatur akun penyimpanan default agar konfigurasi MyBlobStorage.blob.core.windows.net.
- **Add-AzureHDInsightStorage** untuk menambahkan akun penyimpanan kedua yang bernama MySecondBlobStorage.blob.core.windows.net ke konfigurasi.
- **Add-AzureHDInsightMetastore** untuk menambahkan metastore untuk Oozie dan metastore untuk Hive ke konfigurasi.
- **AzureHDInsightCluster baru** untuk membuat kluster HDInsight dengan konfigurasi baru.

## PARAMETERS

### -Config
Menentukan objek konfigurasi.
Cmdlet ini mengatur akun penyimpanan default untuk objek yang ditentukan parameter ini.

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

### -StorageAccountKey
Menentukan kunci akun penyimpanan yang digunakan untuk mengakses akun penyimpanan default.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageAccountName
Menentukan nama akun penyimpanan default.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageContainerName
Menentukan nama wadah penyimpanan default untuk sebuah kluster.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Add-AzureHDInsightMetastore](./Add-AzureHDInsightMetastore.md)

[Add-AzureHDInsightStorage](./Add-AzureHDInsightStorage.md)

[AzureHDInsightCluster baru](./New-AzureHDInsightCluster.md)

[Baru-AzureHDInsightClusterConfig](./New-AzureHDInsightClusterConfig.md)


