---
external help file: Microsoft.WindowsAzure.Commands.HDInsight.dll-Help.xml
ms.assetid: 600D35F8-1E3C-4724-9F5E-75CF754F424F
online version: ''
schema: 2.0.0
ms.openlocfilehash: fb81a0c4fa38cdfa5214aa12e4a01e69ecef8ed7
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142982124"
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
Versi Azure PowerShell HDInsight ini sudah tidak digunakan lagi.
Cmdlet ini akan dihapus pada 1 Januari 2017.
Silakan gunakan versi Azure PowerShell HDInsight yang lebih baru.

Untuk informasi tentang cara menggunakan HDInsight baru untuk membuat klaster, lihat [Membuat kluster berbasis Linux dalam HDInsight menggunakan Azure PowerShell](https://azure.microsoft.com/en-us/documentation/articles/hdinsight-hadoop-create-linux-clusters-azure-powershell/) (https://azure.microsoft.com/en-us/documentation/articles/hdinsight-hadoop-create-linux-clusters-azure-powershell/).
Untuk informasi tentang cara mengirimkan pekerjaan dengan menggunakan Azure PowerShell dan pendekatan lain, lihat [Mengirimkan pekerjaan Hadoop di HDInsight](https://azure.microsoft.com/en-us/documentation/articles/hdinsight-submit-hadoop-jobs-programmatically/) (https://azure.microsoft.com/en-us/documentation/articles/hdinsight-submit-hadoop-jobs-programmatically/).
Untuk informasi referensi tentang Azure PowerShell HDInsight, lihat [Cmdlet Azure HDInsight](/powershell/module/servicemanagement/azure.service/?view=azuresmps-4.0.0#hd-insights).

Cmdlet **Add-AzureHDInsightScriptAction** menyediakan fungsi Azure HDInsight yang digunakan untuk menginstal perangkat lunak tambahan atau untuk mengubah konfigurasi aplikasi yang berjalan di kluster Hadoop dengan menggunakan skrip Windows PowerShell.

Tindakan skrip berjalan pada simpul kluster saat kluster HDInsight digunakan, dan dijalankan setelah node di kluster selesai konfigurasi HDInsight.
Tindakan skrip berjalan di bawah hak istimewa akun administrator sistem dan menyediakan hak akses penuh ke node kluster.
Anda dapat menyediakan daftar tindakan skrip kepada setiap kluster untuk dijalankan dalam urutan yang ditentukan.

## EXAMPLES

### Contoh 1: Menambahkan tindakan skrip ke kluster
```
PS C:\>$Config = New-AzureHDInsightClusterConfig -ClusterSizeInNodes 4
PS C:\> $Config = Add-AzureHDInsightScriptAction -Config $Config -Name "TestScriptAction" -Uri http://test.com/test.ps1 -Parameters "test" -ClusterRoleCollection HeadNode,DataNode
PS C:\> New-AzureHDInsightCluster -Config $Config
```

Perintah pertama menggunakan cmdlet **New-AzureHDInsightClusterConfig** untuk membuat konfigurasi kluster HDInsight, lalu menyimpannya dalam variabel $Config.

Perintah kedua menggunakan cmdlet **Add-AzureHDInsightScriptAction** untuk menambahkan tindakan skrip bernama TestScriptAction ke $Config.

Perintah terakhir menggunakan cmdlet **New-AzureHDInsightCluster** untuk membuat kluster HDInsight baru yang menjalankan tindakan skrip yang disimpan di $Config.

### Contoh 2: Menambahkan beberapa tindakan skrip ke kluster
```
PS C:\>$Config = New-AzureHDInsightClusterConfig -ClusterSizeInNodes 4
PS C:\> $Config = Add-AzureHDInsightScriptAction -Config $Config -Name "TestScriptAction1" -Uri http://test.com/test1.ps1 -Parameters "Test1" -ClusterRoleCollection HeadNode,DataNode | Add-AzureHDInsightScriptAction -Config $Config -Name "TestScriptAction2" -Uri http://test.com/test2.ps1 -ClusterRoleCollection HeadNode
PS C:\> New-AzureHDInsightCluster -Config $Config
```

Perintah pertama menggunakan cmdlet **New-AzureHDInsightClusterConfig** untuk membuat konfigurasi kluster HDInsight, lalu menyimpannya dalam variabel $Config.

Perintah kedua menggunakan cmdlet **Add-AzureHDInsightScriptAction** untuk menambahkan tindakan skrip tertentu ke $Config, lalu menggunakan operator saluran untuk mengirimkan $Config ke **Add-AzureHDInsightScriptAction** untuk kedua kalinya menambahkan tindakan skrip kedua ke $Config.

Perintah terakhir menggunakan cmdlet **New-AzureHDInsightCluster** untuk membuat kluster yang menjalankan tindakan skrip dalam $Config.

## PARAMETERS

### -ClusterRoleCollection
Menentukan node untuk menjalankan skrip.
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

### -Parameters
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[AzureHDInsightCluster baru](./New-AzureHDInsightCluster.md)

[Baru-AzureHDInsightClusterConfig](./New-AzureHDInsightClusterConfig.md)


