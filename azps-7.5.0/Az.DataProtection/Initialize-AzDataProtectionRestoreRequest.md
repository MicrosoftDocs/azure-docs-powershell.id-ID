---
external help file: ''
Module Name: Az.DataProtection
online version: https://docs.microsoft.com/powershell/module/az.dataprotection/initialize-azdataprotectionrestorerequest
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/Initialize-AzDataProtectionRestoreRequest.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/Initialize-AzDataProtectionRestoreRequest.md
ms.openlocfilehash: a142efbe507a53075a1223189292e783a8f50dd5
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145748980"
---
# Initialize-AzDataProtectionRestoreRequest

## SYNOPSIS
Menginisialisasi objek Permintaan Pemulihan untuk memicu pemulihan pada instans cadangan yang dilindungi.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.dataprotection/initialize-azdataprotectionrestorerequest) untuk informasi terbaru.

## SYNTAX

### AlternateLocationFullRecovery (Default)
```
Initialize-AzDataProtectionRestoreRequest -DatasourceType <DatasourceTypes> -RestoreLocation <String>
 -RestoreType <RestoreTargetType> -SourceDataStore <DataStoreType> -TargetResourceId <String>
 [-PointInTime <DateTime>] [-RecoveryPoint <String>] [-RehydrationDuration <String>]
 [-RehydrationPriority <String>] [-SecretStoreType <SecretStoreTypes>] [-SecretStoreURI <String>]
 [<CommonParameters>]
```

### OriginalLocationFullRecovery
```
Initialize-AzDataProtectionRestoreRequest -BackupInstance <BackupInstanceResource>
 -DatasourceType <DatasourceTypes> -RestoreLocation <String> -RestoreType <RestoreTargetType>
 -SourceDataStore <DataStoreType> [-PointInTime <DateTime>] [-RecoveryPoint <String>]
 [-RehydrationDuration <String>] [-RehydrationPriority <String>] [-SecretStoreType <SecretStoreTypes>]
 [-SecretStoreURI <String>] [<CommonParameters>]
```

### OriginalLocationILR
```
Initialize-AzDataProtectionRestoreRequest -BackupInstance <BackupInstanceResource>
 -DatasourceType <DatasourceTypes> -ItemLevelRecovery -RestoreLocation <String>
 -RestoreType <RestoreTargetType> -SourceDataStore <DataStoreType> [-ContainersList <String[]>]
 [-FromPrefixPattern <String[]>] [-PointInTime <DateTime>] [-RecoveryPoint <String>]
 [-RehydrationDuration <String>] [-RehydrationPriority <String>] [-SecretStoreType <SecretStoreTypes>]
 [-SecretStoreURI <String>] [-ToPrefixPattern <String[]>] [<CommonParameters>]
```

### RestoreAsFiles
```
Initialize-AzDataProtectionRestoreRequest -DatasourceType <DatasourceTypes> -FileNamePrefix <String>
 -RestoreLocation <String> -RestoreType <RestoreTargetType> -SourceDataStore <DataStoreType>
 -TargetContainerURI <String> [-RecoveryPoint <String>] [-RehydrationDuration <String>]
 [-RehydrationPriority <String>] [-SecretStoreType <SecretStoreTypes>] [-SecretStoreURI <String>]
 [<CommonParameters>]
```

## DESCRIPTION
Menginisialisasi objek Permintaan Pemulihan untuk memicu pemulihan pada instans cadangan yang dilindungi.

## EXAMPLES

### Contoh 1: Dapatkan objek permintaan pemulihan untuk instans Azure Disk Backup yang Dilindungi
```powershell
$instance = Get-AzDataProtectionBackupInstance -SubscriptionId "xxxx-xxx-xxx" -ResourceGroupName "sarath-rg" -VaultName "sarath-vault"
$rp = Get-AzDataProtectionRecoveryPoint -SubscriptionId "xxx-xxx-xxx" -ResourceGroupName "sarath-rg" -VaultName "sarath-vault" -BackupInstanceName $instance.Name
$restoreRequest = Initialize-AzDataProtectionRestoreRequest -DatasourceType AzureDisk -SourceDataStore OperationalStore -RestoreLocation "westus"  -RestoreType AlternateLocation -TargetResourceId "/subscriptions/{subscriptionId}/resourceGroups/{resourceGroup}/providers/Microsoft.Compute/disks/{DiskName}" -RecoveryPoint "892e5c5014dc4a96807d22924f5745c9"
$restoreRequest
```

