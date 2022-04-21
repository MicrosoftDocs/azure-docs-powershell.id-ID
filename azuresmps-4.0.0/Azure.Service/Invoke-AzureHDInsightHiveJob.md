---
external help file: Microsoft.WindowsAzure.Commands.HDInsight.dll-Help.xml
ms.assetid: BB01591D-4E1A-4C89-8B2A-5A242C29B125
online version: ''
schema: 2.0.0
ms.openlocfilehash: 42075f3ada389249e885ea7e061e92eabcbfe795
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142656064"
---
# Invoke-AzureHDInsightHiveJob

## SYNOPSIS
Mengirimkan kueri Sarang ke klaster HDInsight, memperlihatkan kemajuan eksekusi kueri, dan mendapatkan hasil kueri dalam satu operasi.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Invoke-AzureHDInsightHiveJob [-Arguments <String[]>] [-Defines <Hashtable>] [-File <String>]
 [-Files <String[]>] [-JobName <String>] [-Query <String>] [-RunAsFileJob] [-StatusFolder <String>]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Versi Azure PowerShell HDInsight ini sudah tidak digunakan lagi.
Cmdlet ini akan dihapus pada 1 Januari 2017.
Silakan gunakan versi Azure PowerShell HDInsight yang lebih baru.

Untuk informasi tentang cara menggunakan HDInsight baru untuk membuat klaster, lihat [Membuat kluster berbasis Linux dalam HDInsight menggunakan Azure PowerShell](https://azure.microsoft.com/en-us/documentation/articles/hdinsight-hadoop-create-linux-clusters-azure-powershell/) (https://azure.microsoft.com/en-us/documentation/articles/hdinsight-hadoop-create-linux-clusters-azure-powershell/).
Untuk informasi tentang cara mengirimkan pekerjaan dengan menggunakan Azure PowerShell dan pendekatan lain, lihat [Mengirimkan pekerjaan Hadoop di HDInsight](https://azure.microsoft.com/en-us/documentation/articles/hdinsight-submit-hadoop-jobs-programmatically/) (https://azure.microsoft.com/en-us/documentation/articles/hdinsight-submit-hadoop-jobs-programmatically/).
Untuk informasi referensi tentang Azure PowerShell HDInsight, lihat [Cmdlet Azure HDInsight](/powershell/module/servicemanagement/azure.service/?view=azuresmps-4.0.0#hd-insights).

Cmdlet **Invoke-AzureHDInsightHiveJob** mengirimkan kueri Hive ke kluster HDInsight, menampilkan kemajuan eksekusi kueri, dan mendapatkan hasil kueri dalam satu operasi.
Anda harus menjalankan cmdlet Use-AzureHDInsightCluster sebelum menjalankan **Invoke-AzureHDInsightHiveJob** untuk menentukan kluster HDInsight yang akan dikirimkan kueri.

## EXAMPLES

### Contoh 1: Mengirim kueri Sarang
```
PS C:\>Use-AzureHDInsightCluster "Cluster01" -Subscription (Get-AzureSubscription -Current).SubscriptionId
PS C:\> Invoke-AzureHDInsightHiveJob "select * from hivesampletable limit 10"
```

Perintah pertama menggunakan cmdlet **Use-AzureHDInsightCluster** untuk menentukan kluster dalam langganan saat ini yang akan digunakan untuk kueri Hive.

Perintah kedua menggunakan cmdlet **Invoke-AzureHDInsightHiveJob** untuk mengirimkan kueri Hive.

## PARAMETERS

### -Argumen
Menentukan array argumen untuk pekerjaan Hadoop.
Argumen dikirim sebagai argumen baris perintah ke setiap tugas.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Defines
Menentukan nilai konfigurasi Hadoop untuk diatur ketika pekerjaan berjalan.

```yaml
Type: Hashtable
Parameter Sets: (All)
Aliases: Params

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -File
Menentukan jalur Windows Azure Storage Blob (WASB) ke file di penyimpanan blob Azure yang berisi kueri untuk dijalankan.
Anda bisa menggunakan parameter ini dan bukan parameter *Kueri* .

```yaml
Type: String
Parameter Sets: (All)
Aliases: QueryFile

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Files
Menentukan kumpulan file yang diperlukan untuk pekerjaan Sarang.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobName
Menentukan nama pekerjaan Sarang.
Jika Anda tidak menentukan parameter ini, cmdlet ini menggunakan nilai default: "Sarang: \<first 100 characters of Query\>".

```yaml
Type: String
Parameter Sets: (All)
Aliases: Name

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

### -Query
Menentukan kueri Sarang.

```yaml
Type: String
Parameter Sets: (All)
Aliases: QueryText

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunAsFileJob
Menunjukkan bahwa cmdlet ini membuat file di akun penyimpanan Azure default untuk menyimpan kueri.
Cmdlet ini mengirimkan pekerjaan yang mereferensikan file ini sebagai skrip untuk dijalankan.

Anda dapat menggunakan fungsi ini untuk menangani karakter khusus seperti tanda persen (%) yang akan gagal pada pengiriman pekerjaan melalui Templeton, karena Templeton menginterpretasikan kueri dengan tanda persen sebagai parameter URL.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StatusFolder
Menentukan lokasi folder yang berisi output standar dan output kesalahan untuk suatu pekerjaan, termasuk kode keluar dan log tugasnya.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Baru-AzureHDInsightHiveJobDefinition](./New-AzureHDInsightHiveJobDefinition.md)

[Use-AzureHDInsightCluster](./Use-AzureHDInsightCluster.md)


