---
external help file: Microsoft.WindowsAzure.Commands.HDInsight.dll-Help.xml
ms.assetid: 600D35F8-1E3C-4724-9F5E-75CF754F424F
online version: ''
schema: 2.0.0
ms.openlocfilehash: 67bdbe205f70667fb479e31b577e8853041d806d372c3904ef59d8781da9f493
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132415225"
---
# Add-AzureHDInsightScriptAction

## SYNOPSIS
Menambahkan tindakan skrip HDInsight.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Add-AzureHDInsightScriptAction -Config <AzureHDInsightConfig> -Name <String>
 -ClusterRoleCollection <ClusterNodeType[]> -Uri <Uri> [-Parameters <String>] [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
Versi Azure PowerShell HDInsight ini sudah tidak berlaku.
Cmdlets ini akan dihapus pada 1 Januari 2017.
Silakan gunakan versi yang lebih baru Azure PowerShell HDInsight.

Untuk informasi tentang cara menggunakan HDInsight yang baru untuk membuat kluster, lihat Membuat kluster berbasis Linux di [HDInsight menggunakan Azure PowerShell](https://azure.microsoft.com/en-us/documentation/articles/hdinsight-hadoop-create-linux-clusters-azure-powershell/) ( https://azure.microsoft.com/en-us/documentation/articles/hdinsight-hadoop-create-linux-clusters-azure-powershell/) .
Untuk informasi tentang cara mengirimkan pekerjaan menggunakan Azure PowerShell dan pendekatan lain, lihat Mengirimkan pekerjaan Hadoop di [HDInsight](https://azure.microsoft.com/en-us/documentation/articles/hdinsight-submit-hadoop-jobs-programmatically/) ( https://azure.microsoft.com/en-us/documentation/articles/hdinsight-submit-hadoop-jobs-programmatically/) .
Untuk informasi referensi tentang Azure PowerShell HDInsight, [lihat Cmdlet Azure HDInsight](/powershell/module/servicemanagement/azure.service/?view=azuresmps-4.0.0#hd-insights).

Cmdlet **Add-AzureHDInsightScriptAction** menyediakan fungsionalitas Azure HDInsight yang digunakan untuk menginstal perangkat lunak tambahan atau untuk mengubah konfigurasi aplikasi yang berjalan pada kluster Hadoop menggunakan skrip Windows PowerShell.

Tindakan skrip yang berjalan di node kluster ketika kluster HDInsight disebarkan, dan dijalankan setelah simpul di kluster menyelesaikan konfigurasi HDInsight.
Tindakan skrip dijalankan di bawah hak istimewa akun administrator sistem dan menyediakan hak akses penuh ke node kluster.
Anda dapat menyediakan daftar tindakan skrip untuk setiap kluster untuk dijalankan dalam urutan yang ditentukan.

## EXAMPLES

### Contoh 1: Menambahkan tindakan skrip ke kluster
```
PS C:\>$Config = New-AzureHDInsightClusterConfig -ClusterSizeInNodes 4
PS C:\> $Config = Add-AzureHDInsightScriptAction -Config $Config -Name "TestScriptAction" -Uri http://test.com/test.ps1 -Parameters "test" -ClusterRoleCollection HeadNode,DataNode
PS C:\> New-AzureHDInsightCluster -Config $Config
```

Perintah pertama menggunakan cmdlet **New-AzureHDInsightClusterConfig** untuk membuat konfigurasi kluster HDInsight, lalu menyimpannya di $Config lokal.

Perintah kedua menggunakan cmdlet **Add-AzureHDInsightScriptAction** untuk menambahkan tindakan skrip bernama TestScriptAction ke $Config.

Perintah terakhir menggunakan cmdlet **New-AzureHDInsightCluster** untuk membuat kluster HDInsight baru yang menjalankan tindakan skrip yang disimpan di $Config.

### Contoh 2: Menambahkan beberapa tindakan skrip ke kluster
```
PS C:\>$Config = New-AzureHDInsightClusterConfig -ClusterSizeInNodes 4
PS C:\> $Config = Add-AzureHDInsightScriptAction -Config $Config -Name "TestScriptAction1" -Uri http://test.com/test1.ps1 -Parameters "Test1" -ClusterRoleCollection HeadNode,DataNode | Add-AzureHDInsightScriptAction -Config $Config -Name "TestScriptAction2" -Uri http://test.com/test2.ps1 -ClusterRoleCollection HeadNode
PS C:\> New-AzureHDInsightCluster -Config $Config
```

Perintah pertama menggunakan cmdlet **New-AzureHDInsightClusterConfig** untuk membuat konfigurasi kluster HDInsight, lalu menyimpannya di $Config lokal.

Perintah kedua menggunakan cmdlet **Add-AzureHDInsightScriptAction** untuk menambahkan tindakan skrip tertentu ke $Config, lalu menggunakan operator pipeline untuk menyampaikan $Config ke **Add-AzureHDInsightScriptAction** untuk kedua kalinya untuk menambahkan tindakan skrip kedua ke $Config.

Perintah terakhir menggunakan cmdlet **New-AzureHDInsightCluster** untuk membuat kluster yang menjalankan tindakan skrip dalam $Config.

## PARAMETERS

### -ClusterRoleCollection
Menentukan node tempat untuk menjalankan skrip.
Nilai yang dapat diterima untuk parameter ini adalah: HeadNode atau DataNode.

Anda bisa menentukan satu nilai atau kedua nilai.

```yaml
Type: ClusterNodeType[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Config
Menentukan objek konfigurasi.
Cmdlet ini menambahkan informasi tindakan skrip ke objek yang ditentukan parameter ini.

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

### -Nama
Menentukan nama tindakan skrip.

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

### -Parameter
Menentukan parameter yang diperlukan oleh tindakan skrip.

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

### -Uri
Menentukan lokasi URI dari skrip untuk dijalankan.

```yaml
Type: Uri
Parameter Sets: (All)
Aliases:

Required: True
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

[New-AzureHDInsightCluster](./New-AzureHDInsightCluster.md)

[New-AzureHDInsightClusterConfig](./New-AzureHDInsightClusterConfig.md)