```output
ObjectType                                  RestoreTargetInfoObjectType RestoreTargetInfoRecoveryOption RestoreTargetInfoRestoreLocation SourceDataStoreType RecoveryPointI
                                                                                                                                                             d
----------                                  --------------------------- ------------------------------- -------------------------------- ------------------- --------------
AzureBackupRecoveryPointBasedRestoreRequest RestoreTargetInfo           FailIfExists                    westus                           OperationalStore    892e5c5014dc4a96807d22924f5745c9
```

Perintah ini menginisialisasi objek permintaan pemulihan yang dapat digunakan untuk memicu pemulihan.

### Contoh 2: Dapatkan objek permintaan pemulihan untuk instans Azure Blob Backup yang Dilindungi
```powershell
$startTime = (Get-Date).AddDays(-30).ToString("yyyy-MM-ddTHH:mm:ss.0000000Z")
$endTime = (Get-Date).AddDays(0).ToString("yyyy-MM-ddTHH:mm:ss.0000000Z")
$instance = Get-AzDataProtectionBackupInstance -SubscriptionId "xxxx-xxx-xxx" -ResourceGroupName "rgName" -VaultName "vaultName"
$pointInTimeRange = Find-AzDataProtectionRestorableTimeRange -BackupInstanceName $instance[0].BackupInstanceName -ResourceGroupName "rgName" -SubscriptionId "subscriptionId"  -VaultName "vaultName" -SourceDataStoreType OperationalStore -StartTime $startTime -EndTime $endTime
$restoreRequest = Initialize-AzDataProtectionRestoreRequest -DatasourceType AzureBlob -SourceDataStore OperationalStore -RestoreLocation $vault.Location -RestoreType OriginalLocation -BackupInstance $instance[0] -PointInTime (Get-Date -Date $pointInTimeRange.RestorableTimeRange.EndTime)
$restoreRequest
```

```output
ObjectType                                 RestoreTargetInfoObjectType RestoreTargetInfoRecoveryOption RestoreTargetInfoRestoreLocation SourceDataStoreType RecoveryPointTime
----------                                 --------------------------- ------------------------------- -------------------------------- ------------------- -----------------
AzureBackupRecoveryTimeBasedRestoreRequest restoreTargetInfo           FailIfExists                    eastus2euap                      OperationalStore    2021-04-24T13:32:41.7018481Z

```

Perintah ini menginisialisasi objek permintaan pemulihan yang dapat digunakan untuk memicu pemulihan blob.

### Contoh 3: Dapatkan objek permintaan pemulihan untuk pemulihan Tingkat Item untuk kontainer di bawah instans AzureBlob Backup yang dilindungi
```powershell
$startTime = (Get-Date).AddDays(-30).ToString("yyyy-MM-ddTHH:mm:ss.0000000Z")
$endTime = (Get-Date).AddDays(0).ToString("yyyy-MM-ddTHH:mm:ss.0000000Z")
$instance = Get-AzDataProtectionBackupInstance -SubscriptionId "xxxx-xxx-xxx" -ResourceGroupName "rgName" -VaultName "vaultName"
$pointInTimeRange = Find-AzDataProtectionRestorableTimeRange -BackupInstanceName $instance[0].BackupInstanceName -ResourceGroupName "rgName" -SubscriptionId "subscriptionId"  -VaultName "vaultName" -SourceDataStoreType OperationalStore -StartTime $startTime -EndTime $endTime
$restoreRequest = Initialize-AzDataProtectionRestoreRequest -DatasourceType AzureBlob -SourceDataStore OperationalStore -RestoreLocation $vault.Location -RestoreType OriginalLocation -BackupInstance $instances[0] -PointInTime (Get-Date).AddDays(-1) -ItemLevelRecovery -ContainersList "containerName1","containerName2"
$restoreRequest
```

```output
ObjectType                                 RestoreTargetInfoObjectType RestoreTargetInfoRecoveryOption RestoreTargetInfoRestoreLocation SourceDataStoreType RecoveryPointTime
----------                                 --------------------------- ------------------------------- -------------------------------- ------------------- -----------------
AzureBackupRecoveryTimeBasedRestoreRequest itemLevelRestoreTargetInfo  FailIfExists                    eastus2euap                      OperationalStore    2021-04-23T02:47:02.9500000Z

```

Perintah ini menginisialisasi objek permintaan pemulihan yang dapat digunakan untuk memicu Pemulihan Tingkat Item pada tingkat kontainer untuk Blob.

