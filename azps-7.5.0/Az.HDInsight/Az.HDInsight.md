---
Module Name: Az.HDInsight
Module Guid: 3fd1475f-cb23-4ffb-bf08-33d94b7d1acb
Download Help Link: https://docs.microsoft.com/powershell/module/az.hdinsight
Help Version: 4.1.2.0
Locale: en-US
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/HDInsight/HDInsight/help/Az.HDInsight.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/HDInsight/HDInsight/help/Az.HDInsight.md
ms.openlocfilehash: 72b6a535f5bfc41f1837c90f6d96a669bd708e88
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144212543"
---
# Modul Az.HDInsight
## Deskripsi
Topik di bagian ini men dokumentasikan cmdlet Azure PowerShell untuk Microsoft Azure HDInsight dalam kerangka kerja Azure Resource Manager (ARM). Cmdlet ini digunakan untuk mengelola kluster HDInsight dan pekerjaan yang berjalan di atasnya. Cmdlet ada di namespace Microsoft.Azure.Commands.HDInsight.

## Cmdlet Az.HDInsight
### [Add-AzHDInsightClusterIdentity](Add-AzHDInsightClusterIdentity.md)
Menambahkan identitas kluster ke objek konfigurasi kluster.

### [Add-AzHDInsightComponentVersion](Add-AzHDInsightComponentVersion.md)
Menambahkan versi untuk layanan yang berjalan dalam kluster ke objek konfigurasi kluster.

### [Add-AzHDInsightConfigValue](Add-AzHDInsightConfigValue.md)
Menambahkan kustomisasi nilai konfigurasi Hadoop dan/atau kustomisasi pustaka bersama Apache Hive ke objek konfigurasi kluster.

### [Add-AzHDInsightMetastore](Add-AzHDInsightMetastore.md)
Menambahkan SQL Database untuk berfungsi sebagai metastore Apache Hive atau Oozie ke objek konfigurasi kluster.

### [Add-AzHDInsightScriptAction](Add-AzHDInsightScriptAction.md)
Menambahkan tindakan skrip ke objek konfigurasi kluster.

### [Add-AzHDInsightSecurityProfile](Add-AzHDInsightSecurityProfile.md)
Menambahkan profil keamanan ke objek konfigurasi kluster.

### [Add-AzHDInsightStorage](Add-AzHDInsightStorage.md)
Menambahkan kunci Azure Storage ke objek konfigurasi kluster.

### [Disable-AzHDInsightAzureMonitor](Disable-AzHDInsightAzureMonitor.md)
Menonaktifkan Azure Monitor dalam kluster HDInsight tertentu.

### [Disable-AzHDInsightMonitoring](Disable-AzHDInsightMonitoring.md)
Menonaktifkan integrasi log Azure Monitor Klasik pada kluster HDInsight dan log yang relevan akan berhenti mengalir ke ruang kerja pemantauan yang ditentukan selama pengaktifan.

### [Enable-AzHDInsightAzureMonitor](Enable-AzHDInsightAzureMonitor.md)
Mengaktifkan Azure Monitor dalam kluster HDInsight tertentu.

### [Enable-AzHDInsightMonitoring](Enable-AzHDInsightMonitoring.md)
Mengaktifkan integrasi log Azure Monitor Klasik pada kluster HDInsight dan log yang relevan akan dikirim ke ruang kerja pemantauan yang ditentukan selama pengaktifan.

### [Get-AzHDInsightAzureMonitor](Get-AzHDInsightAzureMonitor.md)
Mendapatkan status azure monitor dari kluster HDInsight tertentu.

### [Get-AzHDInsightCluster](Get-AzHDInsightCluster.md)
Mendapatkan dan mencantumkan semua kluster Azure HDInsight yang terkait dengan langganan saat ini atau grup sumber daya tertentu, atau mengambil kluster tertentu.

### [Get-AzHDInsightClusterAutoscaleConfiguration](Get-AzHDInsightClusterAutoscaleConfiguration.md)
Mendapatkan konfigurasi skala otomatis kluster HDInsight.

### [Get-AzHDInsightHost](Get-AzHDInsightHost.md)
Mencantumkan host kluster HDInsight.

### [Get-AzHDInsightJob](Get-AzHDInsightJob.md)
Mendapatkan daftar pekerjaan dari kluster dan mencantumkannya dalam urutan kronologis terbalik, atau mengambil pekerjaan tertentu.

### [Get-AzHDInsightJobOutput](Get-AzHDInsightJobOutput.md)
Mendapatkan output log untuk pekerjaan dari akun penyimpanan yang terkait dengan kluster tertentu.

### [Get-AzHDInsightMonitoring](Get-AzHDInsightMonitoring.md)
Mendapatkan status integrasi log Azure Monitor Klasik pada kluster HDInsight.

### [Get-AzHDInsightPersistedScriptAction](Get-AzHDInsightPersistedScriptAction.md)
Mendapatkan tindakan skrip yang bertahan untuk kluster dan mencantumkannya dalam urutan kronologis, atau mendapatkan detail untuk tindakan skrip yang bertahan tertentu.

### [Get-AzHDInsightProperty](Get-AzHDInsightProperty.md)
Mendapatkan properti tentang layanan HDInsight, seperti lokasi dan kapasitas yang tersedia.

