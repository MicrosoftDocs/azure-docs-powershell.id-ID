---
external help file: ''
Module Name: Az.DataProtection
online version: https://docs.microsoft.com/powershell/module/az.dataprotection/initialize-azdataprotectionrestorerequest
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/Initialize-AzDataProtectionRestoreRequest.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/Initialize-AzDataProtectionRestoreRequest.md
ms.openlocfilehash: e9fb8de7d81171e18c35725dbc9e8241e42b209c
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/02/2021
ms.locfileid: "136337087"
---
# Initialize-AzDataProtectionRestoreRequest

## SYNOPSIS
Memulai pemulihan objek Permintaan untuk memicu pemulihan pada instans cadangan yang diproteksi.

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
Memulai pemulihan objek Permintaan untuk memicu pemulihan pada instans cadangan yang diproteksi.

## EXAMPLES

### Contoh 1: Dapatkan objek permintaan pemulihan untuk instans Pencadangan Disk Azure yang Dilindungi
```powershell
PS C:\> $instance = Get-AzDataProtectionBackupInstance -SubscriptionId "xxxx-xxx-xxx" -ResourceGroupName "sarath-rg" -VaultName "sarath-vault"
PS C:\> $rp = Get-AzDataProtectionRecoveryPoint -SubscriptionId "xxx-xxx-xxx" -ResourceGroupName "sarath-rg" -VaultName "sarath-vault" -BackupInstanceName $instance.Name
PS C:\> $restoreRequest = Initialize-AzDataProtectionRestoreRequest -DatasourceType AzureDisk -SourceDataStore OperationalStore -RestoreLocation "westus"  -RestoreType AlternateLocation -TargetResourceId "/subscriptions/{subscriptionId}/resourceGroups/{resourceGroup}/providers/Microsoft.Compute/disks/{DiskName}" -RecoveryPoint "892e5c5014dc4a96807d22924f5745c9"
PS C:\> $restoreRequest

ObjectType                                  RestoreTargetInfoObjectType RestoreTargetInfoRecoveryOption RestoreTargetInfoRestoreLocation SourceDataStoreType RecoveryPointI
                                                                                                                                                             d
----------                                  --------------------------- ------------------------------- -------------------------------- ------------------- --------------
AzureBackupRecoveryPointBasedRestoreRequest RestoreTargetInfo           FailIfExists                    westus                           OperationalStore    892e5c5014dc4a96807d22924f5745c9
```

Perintah ini menginialisasi objek permintaan pemulihan yang dapat digunakan untuk memicu pemulihan.

### Contoh 2: Dapatkan objek permintaan pemulihan untuk instans Pencadangan Blob Azure Terlindungi
```powershell
PS C:\> $startTime = (Get-Date).AddDays(-30).ToString("yyyy-MM-ddTHH:mm:ss.0000000Z")
PS C:\> $endTime = (Get-Date).AddDays(0).ToString("yyyy-MM-ddTHH:mm:ss.0000000Z")
PS C:\> $instance = Get-AzDataProtectionBackupInstance -SubscriptionId "xxxx-xxx-xxx" -ResourceGroupName "rgName" -VaultName "vaultName"
PS C:\> $pointInTimeRange = Find-AzDataProtectionRestorableTimeRange -BackupInstanceName $instance[0].BackupInstanceName -ResourceGroupName "rgName" -SubscriptionId "subscriptionId"  -VaultName "vaultName" -SourceDataStoreType OperationalStore -StartTime $startTime -EndTime $endTime
PS C:\> $restoreRequest = Initialize-AzDataProtectionRestoreRequest -DatasourceType AzureBlob -SourceDataStore OperationalStore -RestoreLocation $vault.Location -RestoreType OriginalLocation -BackupInstance $instance[0] -PointInTime (Get-Date -Date $pointInTimeRange.RestorableTimeRange.EndTime)
PS C:\> $restoreRequest

ObjectType                                 RestoreTargetInfoObjectType RestoreTargetInfoRecoveryOption RestoreTargetInfoRestoreLocation SourceDataStoreType RecoveryPointTime
----------                                 --------------------------- ------------------------------- -------------------------------- ------------------- -----------------
AzureBackupRecoveryTimeBasedRestoreRequest restoreTargetInfo           FailIfExists                    eastus2euap                      OperationalStore    2021-04-24T13:32:41.7018481Z

```

Perintah ini menginisialisasi objek permintaan pemulihan yang dapat digunakan untuk memicu pemulihan untuk Blob.

