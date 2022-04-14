---
Module Name: AzureRM.HDInsight
Module Guid: 3fd1475f-cb23-4ffb-bf08-33d94b7d1acb
Download Help Link: https://docs.microsoft.com/en-us/powershell/module/azurerm.hdinsight
Help Version: 4.1.2.0
Locale: en-US
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/HDInsight/Commands.HDInsight/help/AzureRM.HDInsight.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/HDInsight/Commands.HDInsight/help/AzureRM.HDInsight.md
ms.openlocfilehash: bbbb418a8e101fa1b806bc910132f44e40158190
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "132418377"
---
# Modul AzureRM.HDInsight
## Deskripsi
Topik di bagian ini mendokumentasikan cmdlet Azure PowerShell untuk Microsoft Azure HDInsight dalam kerangka kerja Azure Resource Manager (ARM). Cmdlet ini digunakan untuk mengelola kluster HDInsight dan pekerjaan yang berjalan di dalamnya. Cmdlet ada di ruang nama Microsoft.Azure.Commands.HDInsight.

## Cmdlet AzureRM.HDInsight
### [Add-AzureRmHDInsightClusterIdentity](Add-AzureRmHDInsightClusterIdentity.md)
Menambahkan identitas kluster ke objek konfigurasi kluster.

### [Add-AzureRmHDInsightComponentVersion](Add-AzureRmHDInsightComponentVersion.md)
Menambahkan versi untuk layanan yang berjalan dalam kluster ke objek konfigurasi kluster.

### [Add-AzureRmHDInsightConfigValues](Add-AzureRmHDInsightConfigValues.md)
Menambahkan kustomisasi nilai konfigurasi Hadoop dan/atau kustomisasi pustaka bersama Hive ke objek konfigurasi kluster.

### [Add-AzureRmHDInsightMetastore](Add-AzureRmHDInsightMetastore.md)
Menambahkan SQL Database untuk berfungsi sebagai metastore Hive atau Oozie ke objek konfigurasi kluster.

### [Add-AzureRmHDInsightScriptAction](Add-AzureRmHDInsightScriptAction.md)
Menambahkan tindakan skrip ke objek konfigurasi kluster.

### [Add-AzureRmHDInsightSecurityProfile](Add-AzureRmHDInsightSecurityProfile.md)
Menambahkan profil keamanan ke objek konfigurasi kluster.

### [Add-AzureRmHDInstorage](Add-AzureRmHDInsightStorage.md)
Menambahkan kunci Azure Storage ke objek konfigurasi kluster.

### [Disable-AzureRmHDInsightOperationsManagementSuite](Disable-AzureRmHDInsightOperationsManagementSuite.md)
Menonaktifkan Operations Management Suite (OMS) dalam kluster HDInsight dan log yang relevan akan berhenti mengalir ke ruang kerja OMS yang ditentukan selama aktifkan.

### [Enable-AzureRmHDInsightOperationsManagementSuite](Enable-AzureRmHDInsightOperationsManagementSuite.md)
Mengaktifkan Operations Management Suite (OMS) dalam kluster HDInsight dan log yang relevan akan dikirim ke ruang kerja OMS yang ditentukan selama aktifkan.

### [Get-AzureRmHDInsightCluster](Get-AzureRmHDInsightCluster.md)
Mendapatkan dan mencantumkan semua kluster Azure HDInsight yang terkait dengan langganan saat ini atau grup sumber daya tertentu, atau mengambil klaster tertentu.

### [Get-AzureRmHDInsightJob](Get-AzureRmHDInsightJob.md)
Mendapatkan daftar pekerjaan dari kluster dan mencantumkannya dalam urutan kronologis terbalik, atau mengambil pekerjaan tertentu.

### [Get-AzureRmHDInsightJobOutput](Get-AzureRmHDInsightJobOutput.md)
Mendapatkan output log untuk pekerjaan dari akun penyimpanan yang terkait dengan kluster tertentu.

### [Get-AzureRmHDInsightOperationsManagementSuite](Get-AzureRmHDInsightOperationsManagementSuite.md)
Mendapatkan status penginstalan Operations Management Suite (OMS) di kluster.

### [Get-AzureRmHDInsightPersistedScriptAction](Get-AzureRmHDInsightPersistedScriptAction.md)
Mendapatkan tindakan skrip tetap untuk sebuah kluster dan mencantumkannya dalam urutan kronologis, atau mendapatkan detail untuk tindakan skrip tetap tertentu.

### [Get-AzureRmHDInsightProperties](Get-AzureRmHDInsightProperties.md)
Mendapatkan properti tentang layanan HDInsight, seperti lokasi dan kapasitas yang tersedia.