### Contoh 4: Dapatkan objek permintaan pemulihan untuk pemulihan Tingkat Item untuk kontainer/prefixMatch di bawah instans AzureBlob Backup yang dilindungi
```powershell
$startTime = (Get-Date).AddDays(-30).ToString("yyyy-MM-ddTHH:mm:ss.0000000Z")
$endTime = (Get-Date).AddDays(0).ToString("yyyy-MM-ddTHH:mm:ss.0000000Z")
$instance = Get-AzDataProtectionBackupInstance -SubscriptionId "xxxx-xxx-xxx" -ResourceGroupName "rgName" -VaultName "vaultName"
$pointInTimeRange = Find-AzDataProtectionRestorableTimeRange -BackupInstanceName $instance[0].BackupInstanceName -ResourceGroupName "rgName" -SubscriptionId "subscriptionId"  -VaultName "vaultName" -SourceDataStoreType OperationalStore -StartTime $startTime -EndTime $endTime
$restoreRequest = Initialize-AzDataProtectionRestoreRequest -DatasourceType AzureBlob -SourceDataStore OperationalStore -RestoreLocation $vault.Location -RestoreType OriginalLocation -BackupInstance $instances[0] -PointInTime (Get-Date).AddDays(-1) -ItemLevelRecovery -FromPrefixPattern "container1/aaa","container1/ccc", "container2/aab", "container3" -ToPrefixPattern "container1/bbb","container1/ddd", "container2/abc", "container3-0"
$restoreRequest
```

```output
ObjectType                                 RestoreTargetInfoObjectType RestoreTargetInfoRecoveryOption RestoreTargetInfoRestoreLocation SourceDataStoreType RecoveryPointTime
----------                                 --------------------------- ------------------------------- -------------------------------- ------------------- -----------------
AzureBackupRecoveryTimeBasedRestoreRequest itemLevelRestoreTargetInfo  FailIfExists                    eastus2euap                      OperationalStore    2021-04-23T02:47:02.9500000Z

```

Perintah ini menginisialisasi objek permintaan pemulihan yang dapat digunakan untuk memicu Pemulihan Tingkat Item pada tingkat blob berdasarkan awalan nama di bawah kontainer Blob.

RestoreRequest di atas memulihkan kontainer/blob berikut:

FromPrefix ToPrefix "container1/aaa" "container1/bbb" (memulihkan semua blob yang cocok dalam rentang Prefiks ini) "container1/ccc" "container1/ddd" "container2/aab" "container2/abc" "container3" "container3-0" (memulihkan seluruh kontainer3)
                    
Catatan: Rentang tidak boleh tumpang tindih satu sama lain.
Referensi: https://docs.microsoft.com/en-us/rest/api/storageservices/naming-and-referencing-containers--blobs--and-metadata

## PARAMETERS

### -BackupInstance
Objek Instans Cadangan untuk memicu pemulihan lokal asli.
Untuk membuat, lihat bagian CATATAN untuk properti BACKUPINSTANCE dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DataProtection.Models.Api20210701.BackupInstanceResource
Parameter Sets: OriginalLocationFullRecovery, OriginalLocationILR
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ContainersList
Nama kontainer untuk Pemulihan Tingkat Item.

```yaml
Type: System.String[]
Parameter Sets: OriginalLocationILR
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DatasourceType
Jenis Sumber Data

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DataProtection.Support.DatasourceTypes
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FileNamePrefix
Nama file yang akan diawali dengan data cadangan yang dipulihkan.

```yaml
Type: System.String
Parameter Sets: RestoreAsFiles
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FromPrefixPattern
Nilai pencocokan minimum untuk Pemulihan Tingkat Item.

