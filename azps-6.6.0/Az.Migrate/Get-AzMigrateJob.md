---
external help file: ''
Module Name: Az.Migrate
online version: https://docs.microsoft.com/powershell/module/az.migrate/get-azmigratejob
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Migrate/help/Get-AzMigrateJob.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Migrate/help/Get-AzMigrateJob.md
ms.openlocfilehash: 42178774f99befb2c65d1a1d8e6d4321008df0e5
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142270249"
---
# Get-AzMigrateJob

## SYNOPSIS
Mengambil status pekerjaan Migrasi Azure.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.migrate/get-azmigratejob) untuk informasi terbaru.

## SYNTAX

### ListByName (Default)
```
Get-AzMigrateJob -ProjectName <String> -ResourceGroupName <String> [-SubscriptionId <String>]
 [-Filter <String>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetById
```
Get-AzMigrateJob -JobID <String> [-SubscriptionId <String>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetByInputObject
```
Get-AzMigrateJob -InputObject <IJob> [-SubscriptionId <String>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### GetByName
```
Get-AzMigrateJob -JobName <String> -ProjectName <String> -ResourceGroupName <String>
 [-SubscriptionId <String>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### ListById
```
Get-AzMigrateJob -ProjectID <String> -ResourceGroupID <String> [-SubscriptionId <String>] [-Filter <String>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet Get-AzMigrateJob mengupahkan status pekerjaan Migrasi Azure.

## EXAMPLES

### Contoh 1: Get By Job Id
```powershell
PS C:\> Get-AzMigrateJob -JobID "/Subscriptions/xxx-xxx-xxx/resourceGroups/azmigratepwshtestasr13072020/providers/Microsoft.RecoveryServices/vaults/AzMigrateTestProjectPWSH02aarsvault/replicationJobs/997e2a92-5afe-49c7-a81a-89660aec9b7b" 

ActivityId                       : 68af14b4-46ae-48d1-b3e9-cdcffb9e8a93 ActivityId: 74d1a396-1d37-4264-8a5b-b727aaef0171
AllowedAction                    : {}
CustomDetailAffectedObjectDetail : Microsoft.Azure.PowerShell.Cmdlets.Migrate.Models.Api20180110.JobDetailsAffectedObjectDetails
CustomDetailInstanceType         : AsrJobDetails
EndTime                          : 9/16/20 11:57:33 AM
Error                            : {}
FriendlyName                     : Associate replication policy
Id                               : /Subscriptions/xxx-xxx-xxx/resourceGroups/azmigratepwshtestasr13072020/providers/Microsoft.Recover
                                   yServices/vaults/AzMigrateTestProjectPWSH02aarsvault/replicationJobs/997e2a92-5afe-49c7-a81a-89660aec9b7b
Location                         :
Name                             : 997e2a92-5afe-49c7-a81a-89660aec9b7b
ScenarioName                     : AssociateProtectionProfile
StartTime                        : 9/16/20 11:57:32 AM
State                            : Succeeded
StateDescription                 : Completed
TargetInstanceType               : ProtectionProfile
TargetObjectId                   : 42752b89-5fad-52fd-bf93-679fbdb6fed9
TargetObjectName                 : migrateAzMigratePWSHTc8d1sitepolicy
Task                             : {CloudPairingPrerequisitesCheck, CloudPairingPrepareSite}
Type                             : Microsoft.RecoveryServices/vaults/replicationJobs
```

Ini mengambil pekerjaan dengan id itu.

### Contoh 2: Daftar menurut grup sumber daya dan proyek
```powershell
PS C:\> Get-AzMigrateJob -ResourceGroupName 'azmigratepwshtestasr13072020' -ProjectName 'AzMigrateTestProjectPWSH'

ActivityId                       :
AllowedAction                    : {}
CustomDetailAffectedObjectDetail : Microsoft.Azure.PowerShell.Cmdlets.Migrate.Models.Api20180110.JobDetailsAffectedObjectDetails
CustomDetailInstanceType         :
EndTime                          : 9/21/20 4:13:40 PM
Error                            : {}
FriendlyName                     : Update the virtual machine
Id                               : /Subscriptions/xxx-xxx-xxx/resourceGroups/azmigratepwshtestasr13072020/providers/Microsoft.Recover
                                   yServices/vaults/AzMigrateTestProjectPWSH02aarsvault/replicationJobs/1c89e38e-34ec-4903-aa7c-115201bf2de1
Location                         :
Name                             : 1c89e38e-34ec-4903-aa7c-115201bf2de1
ScenarioName                     : UpdateVmProperties
StartTime                        : 9/21/20 4:13:34 PM
State                            : Succeeded
StateDescription                 : Completed
TargetInstanceType               : ProtectionEntity
TargetObjectId                   : 593b735d-2a34-53b2-b8ed-e33da5650703
TargetObjectName                 : rb-w2k12r2-1
Task                             : {}
Type                             : Microsoft.RecoveryServices/vaults/replicationJobs
```

Ini mendapatkan semua pekerjaan dalam sebuah proyek.

### Contoh 3: Dapatkan menurut grup sumber daya, proyek dan nama pekerjaan
```powershell
PS C:\> Get-AzMigrateJob -ResourceGroupName 'azmigratepwshtestasr13072020' -ProjectName 'AzMigrateTestProjectPWSH' -JobName 7ae1ee7c-442c-499d-8b0e-81d52a42b71e

ActivityId                       : 6986b7e5-0f1f-49d8-8b4b-77e6f66bcb92 ActivityId: eb73c6a1-7c66-469f-a853-d896aa38cc0f
AllowedAction                    : {}
CustomDetailAffectedObjectDetail : Microsoft.Azure.PowerShell.Cmdlets.Migrate.Models.Api20180110.JobDetailsAffectedObjectDetails
CustomDetailInstanceType         : AsrJobDetails
EndTime                          : 8/21/20 6:41:48 AM
Error                            : {}
FriendlyName                     : Create replication policy
Id                               : /Subscriptions/xxx-xxx-xxx/resourceGroups/azmigratepwshtestasr13072020/providers/Microsoft.Recover
                                   yServices/vaults/AzMigrateTestProjectPWSH02aarsvault/replicationJobs/7ae1ee7c-442c-499d-8b0e-81d52a42b71e
Location                         :
Name                             : 7ae1ee7c-442c-499d-8b0e-81d52a42b71e
ScenarioName                     : AddProtectionProfile
StartTime                        : 8/21/20 6:41:48 AM
State                            : Succeeded
StateDescription                 : Completed
TargetInstanceType               : ProtectionProfile
TargetObjectId                   : 18b2ccec-e39a-517b-ae5d-dd395e9f4f96
TargetObjectName                 : samplePolicy3
Task                             : {AddProtectionProfilePreflightsCheckTask, AddProtectionProfileTask}
Type                             : Microsoft.RecoveryServices/vaults/replicationJobs
```

Ini mendapatkan pekerjaan tertentu.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases: AzureRMContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Filter
Opsi filter OData.

```yaml
Type: System.String
Parameter Sets: ListById, ListByName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Menentukan objek pekerjaan server replikasi.
Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Migrate.Models.Api20210210.IJob
Parameter Sets: GetByInputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobID
Menentukan id pekerjaan yang detailnya perlu diambil.

```yaml
Type: System.String
Parameter Sets: GetById
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobName
Pengidentifikasi pekerjaan

```yaml
Type: System.String
Parameter Sets: GetByName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProjectID
Menentukan Project Azure Migrasi server yang sedang direplikasi.

```yaml
Type: System.String
Parameter Sets: ListById
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProjectName
Nama proyek migrasi.

```yaml
Type: System.String
Parameter Sets: GetByName, ListByName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupID
Menentukan Grup Sumber Daya Azure Melakukan migrasi Project dalam langganan saat ini.

```yaml
Type: System.String
Parameter Sets: ListById
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya tempat kubah layanan pemulihan ada.

```yaml
Type: System.String
Parameter Sets: GetByName, ListByName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
ID Langganan Azure.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Migrate.Models.Api20210210.IJob

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IJob>: Menentukan objek pekerjaan server replikasi.
  - `[Location <String>]`: Lokasi Sumber Daya
  - `[ActivityId <String>]`: Id aktivitas.
  - `[AllowedAction <String[]>]`: Tindakan yang diizinkan untuk pekerjaan.
  - `[CustomDetailAffectedObjectDetail <IJobDetailsAffectedObjectDetails>]`: Properti objek yang terpengaruh seperti server sumber, awan sumber, server target, awan target dll. berdasarkan detail objek alur kerja.
    - `[(Any) <String>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.
  - `[EndTime <DateTime?>]`: Waktu akhir.
  - `[Error <IJobErrorDetails[]>]`: Kesalahan.
    - `[CreationTime <DateTime?>]`: Waktu pembuatan kesalahan pekerjaan.
    - `[ErrorLevel <String>]`: Tingkat kesalahan kesalahan.
    - `[ProviderErrorDetailErrorCode <Int32?>]`: Kode Kesalahan.
    - `[ProviderErrorDetailErrorId <String>]`: Id kesalahan Penyedia.
    - `[ProviderErrorDetailErrorMessage <String>]`: Pesan Kesalahan.
    - `[ProviderErrorDetailPossibleCaus <String>]`: Kemungkinan penyebab kesalahan.
    - `[ProviderErrorDetailRecommendedAction <String>]`: Tindakan yang disarankan untuk mengatasi kesalahan.
    - `[ServiceErrorDetailActivityId <String>]`: Id Aktivitas.
    - `[ServiceErrorDetailCode <String>]`: Kode kesalahan.
    - `[ServiceErrorDetailMessage <String>]`: Pesan kesalahan.
    - `[ServiceErrorDetailPossibleCaus <String>]`: Kemungkinan penyebab kesalahan.
    - `[ServiceErrorDetailRecommendedAction <String>]`: Tindakan yang disarankan untuk mengatasi kesalahan.
    - `[TaskId <String>]`: Id tugas.
  - `[FriendlyName <String>]`: NamaPajangan.
  - `[ScenarioName <String>]`: Nama Skenario.
  - `[StartTime <DateTime?>]`: Waktu mulai.
  - `[State <String>]`: Status Pekerjaan. Ini adalah salah satu nilai ini - NotStarted, InProgress, Berhasil, Gagal, Dibatalkan, Ditangguhkan atau Lainnya.
  - `[StateDescription <String>]`: Penjabaran status Pekerjaan. Misalnya - Untuk status Berhasil, deskripsi dapat Diselesaikan, Diukur Sebagian, CompletedWithInformation atau Dilewati.
  - `[TargetInstanceType <String>]`: Tipe objek yang terpengaruh yang merupakan kelas Microsoft.Azure.SiteRecovery.V2015_11_10.AffectedObjectType.
  - `[TargetObjectId <String>]`: Id Objek yang terpengaruh.
  - `[TargetObjectName <String>]`: Nama objek yang terpengaruh.
  - `[Task <IAsrTask[]>]`: Tugas.
    - `[AllowedAction <String[]>]`: Status/tindakan yang berlaku pada tugas ini.
    - `[CustomDetailInstanceType <String>]`: Tipe detail tugas.
    - `[EndTime <DateTime?>]`: Waktu akhir.
    - `[Error <IJobErrorDetails[]>]`: Detail kesalahan tugas.
    - `[FriendlyName <String>]`: Nama.
    - `[GroupTaskCustomDetailChildTask <IAsrTask[]>]`: Tugas anak.
    - `[GroupTaskCustomDetailInstanceType <String>]`: Tipe detail tugas.
    - `[Name <String>]`: Nama Tugas yang unik.
    - `[StartTime <DateTime?>]`: Waktu mulai.
    - `[State <String>]`: Negara Bagian. Ini adalah salah satu nilai ini - NotStarted, InProgress, Berhasil, Gagal, Dibatalkan, Ditangguhkan atau Lainnya.
    - `[StateDescription <String>]`: Penjabaran dari status tugas. Misalnya - Untuk Status berhasil, deskripsi dapat Diselesaikan, Dididik Sebagian, SelesaiWithInformation atau Dilewati.
    - `[TaskId <String>]`: Id.
    - `[TaskType <String>]`: Tipe tugas. Detail dalam properti CustomDetails bergantung pada tipe ini.

## RELATED LINKS

