---
external help file: ''
Module Name: Az.DataProtection
online version: https://docs.microsoft.com/powershell/module/az.dataprotection/new-azdataprotectionbackuppolicy
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/New-AzDataProtectionBackupPolicy.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/New-AzDataProtectionBackupPolicy.md
ms.openlocfilehash: 5653799e3c5e9c548b426197719bed981c1cbf72
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144218870"
---
# New-AzDataProtectionBackupPolicy

## SYNOPSIS
Membuat kebijakan pencadangan baru dalam vault cadangan tertentu

## SYNTAX

```
New-AzDataProtectionBackupPolicy -Name <String> -Policy <IBackupPolicy> -ResourceGroupName <String>
 -VaultName <String> [-DefaultProfile <PSObject>] [-SubscriptionId <String>] [-Confirm] [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
Membuat kebijakan pencadangan baru dalam vault cadangan tertentu

## EXAMPLES

### Contoh 1: Membuat kebijakan default
```powershell
$defaultPol = Get-AzDataProtectionPolicyTemplate -DatasourceType AzureDisk
New-AzDataProtectionBackupPolicy -SubscriptionId "xxxx-xxx-xxx" -ResourceGroupName sarath-rg -VaultName sarath-vault -Name "MyPolicy" -Policy $defaultPol
```

```output
Name              Type
----              ----
MyPolicy       Microsoft.DataProtection/backupVaults/backupPolicies
```

Perintah ini membuat kebijakan default untuk jenis sumber data disk Azure.

### Contoh 2: Membuat kebijakan untuk AzureDatabaseForPostgreSQL, contoh ini mencakup kebijakan canggih menggunakan powerShell
```powershell
$defaultPol = Get-AzDataProtectionPolicyTemplate -DatasourceType AzureDatabaseForPostgreSQL
$lifeCycleVault = New-AzDataProtectionRetentionLifeCycleClientObject -SourceDataStore VaultStore -SourceRetentionDurationType Months -SourceRetentionDurationCount 3 -TargetDataStore ArchiveStore -CopyOption CopyOnExpiryOption
$lifeCycleArchive = New-AzDataProtectionRetentionLifeCycleClientObject -SourceDataStore ArchiveStore -SourceRetentionDurationType Months -SourceRetentionDurationCount 6
Edit-AzDataProtectionPolicyRetentionRuleClientObject -Policy $defaultPol -Name Default -LifeCycles $lifeCycleVault, $lifeCycleArchive -IsDefault $true
$schDates = @(
 (
     (Get-Date -Year 2021 -Month 08 -Day 18 -Hour 10 -Minute 0 -Second 0)
 ),
 (
     (Get-Date -Year 2021 -Month 08 -Day 22 -Hour 10 -Minute 0 -Second 0) 
 ))

