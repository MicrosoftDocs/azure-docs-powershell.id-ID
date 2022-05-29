---
external help file: ''
Module Name: Az.Migrate
online version: https://docs.microsoft.com/powershell/module/az.migrate/new-azmigrateserverreplication
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Migrate/help/New-AzMigrateServerReplication.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Migrate/help/New-AzMigrateServerReplication.md
ms.openlocfilehash: f384eb6b02cf622d5102578bc0b4f29d49484e6d
ms.sourcegitcommit: 321c644cf2161807a71e1af318fc5c5311d22e25
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/25/2022
ms.locfileid: "145776360"
---
# New-AzMigrateServerReplication

## SYNOPSIS
Memulai replikasi untuk server yang ditentukan.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.migrate/new-azmigrateserverreplication) untuk informasi terbaru.

## SYNTAX

### ByIdDefaultUser (Default)
```
New-AzMigrateServerReplication -DiskType <String> -LicenseType <String> -MachineId <String> -OSDiskID <String>
 -TargetNetworkId <String> -TargetResourceGroupId <String> -TargetSubnetName <String> -TargetVMName <String>
 [-DiskEncryptionSetID <String>] [-DiskTag <IVMwareCbtEnableMigrationInputTargetDiskTags>]
 [-NicTag <IVMwareCbtEnableMigrationInputTargetNicTags>] [-PerformAutoResync <String>]
 [-SqlServerLicenseType <String>] [-SubscriptionId <String>] [-Tag <Hashtable>]
 [-TargetAvailabilitySet <String>] [-TargetAvailabilityZone <String>]
 [-TargetBootDiagnosticsStorageAccount <String>] [-TargetVMSize <String>]
 [-VMTag <IVMwareCbtEnableMigrationInputTargetVmtags>] [-VMWarerunasaccountID <String>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### ByIdPowerUser
```
New-AzMigrateServerReplication -DiskToInclude <IVMwareCbtDiskInput[]> -LicenseType <String>
 -MachineId <String> -TargetNetworkId <String> -TargetResourceGroupId <String> -TargetSubnetName <String>
 -TargetVMName <String> [-DiskTag <IVMwareCbtEnableMigrationInputTargetDiskTags>]
 [-NicTag <IVMwareCbtEnableMigrationInputTargetNicTags>] [-PerformAutoResync <String>]
 [-SqlServerLicenseType <String>] [-SubscriptionId <String>] [-Tag <Hashtable>]
 [-TargetAvailabilitySet <String>] [-TargetAvailabilityZone <String>]
 [-TargetBootDiagnosticsStorageAccount <String>] [-TargetVMSize <String>]
 [-VMTag <IVMwareCbtEnableMigrationInputTargetVmtags>] [-VMWarerunasaccountID <String>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### ByInputObjectDefaultUser
```
New-AzMigrateServerReplication -DiskType <String> -InputObject <IVMwareMachine> -LicenseType <String>
 -OSDiskID <String> -TargetNetworkId <String> -TargetResourceGroupId <String> -TargetSubnetName <String>
 -TargetVMName <String> [-DiskEncryptionSetID <String>]
 [-DiskTag <IVMwareCbtEnableMigrationInputTargetDiskTags>]
 [-NicTag <IVMwareCbtEnableMigrationInputTargetNicTags>] [-PerformAutoResync <String>]
 [-SqlServerLicenseType <String>] [-SubscriptionId <String>] [-Tag <Hashtable>]
 [-TargetAvailabilitySet <String>] [-TargetAvailabilityZone <String>]
 [-TargetBootDiagnosticsStorageAccount <String>] [-TargetVMSize <String>]
 [-VMTag <IVMwareCbtEnableMigrationInputTargetVmtags>] [-VMWarerunasaccountID <String>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### ByInputObjectPowerUser
```
New-AzMigrateServerReplication -DiskToInclude <IVMwareCbtDiskInput[]> -InputObject <IVMwareMachine>
 -LicenseType <String> -TargetNetworkId <String> -TargetResourceGroupId <String> -TargetSubnetName <String>
 -TargetVMName <String> [-DiskTag <IVMwareCbtEnableMigrationInputTargetDiskTags>]
 [-NicTag <IVMwareCbtEnableMigrationInputTargetNicTags>] [-PerformAutoResync <String>]
 [-SqlServerLicenseType <String>] [-SubscriptionId <String>] [-Tag <Hashtable>]
 [-TargetAvailabilitySet <String>] [-TargetAvailabilityZone <String>]
 [-TargetBootDiagnosticsStorageAccount <String>] [-TargetVMSize <String>]
 [-VMTag <IVMwareCbtEnableMigrationInputTargetVmtags>] [-VMWarerunasaccountID <String>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet New-AzMigrateServerReplication memulai replikasi untuk server tertentu yang ditemukan dalam proyek Azure Migrate.

## EXAMPLES

### Contoh 1: Ketika hanya ada disk OS
```powershell
New-AzMigrateServerReplication -MachineId "/subscriptions/xxx-xxx-xxx4/resourceGroups/azmigratepwshtestasr13072020/providers/Microsoft.OffAzure/VMwareSites/AzMigratePWSHTc8d1site/machines/bcdr-vcenter-fareast-corp-micro-cfcc5a24-a40e-56b9-a6af-e206c9ca4f93_50063baa-9806-d6d6-7e09-c0ae87309b4f" -LicenseType NoLicenseType -TargetResourceGroupId "/subscriptions/xxx-xxx-xxx/resourceGroups/AzMigratePWSHtargetRG" -TargetNetworkId  "/subscriptions/xxx-xxx-xxx/resourceGroups/AzMigratePWSHtargetRG/providers/Microsoft.Network/virtualNetworks/AzMigrateTargetNetwork" -TargetSubnetName default -TargetVMName "prsadhu-TestVM" -DiskType "Standard_LRS" -OSDiskID "6000C299-343d-7bcd-c05e-a94bd63316dd"
```

```output
ActivityId                       : 68af14b4-46ae-48d1-b3e9-cdcffb9e8a93 ActivityId: 74d1a396-1d37-4264-8a5b-b727aaef0171
AllowedAction                    : {}
CustomDetailAffectedObjectDetail : Microsoft.Azure.PowerShell.Cmdlets.Migrate.Models.Api20180110.JobDetailsAffectedObjectDetails
CustomDetailInstanceType         : AsrJobDetails
EndTime                          : 9/16/20 11:57:33 AM
Error                            : {}
FriendlyName                     : Enable
Id                               : /Subscriptions/xxx-xxx-xxx/resourceGroups/azmigratepwshtestasr13072020/providers/Microsoft.Recover
                                   yServices/vaults/AzMigrateTestProjectPWSH02aarsvault/replicationJobs/997e2a92-5afe-49c7-a81a-89660aec9b7b
Location                         :
Name                             : 997e2a92-5afe-49c7-a81a-89660aec9b7b
ScenarioName                     : Enable
StartTime                        : 9/16/20 11:57:32 AM
State                            : Succeeded
StateDescription                 : Completed
TargetInstanceType               : ProtectionProfile
TargetObjectId                   : 42752b89-5fad-52fd-bf93-679fbdb6fed9
TargetObjectName                 : migrateAzMigratePWSHTc8d1sitepolicy
Task                             : {CloudPairingPrerequisitesCheck, CloudPairingPrepareSite}
Type                             : Microsoft.RecoveryServices/vaults/replicationJobs
```

Ini untuk skenario, ketika hanya ada satu disk tunggal yang harus dilindungi.

### Contoh 2: Ketika ada beberapa disk
```powershell
$OSDisk = New-AzMigrateDiskMapping -DiskID '6000C299-343d-7bcd-c05e-a94bd63316dd' -DiskType 'Standard_LRS' -IsOSDisk 'true'
$DataDisk = New-AzMigrateDiskMapping -DiskID '7000C299-343d-7bcd-c05e-a94bd63316dd' -DiskType 'Standard_LRS' -IsOSDisk 'false'
$DisksToInclude += $OSDisk
$DisksToInclude += $DataDisk
New-AzMigrateServerReplication -MachineId "/subscriptions/xxx-xxx-xxx/resourceGroups/azmigratepwshtestasr13072020/providers/Microsoft.OffAzure/VMwareSites/AzMigratePWSHTc8d1site/machines/bcdr-vcenter-fareast-corp-micro-cfcc5a24-a40e-56b9-a6af-e206c9ca4f93_50063baa-9806-d6d6-7e09-c0ae87309b4f" -LicenseType NoLicenseType -TargetResourceGroupId "/subscriptions/xxx-xxx-xxx/resourceGroups/AzMigratePWSHtargetRG" -TargetNetworkId  "/subscriptions/xxx-xxx-xxx/resourceGroups/AzMigratePWSHtargetRG/providers/Microsoft.Network/virtualNetworks/AzMigrateTargetNetwork" -TargetSubnetName default -TargetVMName "prsadhu-TestVM" -DiskToInclude $DisksToInclude -PerformAutoResync true
```

```output
ActivityId                       : 68af14b4-46ae-48d1-b3e9-cdcffb9e8a93 ActivityId: 74d1a396-1d37-4264-8a5b-b727aaef0171
AllowedAction                    : {}
CustomDetailAffectedObjectDetail : Microsoft.Azure.PowerShell.Cmdlets.Migrate.Models.Api20180110.JobDetailsAffectedObjectDetails
CustomDetailInstanceType         : AsrJobDetails
EndTime                          : 9/16/20 11:57:33 AM
Error                            : {}
FriendlyName                     : Enable
Id                               : /Subscriptions/xxx-xxx-xxx/resourceGroups/azmigratepwshtestasr13072020/providers/Microsoft.Recover
                                   yServices/vaults/AzMigrateTestProjectPWSH02aarsvault/replicationJobs/997e2a92-5afe-49c7-a81a-89660aec9b7b
Location                         :
Name                             : 997e2a92-5afe-49c7-a81a-89660aec9b7b
ScenarioName                     : Enable
StartTime                        : 9/16/20 11:57:32 AM
State                            : Succeeded
StateDescription                 : Completed
TargetInstanceType               : ProtectionProfile
TargetObjectId                   : 42752b89-5fad-52fd-bf93-679fbdb6fed9
TargetObjectName                 : migrateAzMigratePWSHTc8d1sitepolicy
Task                             : {CloudPairingPrerequisitesCheck, CloudPairingPrepareSite}
Type                             : Microsoft.RecoveryServices/vaults/replicationJobs
```

Ini untuk skenario, ketika ada beberapa disk yang harus dilindungi.

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

### -DiskEncryptionSetID
Menentukan set ensipsi disk yang akan digunakan.

```yaml
Type: System.String
Parameter Sets: ByIdDefaultUser, ByInputObjectDefaultUser
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DiskTag
Menentukan tag yang akan digunakan untuk pembuatan disk.
Untuk membuat, lihat bagian CATATAN untuk properti DISKTAG dan membuat tabel hash.

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

### -DiskToInclude
Menentukan disk pada server sumber yang akan disertakan untuk replikasi.
Untuk membuat, lihat bagian CATATAN untuk properti DISKTOINCLUDE dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Migrate.Models.Api20210210.IVMwareCbtDiskInput[]
Parameter Sets: ByIdPowerUser, ByInputObjectPowerUser
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DiskType
Menentukan jenis disk yang akan digunakan untuk Azure VM.

```yaml
Type: System.String
Parameter Sets: ByIdDefaultUser, ByInputObjectDefaultUser
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Menentukan server yang ditemukan yang akan dimigrasikan.
Objek server dapat diambil menggunakan cmdlet Get-AzMigrateServer.
Untuk membuat, lihat bagian CATATAN untuk properti INPUTOBJECT dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Migrate.Models.Api202001.IVMwareMachine
Parameter Sets: ByInputObjectDefaultUser, ByInputObjectPowerUser
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LicenseType
Menentukan apakah manfaat Azure Hybrid berlaku untuk server sumber yang akan dimigrasikan.

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

### -MachineId
Menentukan ID komputer dari server yang ditemukan yang akan dimigrasikan.

```yaml
Type: System.String
Parameter Sets: ByIdDefaultUser, ByIdPowerUser
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NicTag
Menentukan tag yang akan digunakan untuk pembuatan NIC.
Untuk membuat, lihat bagian CATATAN untuk properti NICTAG dan membuat tabel hash.

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

### -OSDiskID
Menentukan disk Sistem Operasi untuk server sumber yang akan dimigrasikan.

```yaml
Type: System.String
Parameter Sets: ByIdDefaultUser, ByInputObjectDefaultUser
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PerformAutoResync
Menentukan apakah replikasi diperbaiki secara otomatis jika pelacakan perubahan hilang untuk server sumber yang sedang direplikasi.

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

### -Tag
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

### -TargetAvailabilitySet
Menentukan Set Ketersediaan yang akan digunakan untuk pembuatan VMSpesifikasi Set Ketersediaan yang akan digunakan untuk pembuatan VM.

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

### -TargetNetworkId
Menentukan id Virtual Network dalam langganan Azure tujuan tempat server perlu dimigrasikan.

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

### -TargetResourceGroupId
Menentukan id Grup Sumber Daya dalam langganan Azure tujuan tempat server perlu dimigrasikan.

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

### -TargetSubnetName
Menentukan nama Subnet dalam tujuan Virtual Netowk tempat server perlu dimigrasikan.

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

### -TargetVMName
Menentukan nama Azure VM yang akan dibuat.

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

### -TargetVMSize
Menentukan SKU Azure VM yang akan dibuat.

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

### -VMTag
Menentukan tag yang akan digunakan untuk pembuatan VM.
Untuk membuat, lihat bagian CATATAN untuk properti VMTAG dan membuat tabel hash.

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

### -VMWarerunasaccountID
Id akun.

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


DISKTAG <IVMwareCbtEnableMigrationInputTargetDiskTags>: Menentukan tag yang akan digunakan untuk pembuatan disk.
  - `[(Any) <String>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.

DISKTOINCLUDE <IVMwareCbtDiskInput[]>: Menentukan disk pada server sumber yang akan disertakan untuk replikasi.
  - `DiskId <String>`: Id disk.
  - `IsOSDisk <String>`: Nilai yang menunjukkan apakah disk adalah disk OS.
  - `LogStorageAccountId <String>`: Id ARM akun penyimpanan log.
  - `LogStorageAccountSasSecretName <String>`: Nama rahasia brankas kunci dari akun penyimpanan log.
  - `[DiskEncryptionSetId <String>]`: Id ARM DiskEncryptionSet.
  - `[DiskType <DiskAccountType?>]`: Jenis disk.

INPUTOBJECT <IVMwareMachine>: Menentukan server yang ditemukan yang akan dimigrasikan. Objek server dapat diambil menggunakan cmdlet Get-AzMigrateServer.
  - `[GuestOSDetailOstype <String>]`: Jenis sistem operasi.

NICTAG <IVMwareCbtEnableMigrationInputTargetNicTags>: Menentukan tag yang akan digunakan untuk pembuatan NIC.
  - `[(Any) <String>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.

VMTAG <IVMwareCbtEnableMigrationInputTargetVmtags>: Menentukan tag yang akan digunakan untuk pembuatan VM.
  - `[(Any) <String>]`: Ini menunjukkan properti apa pun dapat ditambahkan ke objek ini.

## RELATED LINKS

