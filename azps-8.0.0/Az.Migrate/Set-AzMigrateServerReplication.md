---
external help file: ''
Module Name: Az.Migrate
online version: https://docs.microsoft.com/powershell/module/az.migrate/set-azmigrateserverreplication
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Migrate/help/Set-AzMigrateServerReplication.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Migrate/help/Set-AzMigrateServerReplication.md
ms.openlocfilehash: e69b869c9588fa9460f478d07a4d1669aeacecc9
ms.sourcegitcommit: 5df8b100721844736630242c724da453a2168434
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/26/2022
ms.locfileid: "146593049"
---
# Set-AzMigrateServerReplication

## SYNOPSIS
Updates properti target untuk server replikasi.

## SYNTAX

### ByIDVMwareCbt (Default)
```
Set-AzMigrateServerReplication -TargetObjectID <String> [-DiskToUpdate <IVMwareCbtUpdateDiskInput[]>]
 [-NicToUpdate <IVMwareCbtNicInput[]>] [-SqlServerLicenseType <String>] [-SubscriptionId <String>]
 [-TargetAvailabilitySet <String>] [-TargetAvailabilityZone <String>]
 [-TargetBootDiagnosticsStorageAccount <String>] [-TargetDiskName <String>] [-TargetNetworkId <String>]
 [-TargetResourceGroupID <String>] [-TargetVMName <String>] [-TargetVMSize <String>]
 [-UpdateDiskTag <IVMwareCbtEnableMigrationInputTargetDiskTags>] [-UpdateDiskTagOperation <String>]
 [-UpdateNicTag <IVMwareCbtEnableMigrationInputTargetNicTags>] [-UpdateNicTagOperation <String>]
 [-UpdateTag <Hashtable>] [-UpdateTagOperation <String>]
 [-UpdateVMTag <IVMwareCbtEnableMigrationInputTargetVmtags>] [-UpdateVMTagOperation <String>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### ByInputObjectVMwareCbt
```
Set-AzMigrateServerReplication -InputObject <IMigrationItem> [-DiskToUpdate <IVMwareCbtUpdateDiskInput[]>]
 [-NicToUpdate <IVMwareCbtNicInput[]>] [-SqlServerLicenseType <String>] [-SubscriptionId <String>]
 [-TargetAvailabilitySet <String>] [-TargetAvailabilityZone <String>]
 [-TargetBootDiagnosticsStorageAccount <String>] [-TargetDiskName <String>] [-TargetNetworkId <String>]
 [-TargetResourceGroupID <String>] [-TargetVMName <String>] [-TargetVMSize <String>]
 [-UpdateDiskTag <IVMwareCbtEnableMigrationInputTargetDiskTags>] [-UpdateDiskTagOperation <String>]
 [-UpdateNicTag <IVMwareCbtEnableMigrationInputTargetNicTags>] [-UpdateNicTagOperation <String>]
 [-UpdateTag <Hashtable>] [-UpdateTagOperation <String>]
 [-UpdateVMTag <IVMwareCbtEnableMigrationInputTargetVmtags>] [-UpdateVMTagOperation <String>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet Set-AzMigrateServerReplication memperbarui properti target untuk server replikasi.

## EXAMPLES

### Contoh 1: Perbarui menurut id
```powershell
Set-AzMigrateServerReplication -TargetObjectID '/Subscriptions/xxx-xxx-xxx/resourceGroups/azmigratepwshtestasr13072020/providers/Microsoft.RecoveryServices/vaults/AzMigrateTestProjectPWSH02aarsvault/replicationFabrics/AzMigratePWSHTc8d1replicationfabric/replicationProtectionContainers/AzMigratePWSHTc8d1replicationcontainer/replicationMigrationItems/bcdr-vcenter-fareast-corp-micro-cfcc5a24-a40e-56b9-a6af-e206c9ca4f93_500f44f8-2aa3-587b-8958-ead358639629' -TargetVMName 'rb-w2k12r2-1'
```

```output
ActivityId                       : da958651-96b3-4e65-a41e-897d4b06f7dd ActivityId: 3a4c8d4d-920a-47cd-82c3-f3dcce90a588
AllowedAction                    : {Cancel}
CustomDetailAffectedObjectDetail : Microsoft.Azure.PowerShell.Cmdlets.Migrate.Models.Api20180110.JobDetailsAffectedObjectDetails
CustomDetailInstanceType         : AsrJobDetails
EndTime                          :
Error                            : {}
FriendlyName                     : Update
Id                               : /Subscriptions/xxx-xxx-xxx/resourceGroups/azmigratepwshtestasr13072020/providers/Microsoft.Recover
                                   yServices/vaults/AzMigrateTestProjectPWSH02aarsvault/replicationJobs/931dde9a-de67-4a30-a045-bb9d6162f8ab
Location                         :
Name                             : 931dde9a-de67-4a30-a045-bb9d6162f8ab
ScenarioName                     : Update
StartTime                        : 9/25/20 9:20:08 PM
State                            : InProgress
StateDescription                 : InProgress
TargetInstanceType               : ProtectionEntity
TargetObjectId                   : 101883a0-23f7-538a-bbd5-6d8b4fa900e2
TargetObjectName                 : prsadhu-TestVM
Task                             : {DisableProtectionOnPrimary, UpdateDraState}
Type                             : Microsoft.RecoveryServices/vaults/replicationJobs
```

Berdasarkan id.

### Contoh 2: Memperbarui beberapa nama disk menurut id
```powershell
$OSDisk = Set-AzMigrateDiskMapping -DiskID "6000C294-1217-dec3-bc18-81f117220424" -DiskName "ContosoDisk_1"
$DataDisk = Set-AzMigrateDiskMapping -DiskID "6000C292-79b9-bbdc-fb8a-f1fa8dbeff84" -DiskName "ContosoDisk_2"
$DiskMapping = $OSDisk, $DataDisk
Set-AzMigrateServerReplication -TargetObjectId "/Subscriptions/7c943c1b-5122-4097-90c8-861411bdd574/resourceGroups/cbtsignoff2105srcrg/providers/Microsoft.RecoveryServices/vaults/signoff2105app1452vault/replicationFabrics/signoff2105app1c36replicationfabric/replicationProtectionContainers/signoff2105app1c36replicationcontainer/replicationMigrationItems/idclab-vcen67-fareast-corp-micr-6f5e3b29-29ad-4e62-abbd-6cd33c4183ef_5015f6d8-fc84-afdf-de47-1eab79330f00" -DiskToUpdate $DiskMapping
```

```output
ActivityId                       : c533d88d-2211-43c6-b615-7b46876d8882 ActivityId: de18df8b-8d43-4249-8989-846d33a124f6
AllowedAction                    : {}
CustomDetailAffectedObjectDetail : Microsoft.Azure.PowerShell.Cmdlets.Migrate.Models.Api20210210.JobDetailsAffectedObje
                                   ctDetails
CustomDetailInstanceType         : AsrJobDetails
EndTime                          :
Error                            : {}
FriendlyName                     : Update the virtual machine
Id                               : /Subscriptions/7c943c1b-5122-4097-90c8-861411bdd574/resourceGroups/cbtsignoff2105src
                                   rg/providers/Microsoft.RecoveryServices/vaults/signoff2105app1452vault/replicationJo
                                   bs/6ec1cca6-87c7-4f14-9657-bd0469c02fcd
Location                         :
Name                             : 6ec1cca6-87c7-4f14-9657-bd0469c02fcd
ScenarioName                     : UpdateVmProperties
StartTime                        : 8/30/2021 7:08:51 AM
State                            : InProgress
StateDescription                 : InProgress
TargetInstanceType               : ProtectionEntity
TargetObjectId                   : f3aa6bd4-1b60-52bb-b12d-e850f8d8f13c
TargetObjectName                 : Win2k16
Task                             : {UpdateVmPropertiesTask}
Type                             : Microsoft.RecoveryServices/vaults/replicationJobs
```

Memperbarui nama disk menurut id.

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

### -DiskToUpdate
Updates disk untuk Azure VM yang akan dibuat.
Untuk membuat, lihat bagian CATATAN untuk properti DISKTOUPDATE dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Migrate.Models.Api20210210.IVMwareCbtUpdateDiskInput[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Menentukan server replikasi yang propertinya perlu diperbarui.
Objek server dapat diambil menggunakan cmdlet Get-AzMigrateServerReplication.
Untuk membuat, lihat bagian CATATAN untuk properti INPUTOBJECT dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Migrate.Models.Api20210210.IMigrationItem
Parameter Sets: ByInputObjectVMwareCbt
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NicToUpdate
Updates NIC untuk Azure VM yang akan dibuat.
Untuk membuat, lihat bagian CATATAN untuk properti NICTOUPDATE dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Migrate.Models.Api20210210.IVMwareCbtNicInput[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SqlServerLicenseType
Menentukan apakah manfaat Azure Hybrid untuk SQL Server berlaku untuk server yang akan dimigrasikan.

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

### -SubscriptionId
Id langganan.

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

### -TargetAvailabilitySet
Menentukan Set Ketersediaan yang akan digunakan untuk pembuatan VM.

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

### -TargetAvailabilityZone
Menentukan Zona Ketersediaan yang akan digunakan untuk pembuatan VM.

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

### -TargetBootDiagnosticsStorageAccount
Menentukan akun penyimpanan yang akan digunakan untuk diagnostik boot.

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

### -TargetDiskName
Menentukan nama Azure VM yang akan dibuat.

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

### -TargetNetworkId
Updates id Virtual Network dalam langganan Azure tujuan tempat server perlu dimigrasikan.

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

### -TargetObjectID
Menentukan server replcating yang propertinya perlu diperbarui.
ID harus diambil menggunakan cmdlet Get-AzMigrateServerReplication.

```yaml
Type: System.String
Parameter Sets: ByIDVMwareCbt
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetResourceGroupID
Updates id Grup Sumber Daya dalam langganan Azure tujuan tempat server perlu dimigrasikan.

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

### -TargetVMName
Menentukan server replcating yang propertinya perlu diperbarui.
ID harus diambil menggunakan cmdlet Get-AzMigrateServerReplication.

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

### -TargetVMSize
Updates SKU Azure VM yang akan dibuat.

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

### -UpdateDiskTag
Menentukan tag yang akan digunakan untuk pembuatan disk.
Untuk membuat, lihat bagian CATATAN untuk properti UPDATEDISKTAG dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Migrate.Models.Api20210210.IVMwareCbtEnableMigrationInputTargetDiskTags
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UpdateDiskTagOperation
Menentukan operasi perbarui tag disk.

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

### -UpdateNicTag
Menentukan tag yang akan digunakan untuk pembuatan NIC.
Untuk membuat, lihat bagian CATATAN untuk properti UPDATENICTAG dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Migrate.Models.Api20210210.IVMwareCbtEnableMigrationInputTargetNicTags
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UpdateNicTagOperation
Menentukan operasi NIC tag pembaruan.

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

### -UpdateTag
Menentukan tag yang akan digunakan untuk pembuatan Sumber Daya.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UpdateTagOperation
Menentukan operasi perbarui tag.

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

### -UpdateVMTag
Menentukan tag yang akan digunakan untuk pembuatan VM.
Untuk membuat, lihat bagian CATATAN untuk properti UPDATEVMTAG dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Migrate.Models.Api20210210.IVMwareCbtEnableMigrationInputTargetVmtags
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UpdateVMTagOperation
Menentukan operasi perbarui tag VM.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Migrate.Models.Api20210210.IJob

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


DISKTOUPDATE <IVMwareCbtUpdateDiskInput[]>: Updates disk untuk azure VM yang akan dibuat.
  - `DiskId <String>`: Id disk.
  - `[TargetDiskName <String>]`: Nama disk target.

INPUTOBJECT `<IMigrationItem>`: Menentukan server replikasi yang propertinya perlu diperbarui. Objek server dapat diambil menggunakan cmdlet Get-AzMigrateServerReplication.
  - `[Location <String>]`: Lokasi Sumber Daya
  - `[ProviderSpecificDetail <IMigrationProviderSpecificSettings>]`: Pengaturan kustom penyedia migrasi.

NICTOUPDATE <IVMwareCbtNicInput[]>: Updates NIC untuk azure VM yang akan dibuat.
  - `IsPrimaryNic <String>`: Nilai yang menunjukkan apakah ini adalah NIC utama.
  - `NicId <String>`: Id NIC.
  - `[IsSelectedForMigration <String>]`: Nilai yang menunjukkan apakah NIC ini dipilih untuk migrasi.
  - `[TargetNicName <String>]`: Nama NIC target.
  - `[TargetStaticIPAddress <String>]`: Alamat IP statis.
  - `[TargetSubnetName <String>]`: Nama subnet target.

UPDATEDISKTAG `<IVMwareCbtEnableMigrationInputTargetDiskTags>`: Menentukan tag yang akan digunakan untuk pembuatan disk.
  - `[(Any) <String>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.

UPDATENICTAG `<IVMwareCbtEnableMigrationInputTargetNicTags>`: Menentukan tag yang akan digunakan untuk pembuatan NIC.
  - `[(Any) <String>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.

UPDATEVMTAG `<IVMwareCbtEnableMigrationInputTargetVmtags>`: Menentukan tag yang akan digunakan untuk pembuatan VM.
  - `[(Any) <String>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.

## RELATED LINKS

