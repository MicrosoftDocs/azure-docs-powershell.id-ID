---
Module Name: Az.HDInsight
Module Guid: 3fd1475f-cb23-4ffb-bf08-33d94b7d1acb
Download Help Link: https://docs.microsoft.com/powershell/module/az.hdinsight
Help Version: 4.1.2.0
Locale: en-US
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/HDInsight/HDInsight/help/Az.HDInsight.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/HDInsight/HDInsight/help/Az.HDInsight.md
ms.openlocfilehash: 72b6a535f5bfc41f1837c90f6d96a669bd708e88
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138284412"
---
# Az.HDInsight Module
## Deskripsi
Topik dalam dokumen bagian ini adalah cmdlet Azure PowerShell untuk Microsoft Azure HDInsight dalam kerangka kerja Azure Resource Manager (ARM). Cmdlet ini digunakan untuk mengelola kluster HDInsight serta pekerjaan yang dijalankan di dalamnya. Cmdlet ada di ruang nama Microsoft.Azure.Commands.HDInsight.

## Cmdlet Az.HDInsight
### [Add-AzHDInsightClusterIdentity](Add-AzHDInsightClusterIdentity.md)
Menambahkan identitas kluster ke objek konfigurasi kluster.

### [Add-AzHDInsightComponentVersion](Add-AzHDInsightComponentVersion.md)
Menambahkan versi untuk layanan yang berjalan dalam kluster ke objek konfigurasi kluster.

### [Add-AzHDInsightConfigValue](Add-AzHDInsightConfigValue.md)
Menambahkan kustomisasi nilai konfigurasi Hadoop dan/atau kustomisasi pustaka bersama Hive ke objek konfigurasi kluster.

### [Add-AzHDInsightMetastore](Add-AzHDInsightMetastore.md)
Menambahkan SQL Database berfungsi sebagai metastore Hive atau Oozie ke objek konfigurasi kluster.

### [Add-AzHDInsightScriptAction](Add-AzHDInsightScriptAction.md)
Menambahkan tindakan skrip ke objek konfigurasi kluster.

### [Add-AzHDInsightSecurityProfile](Add-AzHDInsightSecurityProfile.md)
Menambahkan profil keamanan ke objek konfigurasi kluster.

### [Add-AzHDInsightStorage](Add-AzHDInsightStorage.md)
Menambahkan kunci Azure Storage ke objek konfigurasi kluster.

### [Disable-AzHDInsightAzureMonitor](Disable-AzHDInsightAzureMonitor.md)
Menonaktifkan Azure Monitor dalam kluster HDInsight yang ditentukan.

### [Disable-AzHDInsightMonitoring](Disable-AzHDInsightMonitoring.md)
Menonaktifkan integrasi log Monitor Azure Klasik pada kluster HDInsight dan log yang relevan akan berhenti mengalir ke ruang kerja pemantauan yang ditentukan selama diaktifkan.

### [Enable-AzHDInsightAzureMonitor](Enable-AzHDInsightAzureMonitor.md)
Mengaktifkan Azure Monitor dalam kluster HDInsight yang ditentukan.

### [Enable-AzHDInsightMonitoring](Enable-AzHDInsightMonitoring.md)
Mengaktifkan integrasi log Monitor Azure Klasik pada kluster HDInsight dan log yang relevan akan dikirim ke ruang kerja pemantauan yang ditentukan selama diaktifkan.

### [Get-AzHDInsightAzureMonitor](Get-AzHDInsightAzureMonitor.md)
Mendapatkan status monitor Azure dari kluster HDInsight yang ditentukan.

### [Get-AzHDInsightCluster](Get-AzHDInsightCluster.md)
Mendapatkan dan mencantumkan semua kluster Azure HDInsight yang terkait dengan langganan saat ini atau grup sumber daya yang ditentukan, atau mengambil kluster tertentu.

### [Get-AzHDInsightClusterAutoscaleConfiguration](Get-AzHDInsightClusterAutoscaleConfiguration.md)
Mendapatkan konfigurasi skala otomatis dari kluster HDInsight.

### [Get-AzHDInsightHost](Get-AzHDInsightHost.md)
Mencantumkan host kluster HDInsight.

### [Get-AzHDInsightJob](Get-AzHDInsightJob.md)
Mendapatkan daftar pekerjaan dari kluster dan mencantumkannya dalam urutan kronologis terbalik, atau mengambil pekerjaan tertentu.

### [Get-AzHDInsightJobOutput](Get-AzHDInsightJobOutput.md)
Mendapatkan output log untuk pekerjaan dari akun penyimpanan yang terkait dengan kluster tertentu.

### [Get-AzHDInsightMonitoring](Get-AzHDInsightMonitoring.md)
Mendapatkan status integrasi log Azure Monitor Klasik di kluster HDInsight.