```yaml
Type: System.String[]
Parameter Sets: OriginalLocationILR
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ItemLevelRecovery
Alihkan Parameter untuk mengaktifkan pemulihan tingkat item.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: OriginalLocationILR
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PointInTime
Titik Waktu untuk pemulihan.

```yaml
Type: System.DateTime
Parameter Sets: AlternateLocationFullRecovery, OriginalLocationFullRecovery, OriginalLocationILR
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RecoveryPoint
Id titik pemulihan yang akan dipulihkan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RehidrasiDurasi
Durasi rehidrasi untuk titik pemulihan yang diarsipkan agar tetap direhidrasi, nilai default untuk durasi rehidrasi adalah 15.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RehydrationPriority
Prioritas rehidrasi untuk titik pemulihan yang diarsipkan.
Parameter ini wajib untuk pemulihan rehidrasi titik yang diarsipkan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RestoreLocation
Lokasi Pemulihan Target

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RestoreType
Pulihkan Jenis Target

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DataProtection.Support.RestoreTargetType
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SecretStoreType
Jenis penyimpanan rahasia untuk autentikasi penyimpanan rahasia sumber data.
Parameter ini hanya didukung untuk AzureDatabaseForPostgreSQL saat ini.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DataProtection.Support.SecretStoreTypes
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SecretStoreURI
Uri rahasia untuk autentikasi penyimpanan rahasia sumber data.
Parameter ini hanya didukung untuk AzureDatabaseForPostgreSQL saat ini.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceDataStore
Jenis DataStore dari titik Pemulihan

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DataProtection.Support.DataStoreType
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetContainerURI
Id kontainer akun penyimpanan target tempat data cadangan akan dipulihkan sebagai file.

```yaml
Type: System.String
Parameter Sets: RestoreAsFiles
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetResourceId
Id sumber daya target yang data cadangannya akan dipulihkan.

```yaml
Type: System.String
Parameter Sets: AlternateLocationFullRecovery
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ToPrefixPattern
Nilai pencocokan maksimum untuk Pemulihan Tingkat Item.

```yaml
Type: System.String[]
Parameter Sets: OriginalLocationILR
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DataProtection.Models.Api20210701.IAzureBackupRestoreRequest

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


BACKUPINSTANCE <BackupInstanceResource>: Objek Instans Cadangan untuk memicu pemulihan lokalsi asli.
  - `[Property <IBackupInstance>]`: Properti BackupInstanceResource
    - `DataSourceInfo <IDatasource>`: Mendapatkan atau mengatur informasi sumber data.
      - `ResourceId <String>`: ID ARM lengkap sumber daya. Untuk sumber daya azure, ini adalah ARM ID. Untuk sumber daya non azure, ini akan menjadi ID yang dibuat oleh layanan cadangan melalui Fabric/Vault.
      - `[ObjectType <String>]`: Jenis objek Datasource, digunakan untuk menginisialisasi jenis warisan yang tepat
      - `[ResourceLocation <String>]`: Lokasi sumber data.
      - `[ResourceName <String>]`: Pengidentifikasi unik sumber daya dalam konteks induk.
      - `[ResourceType <String>]`: Jenis Sumber Daya Sumber Daya.
      - `[ResourceUri <String>]`: Uri sumber daya.
      - `[Type <String>]`: DatasourceType sumber daya.
    - `ObjectType <String>`: 
    - `PolicyInfo <IPolicyInfo>`: Mendapatkan atau menetapkan informasi kebijakan.
      - `PolicyId <String>`: 
      - `[PolicyParameter <IPolicyParameters>]`: Parameter kebijakan untuk instans cadangan
        - `[DataStoreParametersList <IDataStoreParameters[]>]`: Mendapatkan atau mengatur Parameter DataStore
          - `DataStoreType <DataStoreTypes>`: jenis datastore; Operasional/Vault/Arsip
          - `ObjectType <String>`: Jenis objek tertentu - digunakan untuk deserialisasi
    - `[DataSourceSetInfo <IDatasourceSet>]`: Mendapatkan atau mengatur informasi kumpulan sumber data.
      - `ResourceId <String>`: ID ARM lengkap sumber daya. Untuk sumber daya azure, ini adalah ARM ID. Untuk sumber daya non azure, ini akan menjadi ID yang dibuat oleh layanan cadangan melalui Fabric/Vault.
      - `[DatasourceType <String>]`: DatasourceType sumber daya.
      - `[ObjectType <String>]`: Jenis objek Datasource, digunakan untuk menginisialisasi jenis warisan yang tepat
      - `[ResourceLocation <String>]`: Lokasi sumber data.
      - `[ResourceName <String>]`: Pengidentifikasi unik sumber daya dalam konteks induk.
      - `[ResourceType <String>]`: Jenis Sumber Daya Sumber Daya.
      - `[ResourceUri <String>]`: Uri sumber daya.
    - `[DatasourceAuthCredentials <IAuthCredentials>]`: Kredensial yang digunakan untuk mengautentikasi dengan penyedia sumber data.
      - `ObjectType <String>`: Jenis objek tertentu - digunakan untuk deserialisasi
    - `[FriendlyName <String>]`: Mendapatkan atau mengatur nama yang mudah diingat Instans Cadangan.

## RELATED LINKS