### Contoh 3: Dapatkan objek permintaan pemulihan untuk Pemulihan Tingkat Item untuk wadah dalam contoh AzureBlob Cadangan yang dilindungi
```powershell
PS C:\> $startTime = (Get-Date).AddDays(-30).ToString("yyyy-MM-ddTHH:mm:ss.0000000Z")
PS C:\> $endTime = (Get-Date).AddDays(0).ToString("yyyy-MM-ddTHH:mm:ss.0000000Z")
PS C:\> $instance = Get-AzDataProtectionBackupInstance -SubscriptionId "xxxx-xxx-xxx" -ResourceGroupName "rgName" -VaultName "vaultName"
PS C:\> $pointInTimeRange = Find-AzDataProtectionRestorableTimeRange -BackupInstanceName $instance[0].BackupInstanceName -ResourceGroupName "rgName" -SubscriptionId "subscriptionId"  -VaultName "vaultName" -SourceDataStoreType OperationalStore -StartTime $startTime -EndTime $endTime
PS C:\> $restoreRequest = Initialize-AzDataProtectionRestoreRequest -DatasourceType AzureBlob -SourceDataStore OperationalStore -RestoreLocation $vault.Location -RestoreType OriginalLocation -BackupInstance $instances[0] -PointInTime (Get-Date).AddDays(-1) -ItemLevelRecovery -ContainersList "containerName1","containerName2"
PS C:\> $restoreRequest

ObjectType                                 RestoreTargetInfoObjectType RestoreTargetInfoRecoveryOption RestoreTargetInfoRestoreLocation SourceDataStoreType RecoveryPointTime
----------                                 --------------------------- ------------------------------- -------------------------------- ------------------- -----------------
AzureBackupRecoveryTimeBasedRestoreRequest itemLevelRestoreTargetInfo  FailIfExists                    eastus2euap                      OperationalStore    2021-04-23T02:47:02.9500000Z

```

Perintah ini menginisialisasi objek permintaan pemulihan yang dapat digunakan untuk memicu Pemulihan Tingkat Item pada tingkat wadah untuk Blob.

### Contoh 4: Dapatkan pemulihan objek permintaan untuk Pemulihan Tingkat Item untuk wadah/prefiksMatch di bawah instans Cadangan AzureBlob yang diproteksi
```powershell
PS C:\> $startTime = (Get-Date).AddDays(-30).ToString("yyyy-MM-ddTHH:mm:ss.0000000Z")
PS C:\> $endTime = (Get-Date).AddDays(0).ToString("yyyy-MM-ddTHH:mm:ss.0000000Z")
PS C:\> $instance = Get-AzDataProtectionBackupInstance -SubscriptionId "xxxx-xxx-xxx" -ResourceGroupName "rgName" -VaultName "vaultName"
PS C:\> $pointInTimeRange = Find-AzDataProtectionRestorableTimeRange -BackupInstanceName $instance[0].BackupInstanceName -ResourceGroupName "rgName" -SubscriptionId "subscriptionId"  -VaultName "vaultName" -SourceDataStoreType OperationalStore -StartTime $startTime -EndTime $endTime
PS C:\> $restoreRequest = Initialize-AzDataProtectionRestoreRequest -DatasourceType AzureBlob -SourceDataStore OperationalStore -RestoreLocation $vault.Location -RestoreType OriginalLocation -BackupInstance $instances[0] -PointInTime (Get-Date).AddDays(-1) -ItemLevelRecovery -FromPrefixPattern "container1/aaa","container1/ccc", "container2/aab", "container3" -ToPrefixPattern "container1/bbb","container1/ddd", "container2/abc", "container3-0"
PS C:\> $restoreRequest

ObjectType                                 RestoreTargetInfoObjectType RestoreTargetInfoRecoveryOption RestoreTargetInfoRestoreLocation SourceDataStoreType RecoveryPointTime
----------                                 --------------------------- ------------------------------- -------------------------------- ------------------- -----------------
AzureBackupRecoveryTimeBasedRestoreRequest itemLevelRestoreTargetInfo  FailIfExists                    eastus2euap                      OperationalStore    2021-04-23T02:47:02.9500000Z

```

Perintah ini menginisialisasi objek permintaan pemulihan yang dapat digunakan untuk memicu Pemulihan Tingkat Item pada tingkat blob berdasarkan prefiks nama dalam wadah Blob.

RestoreRequest di atas memulihkan container/blob berikut:

FromPrefix ToPrefix "container1/aaa" "container1/bbb" (memulihkan semua blob yang cocok dalam rentang Prefiks ini) "container1/ccc" "container1/ddd" "container2/aab" "container2/abc" "container3" "container3-0" (restores whole container3)
                    