$trigger =  New-AzDataProtectionPolicyTriggerScheduleClientObject -ScheduleDays $schDates -IntervalType Weekly -IntervalCount 1
Edit-AzDataProtectionPolicyTriggerClientObject -Schedule $trigger -Policy $defaultPol   
$lifeCycleVault = New-AzDataProtectionRetentionLifeCycleClientObject -SourceDataStore VaultStore -SourceRetentionDurationType Months -SourceRetentionDurationCount 6 -TargetDataStore ArchiveStore -CopyOption CopyOnExpiryOption
$lifeCycleArchive = New-AzDataProtectionRetentionLifeCycleClientObject -SourceDataStore ArchiveStore -SourceRetentionDurationType Months -SourceRetentionDurationCount 12
Edit-AzDataProtectionPolicyRetentionRuleClientObject -Policy $defaultPol -Name Monthly -LifeCycles $lifeCycleVault, $lifeCycleArchive -IsDefault $false
$tagCriteria = New-AzDataProtectionPolicyTagCriteriaClientObject -AbsoluteCriteria FirstOfMonth
Edit-AzDataProtectionPolicyTagClientObject -Policy $defaultPol -Name Monthly -Criteria $tagCriteria
New-AzDataProtectionBackupPolicy -SubscriptionId "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx" -ResourceGroupName "resourceGroupName" -VaultName "vaultName" -Name "MyPolicy" -Policy $defaultPol
```

```output
Name              Type
----              ----
MyPolicy       Microsoft.DataProtection/backupVaults/backupPolicies
```

Perintah pertama mendapatkan templat kebijakan default untuk AzureDatabaseForPostgreSQL.
Perintah kedua, ketiga membuat dua siklus hidup cadangan yang berbeda untuk brankas dan penyimpanan arsip masing-masing.
Cadangan tetap di vaultstore selama 3 Bulan, dan kemudian menyalin kedaluwarsa ke penyimpanan Arsip dan tinggal di sana sampai 6 bulan.
Perintah keempat memperbarui objek kebijakan dengan siklus hidup yang dibuat.
Perintah kelima keenam membuat objek jadwal kustom untuk kebijakan pencadangan, dua kali setiap minggu mulai dari $schDates.
Perintah ketujuh memperbarui objek kebijakan dengan jadwal kustom.
Perintah kedelapan, kesembilan, kesepuluh memperbarui aturan retensi Bulanan dengan siklus hidup kustom.
Perintah ke-112 membuat kriteria tag untuk kebijakan Bulanan.
Kriteria tag perlu ditambahkan untuk setiap aturan retensi kustom (ditambahkan secara otomatis untuk aturan retensi default).
Perintah terakhir membuat kebijakan.

## PARAMETERS

### -DefaultProfile


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

### -Name
Nama Kebijakan

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

### -Kebijakan
Objek Permintaan Kebijakan Untuk dibuat, lihat bagian CATATAN untuk properti POLICY dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DataProtection.Models.Api20210701.IBackupPolicy
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama Grup Sumber Daya

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

### -SubscriptionId
ID Langganan

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

### -VaultName
Nama Vault

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

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
Cmdlet tidak dijalankan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

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

### Microsoft.Azure.PowerShell.Cmdlets.DataProtection.Models.Api20210701.IBaseBackupPolicyResource

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


KEBIJAKAN <IBackupPolicy>: Objek Permintaan Kebijakan
  - `DatasourceType <String[]>`: Jenis sumber data untuk manajemen cadangan
  - `ObjectType <String>`: 
  - `PolicyRule <IBasePolicyRule[]>`: Kamus aturan kebijakan yang berisi aturan untuk setiap jenis cadangan yaitu Penuh/Inkremental/Log dll
    - `Name <String>`: 
    - `ObjectType <String>`: 
    - `DataStoreObjectType <String>`: Jenis objek Datasource, digunakan untuk menginisialisasi jenis warisan yang tepat
    - `DataStoreType <DataStoreTypes>`: jenis datastore; Operasional/Vault/Arsip
    - `TriggerObjectType <String>`: Jenis objek tertentu - digunakan untuk deserialisasi
    - `Lifecycle <ISourceLifeCycle[]>`: 
      - `DeleteAfterDuration <String>`: Durasi penghapusan setelah rentang waktu yang diberikan
      - `DeleteAfterObjectType <String>`: Jenis objek tertentu - digunakan untuk deserialisasi
      - `SourceDataStoreObjectType <String>`: Jenis objek Datasource, digunakan untuk menginisialisasi jenis warisan yang tepat
      - `SourceDataStoreType <DataStoreTypes>`: jenis datastore; Operasional/Vault/Arsip
      - `[TargetDataStoreCopySetting <ITargetCopySetting[]>]`: 
        - `CopyAfterObjectType <String>`: Jenis objek tertentu - digunakan untuk deserialisasi
        - `DataStoreObjectType <String>`: Jenis objek Datasource, digunakan untuk menginisialisasi jenis warisan yang tepat
        - `DataStoreType <DataStoreTypes>`: jenis datastore; Operasional/Vault/Arsip
    - `[BackupParameterObjectType <String>]`: Jenis objek tertentu - digunakan untuk deserialisasi
    - `[IsDefault <Boolean?>]`: 

## RELATED LINKS