### [Get-AzHDInsightScriptActionHistory](Get-AzHDInsightScriptActionHistory.md)
Mendapatkan riwayat tindakan skrip untuk kluster dan mencantumkannya dalam urutan kronologis terbalik, atau mendapatkan detail tindakan skrip yang dijalankan sebelumnya.

### [Invoke-AzHDInsightHiveJob](Invoke-AzHDInsightHiveJob.md)
Mengirimkan kueri Apache Hive ke kluster HDInsight dan mengambil hasil kueri dalam satu operasi.

### [New-AzHDInsightCluster](New-AzHDInsightCluster.md)
Membuat kluster Azure HDInsight di grup sumber daya yang ditentukan untuk langganan saat ini.

### [New-AzHDInsightClusterAutoscaleConfiguration](New-AzHDInsightClusterAutoscaleConfiguration.md)
Membuat objek yang tidak bertahan yang menjelaskan konfigurasi skala otomatis kluster Azure HDInsight.

### [New-AzHDInsightClusterAutoscaleScheduleCondition](New-AzHDInsightClusterAutoscaleScheduleCondition.md)
Membuat kondisi skala otomatis berbasis Jadwal.

### [New-AzHDInsightClusterConfig](New-AzHDInsightClusterConfig.md)
Membuat objek konfigurasi kluster yang tidak bertahan yang menjelaskan konfigurasi kluster Azure HDInsight.

### [New-AzHDInsightHiveJobDefinition](New-AzHDInsightHiveJobDefinition.md)
Membuat objek pekerjaan Apache Hive.

### [New-AzHDInsightIPConfiguration](New-AzHDInsightIPConfiguration.md)
Membuat konfigurasi IP konfigurasi tautan privat.

### [New-AzHDInsightMapReduceJobDefinition](New-AzHDInsightMapReduceJobDefinition.md)
Membuat objek pekerjaan MapReduce.

### [New-AzHDInsightPigJobDefinition](New-AzHDInsightPigJobDefinition.md)
Membuat objek pekerjaan Pig.

### [New-AzHDInsightPrivateLinkConfiguration](New-AzHDInsightPrivateLinkConfiguration.md)
Membuat konfigurasi tautan privat dari kluster HDInsight.

### [New-AzHDInsightSqoopJobDefinition](New-AzHDInsightSqoopJobDefinition.md)
Membuat objek pekerjaan Sqoop.

### [New-AzHDInsightStreamingMapReduceJobDefinition](New-AzHDInsightStreamingMapReduceJobDefinition.md)
Membuat objek pekerjaan Streaming MapReduce.

### [Remove-AzHDInsightCluster](Remove-AzHDInsightCluster.md)
Menghapus kluster HDInsight yang ditentukan dari langganan saat ini.

### [Remove-AzHDInsightClusterAutoscaleConfiguration](Remove-AzHDInsightClusterAutoscaleConfiguration.md)
Menghapus konfigurasi skala otomatis kluster HDInsight.

### [Remove-AzHDInsightPersistedScriptAction](Remove-AzHDInsightPersistedScriptAction.md)
Menghapus tindakan skrip yang bertahan dari kluster HDInsight.

### [Restart-AzHDInsightHost](Restart-AzHDInsightHost.md)
Menghidupkan ulang host tertentu dari kluster HDInsight.

### [Set-AzHDInsightClusterAutoscaleConfiguration](Set-AzHDInsightClusterAutoscaleConfiguration.md)
Mengatur konfigurasi skala otomatis kluster Azure HDInsight.

### [Set-AzHDInsightClusterDiskEncryptionKey](Set-AzHDInsightClusterDiskEncryptionKey.md)
Memutar kunci enkripsi disk dari kluster HDInsight yang ditentukan.

### [Set-AzHDInsightClusterSize](Set-AzHDInsightClusterSize.md)
Mengatur jumlah simpul Pekerja dalam kluster tertentu.

### [Set-AzHDInsightDefaultStorage](Set-AzHDInsightDefaultStorage.md)
Mengatur pengaturan akun Storage default dalam objek konfigurasi kluster.

### [Set-AzHDInsightGatewayCredential](Set-AzHDInsightGatewayCredential.md)
Mengatur kredensial HTTP gateway dari kluster Azure HDInsight.

### [Set-AzHDInsightPersistedScriptAction](Set-AzHDInsightPersistedScriptAction.md)
Mengatur tindakan skrip yang dijalankan sebelumnya menjadi tindakan skrip yang bertahan.

### [Start-AzHDInsightJob](Start-AzHDInsightJob.md)
Memulai pekerjaan Azure HDInsight yang ditentukan pada kluster tertentu.

### [Stop-AzHDInsightJob](Stop-AzHDInsightJob.md)
Menghentikan pekerjaan yang berjalan tertentu pada kluster.

### [Submit-AzHDInsightScriptAction](Submit-AzHDInsightScriptAction.md)
Mengirimkan tindakan skrip baru ke kluster Azure HDInsight.

### [Use-AzHDInsightCluster](Use-AzHDInsightCluster.md)
Memilih kluster yang akan digunakan dengan cmdlet Invoke-RmAzureHDInsightHiveJob.

### [Wait-AzHDInsightJob](Wait-AzHDInsightJob.md)
Menunggu penyelesaian atau kegagalan pekerjaan yang ditentukan.