Catatan: Rentang tidak boleh saling tumpang tindih.
Referensi: https://docs.microsoft.com/en-us/rest/api/storageservices/naming-and-referencing-containers--blobs--and-metadata

## PARAMETERS

### -BackupInstance
Objek Instance Cadangan untuk memicu pemulihan lokal asli.
Untuk membuat, lihat bagian CATATAN untuk properti BACKUPINSTANCE dan membuat tabel hash.

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
Wadah nama untuk Pemulihan Tingkat Item.

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
Tipe SumberData

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
Nama file akan diawali dengan data cadangan yang dipulihkan.

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
Nilai minimum yang cocok untuk Pemulihan Tingkat Item.

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
Arahkan Waktu untuk memulihkan.

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

### -RehydrationDuration
Durasi rehydration untuk titik pemulihan yang diarsipkan agar tetap dihidasi, nilai default untuk durasi rehydration adalah 15.

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
Prioritas rehydrasi untuk titik pemulihan yang diarsipkan.
Parameter ini adalah wajib untuk memulihkan titik-titik yang diarsipkan.

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
Pulihkan Lokasi Target

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
Pulihkan Tipe Target

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
Tipe penyimpanan rahasia untuk autentikasi sumber data toko rahasia.
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
Rahasia uri untuk autentikasi penyimpanan rahasia sumber data.
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
Tipe DataStore titik Pemulihan

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
Id wadah akun penyimpanan target tempat data cadangan akan dipulihkan sebagai file.

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
Id sumber daya target tempat data cadangan akan dipulihkan.

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
Nilai maksimum yang cocok untuk Pemulihan Tingkat Item.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DataProtection.Models.Api20210701.IAzureBackupRestoreRequest

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


BACKUPINSTANCE <BackupInstanceResource> : Objek Instans Cadangan untuk memicu pemulihan lokal asli.
  - `[Property <IBackupInstance>]`: Properti BackupInstanceResource
    - `DataSourceInfo <IDatasource>`: Mendapatkan atau mengatur informasi sumber data.
      - `ResourceId <String>`: ID ARM penuh dari sumber daya. Untuk sumber daya Azure, ini adalah ID ARM. For non azure resources, this will be the ID created by backup service via Fabric/Vault.
      - `[ObjectType <String>]`: Tipe objek Datasource, digunakan untuk memulai tipe yang diwariskan ke kanan
      - `[ResourceLocation <String>]`: Lokasi sumber data.
      - `[ResourceName <String>]`: Pengidentifikasi unik sumber daya dalam konteks induk.
      - `[ResourceType <String>]`: Tipe Sumber Daya Sumber Data.
      - `[ResourceUri <String>]`: Uri dari sumber daya.
      - `[Type <String>]`: TipeData sumber daya.
    - `ObjectType <String>`: 
    - `PolicyInfo <IPolicyInfo>`: Mendapatkan atau mengatur informasi kebijakan.
      - `PolicyId <String>`: 
      - `[PolicyParameter <IPolicyParameters>]`: Parameter kebijakan untuk instans cadangan
        - `[DataStoreParametersList <IDataStoreParameters[]>]`: Mendapatkan atau mengatur Parameter DataStore
          - `DataStoreType <DataStoreTypes>`: tipe penyimpanan data; Operasional/Vault/Arsip
          - `ObjectType <String>`: Tipe objek spesifik - digunakan untuk deserialisasi
    - `[DataSourceSetInfo <IDatasourceSet>]`: Mendapatkan atau mengatur informasi kumpulan sumber data.
      - `ResourceId <String>`: ID ARM penuh dari sumber daya. Untuk sumber daya Azure, ini adalah ID ARM. For non azure resources, this will be the ID created by backup service via Fabric/Vault.
      - `[DatasourceType <String>]`: TipeData sumber daya.
      - `[ObjectType <String>]`: Tipe objek Datasource, digunakan untuk memulai tipe yang diwariskan ke kanan
      - `[ResourceLocation <String>]`: Lokasi sumber data.
      - `[ResourceName <String>]`: Pengidentifikasi unik sumber daya dalam konteks induk.
      - `[ResourceType <String>]`: Tipe Sumber Daya Sumber Data.
      - `[ResourceUri <String>]`: Uri dari sumber daya.
    - `[DatasourceAuthCredentials <IAuthCredentials>]`: Kredensial yang digunakan untuk mengautentikasi dengan penyedia sumber data.
      - `ObjectType <String>`: Tipe objek spesifik - digunakan untuk deserialisasi
    - `[FriendlyName <String>]`: Mendapatkan atau mengatur nama cadangan yang mudah digunakan.

## RELATED LINKS