### [Get-AzHDInsightPersistedScriptAction](Get-AzHDInsightPersistedScriptAction.md)
Mendapatkan tindakan skrip yang tetap untuk kluster dan mencantumkannya dalam urutan kronologis, atau mendapatkan detail untuk tindakan skrip yang sudah ditentukan.

### [Get-AzHDInsightProperty](Get-AzHDInsightProperty.md)
Mendapatkan properti tentang layanan HDInsight, seperti lokasi dan kapasitas yang tersedia.

### [Get-AzHDInsightScriptActionHistory](Get-AzHDInsightScriptActionHistory.md)
Mendapatkan riwayat tindakan skrip untuk kluster dan mencantumkannya dalam urutan kronologis terbalik, atau mendapatkan detail tindakan skrip yang dijalankan sebelumnya.

### [Invoke-AzHDInsightHiveJob](Invoke-AzHDInsightHiveJob.md)
Mengirimkan kueri Hive ke kluster HDInsight dan mengambil hasil kueri dalam satu operasi.

### [New-AzHDInsightCluster](New-AzHDInsightCluster.md)
Membuat kluster Azure HDInsight dalam grup sumber daya yang ditentukan untuk langganan saat ini.

### [New-AzHDInsightClusterAutoscaleConfiguration](New-AzHDInsightClusterAutoscaleConfiguration.md)
Membuat objek yang tidak tetap yang menjelaskan konfigurasi skala otomatis kluster Azure HDInsight.

### [New-AzHDInsightClusterAutoscaleScheduleCondition](New-AzHDInsightClusterAutoscaleScheduleCondition.md)
Membuat kondisi skala otomatis berbasis Jadwal.

### [New-AzHDInsightClusterConfig](New-AzHDInsightClusterConfig.md)
Membuat objek konfigurasi kluster yang tidak tetap yang menjelaskan konfigurasi kluster Azure HDInsight.

### [New-AzHDInsightHiveJobDefinition](New-AzHDInsightHiveJobDefinition.md)
Membuat objek pekerjaan Hive.

### [New-AzHDInsightIPConfiguration](New-AzHDInsightIPConfiguration.md)
Membuat konfigurasi IP dari konfigurasi tautan privat.

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
Menghapus kluster HDInsight tertentu dari langganan saat ini.

### [Remove-AzHDInsightClusterAutoscaleConfiguration](Remove-AzHDInsightClusterAutoscaleConfiguration.md)
Menghapus konfigurasi skala otomatis kluster HDInsight.

### [Remove-AzHDInsightPersistedScriptAction](Remove-AzHDInsightPersistedScriptAction.md)
Menghapus tindakan skrip yang tetap dari kluster HDInsight.

### [Restart-AzHDInsightHost](Restart-AzHDInsightHost.md)
Memulai ulang host kluster HDInsight tertentu.

### [Set-AzHDInsightClusterAutoscaleConfiguration](Set-AzHDInsightClusterAutoscaleConfiguration.md)
Mengatur konfigurasi skala otomatis kluster Azure HDInsight.

### [Set-AzHDInsightClusterDiskEncryptionKey](Set-AzHDInsightClusterDiskEncryptionKey.md)
Memutar kunci enkripsi disk dari kluster HDInsight yang ditentukan.

### [Set-AzHDInsightClusterSize](Set-AzHDInsightClusterSize.md)
Mengatur jumlah node Pekerja dalam kluster yang ditentukan.

### [Set-AzHDInsightDefaultStorage](Set-AzHDInsightDefaultStorage.md)
Mengatur pengaturan akun Storage default dalam objek konfigurasi kluster.

### [Set-AzHDInsightGatewayCredential](Set-AzHDInsightGatewayCredential.md)
Mengatur kredensial HTTP gateway dari kluster Azure HDInsight.

### [Set-AzHDInsightPersistedScriptAction](Set-AzHDInsightPersistedScriptAction.md)
Mengatur tindakan skrip yang dijalankan sebelumnya untuk menjadi tindakan skrip yang tetap.

### [Start-AzHDInsightJob](Start-AzHDInsightJob.md)
Memulai pekerjaan Azure HDInsight yang ditentukan pada kluster tertentu.

### [Stop-AzHDInsightJob](Stop-AzHDInsightJob.md)
Menghentikan pekerjaan berjalan tertentu pada kluster.

### [Submit-AzHDInsightScriptAction](Submit-AzHDInsightScriptAction.md)
Mengirimkan tindakan skrip baru ke kluster Azure HDInsight.

### [Use-AzHDInsightCluster](Use-AzHDInsightCluster.md)
Memilih kluster yang akan digunakan dengan cmdlet Invoke-RmAzureHDInsightHiveJob.

### [Wait-AzHDInsightJob](Wait-AzHDInsightJob.md)
Menunggu penyelesaian atau kegagalan pekerjaan tertentu.