### [Get-AzureRmHDInsightScriptActionHistory](Get-AzureRmHDInsightScriptActionHistory.md)
Mendapatkan riwayat tindakan skrip untuk kluster dan mencantumkannya dalam urutan kronologis terbalik, atau mendapatkan detail tindakan skrip yang dijalankan sebelumnya.

### [Grant-AzureRmHDInsightHttpServicesAccess](Grant-AzureRmHDInsightHttpServicesAccess.md)
Memberikan akses HTTP ke kluster.

### [Grant-AzureRmHDInsightRdpServicesAccess](Grant-AzureRmHDInsightRdpServicesAccess.md)
Memberikan akses RDP ke klaster Windows.

### [Invoke-AzureRmHDInsightHiveJob](Invoke-AzureRmHDInsightHiveJob.md)
Mengirimkan kueri Sarang ke kluster HDInsight dan mengambil hasil kueri dalam satu operasi.

### [Baru-AzureRmHDInsightCluster](New-AzureRmHDInsightCluster.md)
Membuat kluster Azure HDInsight dalam grup sumber daya yang ditentukan untuk langganan saat ini.

### [Baru-AzureRmHDInsightClusterConfig](New-AzureRmHDInsightClusterConfig.md)
Membuat objek konfigurasi kluster yang tidak tetap yang menjelaskan konfigurasi kluster Azure HDInsight.

### [Baru-AzureRmHDInsightHiveJobDefinition](New-AzureRmHDInsightHiveJobDefinition.md)
Membuat objek pekerjaan Sarang.

### [Baru-AzureRmHDInsightMapReduceJobDefinition](New-AzureRmHDInsightMapReduceJobDefinition.md)
Membuat objek pekerjaan MapReduce.

### [Baru-AzureRmHDInsightPigJobDefinition](New-AzureRmHDInsightPigJobDefinition.md)
Membuat objek pekerjaan Babi.

### [Baru-AzureRmHDInsightSqoopJobDefinition](New-AzureRmHDInsightSqoopJobDefinition.md)
Membuat objek pekerjaan Sqoop.

### [New-AzureRmHDInsightStreamingMapReduceJobDefinition](New-AzureRmHDInsightStreamingMapReduceJobDefinition.md)
Membuat objek pekerjaan Streaming MapReduce.

### [Hapus-AzureRmHDInsightCluster](Remove-AzureRmHDInsightCluster.md)
Menghapus kluster HDInsight yang ditentukan dari langganan saat ini.

### [Remove-AzureRmHDInsightPersistedScriptAction](Remove-AzureRmHDInsightPersistedScriptAction.md)
Menghapus tindakan skrip tetap dari kluster HDInsight.

### [Mencabut-AzureRmHDInsightHttpServicesAccess](Revoke-AzureRmHDInsightHttpServicesAccess.md)
Menonaktifkan akses HTTP ke kluster.

### [Cabut-AzureRmHDInsightRdpServicesAccess](Revoke-AzureRmHDInsightRdpServicesAccess.md)
Menonaktifkan akses RDP ke klaster Windows.

### [Set-AzureRmHDInsightClusterSize](Set-AzureRmHDInsightClusterSize.md)
Mengatur jumlah node Pekerja dalam kluster yang ditentukan.

### [Set-AzureRmHDInsightDefaultStorage](Set-AzureRmHDInsightDefaultStorage.md)
Mengatur pengaturan akun Storage default dalam objek konfigurasi kluster.

### [Set-AzureRmHDInsightPersistedScriptAction](Set-AzureRmHDInsightPersistedScriptAction.md)
Mengatur tindakan skrip yang dijalankan sebelumnya menjadi tindakan skrip tetap.

### [Start-AzureRmHDInsightJob](Start-AzureRmHDInsightJob.md)
Memulai pekerjaan Azure HDInsight yang ditentukan pada kluster tertentu.

### [Stop-AzureRmHDInsightJob](Stop-AzureRmHDInsightJob.md)
Menghentikan pekerjaan yang berjalan tertentu pada kluster.

### [Kirim-AzureRmHDInsightScriptAction](Submit-AzureRmHDInsightScriptAction.md)
Mengirimkan tindakan skrip baru ke kluster Azure HDInsight.

### [Gunakan-AzureRmHDInsightCluster](Use-AzureRmHDInsightCluster.md)
Memilih kluster yang akan digunakan dengan cmdlet Invoke-RmAzureHDInsightHiveJob.

### [Tunggu-AzureRmHDInsightJob](Wait-AzureRmHDInsightJob.md)
Menunggu penyelesaian atau kegagalan pekerjaan yang ditentukan.

