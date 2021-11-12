---
external help file: Microsoft.WindowsAzure.Commands.HDInsight.dll-Help.xml
ms.assetid: FF8AA7DE-1E0F-4F5B-95F6-7820AAF789F2
online version: ''
schema: 2.0.0
ms.openlocfilehash: 6e75eaf2fd12644b3ae98a3d76437be46238bfd5
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132423216"
---
# New-AzureHDInsightClusterConfig

## SYNOPSIS
Membuat konfigurasi kluster HDInsight yang tidak ada.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
New-AzureHDInsightClusterConfig -ClusterSizeInNodes <Int32> [-HeadNodeVMSize <String>]
 [-ClusterType <ClusterType>] [-VirtualNetworkId <String>] [-SubnetName <String>] [-DataNodeVMSize <String>]
 [-ZookeeperNodeVMSize <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Versi Azure PowerShell HDInsight ini sudah tidak berlaku.
Cmdlets ini akan dihapus pada 1 Januari 2017.
Silakan gunakan versi yang lebih baru Azure PowerShell HDInsight.

Untuk informasi tentang cara menggunakan HDInsight yang baru untuk membuat kluster, lihat Membuat kluster berbasis Linux di [HDInsight menggunakan Azure PowerShell](https://azure.microsoft.com/en-us/documentation/articles/hdinsight-hadoop-create-linux-clusters-azure-powershell/) ( https://azure.microsoft.com/en-us/documentation/articles/hdinsight-hadoop-create-linux-clusters-azure-powershell/) .
Untuk informasi tentang cara mengirimkan pekerjaan menggunakan Azure PowerShell dan pendekatan lain, lihat [Mengirimkan pekerjaan Hadoop di HDInsight](https://azure.microsoft.com/en-us/documentation/articles/hdinsight-submit-hadoop-jobs-programmatically/) ( https://azure.microsoft.com/en-us/documentation/articles/hdinsight-submit-hadoop-jobs-programmatically/) .
Untuk informasi referensi tentang Azure PowerShell HDInsight, [lihat Cmdlet Azure HDInsight](/powershell/module/servicemanagement/azure.service/?view=azuresmps-4.0.0#hd-insights).

Cmdlet **New-AzureHDInsightClusterConfig** membuat konfigurasi kluster Azure HDInsight yang tidak ada.

## EXAMPLES

### Contoh 1: Buat konfigurasi kluster
```
PS C:\>$SubId = (Get-AzureSubscription -Current).SubscriptionId
PS C:\> $Key1 = Get-AzureStorageKey -StorageAccountName "MyBlobStorage" | %{ $_.Primary }
PS C:\> $Key2 = Get-AzureStorageKey -StorageAccountName "MySecondBlobStorage" | %{ $_.Primary }
PS C:\> $Creds = Get-Credential
PS C:\> $OozieCreds = Get-Credential
PS C:\> $HiveCreds = Get-Credential
PS C:\> New-AzureHDInsightClusterConfig -ClusterSizeInNodes 4
    | Set-AzureHDInsightDefaultStorage -StorageAccountName MyBlobStorage.blob.core.windows.net -StorageAccountKey $Key1 -StorageContainerName "MyContainer"
    | Add-AzureHDInsightStorage -StorageAccountName "MySecondBlobStorage.blob.core.windows.net" -StorageAccountKey $Key2
    | Add-AzureHDInsightMetastore -SqlAzureServerName "MySqlServer.database.windows.net" -DatabaseName "MyOozieDatabaseName" -Credential $OozieCreds -MetastoreType OozieMetastore
    | Add-AzureHDInsightMetastore -SqlAzureServerName "MySqlServer.database.widows.net" -DatabaseName "MyHiveDatabaseName" -Credential $HiveCreds -MetastoreType HiveMetastore
    | New-AzureHDInsightCluster -Subscription $SubID -Credential $Creds
```

Perintah pertama menggunakan cmdlet **Get-AzureSubscription** untuk mendapatkan ID langganan saat ini, lalu menyimpannya dalam $SubId variabel.

Perintah kedua dan ketiga menggunakan cmdlet **Get-AzureStorageKey** untuk mendapatkan kunci penyimpanan utama untuk variabel MyBlobStorage dan MySecondBlobStorage, lalu menyimpan kunci dalam variabel $Key 1 dan $Key 2.

Perintah keempat, kelima, dan keenam menggunakan cmdlet **Get-Credential** untuk mendapatkan kredensial untuk langganan saat ini, lalu untuk Oozie dan Hive, kemudian menyimpan kredensial dalam variabel.

Perintah terakhir menjalankan urutan operasi dengan menggunakan cmdlet ini:

- **New-AzureHDInsightClusterConfig** untuk membuat konfigurasi kluster HDInsight.
- **Set-AzureHDInsightDefaultStorage** untuk mengatur akun penyimpanan default agar konfigurasi MyBlobStorage.blob.core.windows.net.
- **Add-AzureHDInsightStorage** untuk menambahkan akun penyimpanan kedua MySecondBlobStorage.blob.core.windows.net ke konfigurasi.
- **Tambahkan-AzureHDInsightMetastore** untuk menambahkan metastore untuk Oozie dan metastore untuk Hive pada konfigurasi.
- **New-AzureHDInsightCluster** untuk membuat kluster HDInsight dengan konfigurasi baru.

## PARAMETERS

### -ClusterSizeInNodes
Menentukan jumlah node data yang akan dibuat untuk kluster.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: Nodes, Size

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ClusterType
Menentukan tipe kluster yang akan dibuat.

```yaml
Type: ClusterType
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DataNodeVMSize
Menentukan ukuran mesin virtual untuk simpul data.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HeadNodeVMSize
Menentukan ukuran mesin virtual node kepala untuk kluster.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profil
Menentukan profil Azure yang akan dibaca cmdlet ini.
Jika Anda tidak menentukan profil, cmdlet ini akan membaca dari profil default lokal.

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

### -SubnetName
Menentukan nama subnet.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualNetworkId
Menentukan ID jaringan virtual untuk penyediaan kluster.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Penjaga BinatangNodeVMSize
Menentukan ukuran mesin virtual untuk simpul Penjaga Kebun Binatang untuk kluster HBase atau Storm.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Add-AzureHDInsightMetastore](./Add-AzureHDInsightMetastore.md)

[Add-AzureHDInsightStorage](./Add-AzureHDInsightStorage.md)

[New-AzureHDInsightCluster](./New-AzureHDInsightCluster.md)

[Set-AzureHDInsightDefaultStorage](./Set-AzureHDInsightDefaultStorage.md)


