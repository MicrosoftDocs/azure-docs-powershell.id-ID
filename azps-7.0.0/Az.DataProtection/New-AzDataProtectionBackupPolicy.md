---
external help file: ''
Module Name: Az.DataProtection
online version: https://docs.microsoft.com/powershell/module/az.dataprotection/new-azdataprotectionbackuppolicy
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/New-AzDataProtectionBackupPolicy.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/New-AzDataProtectionBackupPolicy.md
ms.openlocfilehash: d059ecb2c7995c7a08ff13d0aad670180f1900fd
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136553224"
---
# New-AzDataProtectionBackupPolicy

## SYNOPSIS
Membuat kebijakan pencadangan baru di vault cadangan tertentu

## SYNTAX

```
New-AzDataProtectionBackupPolicy -Name <String> -Policy <IBackupPolicy> -ResourceGroupName <String>
 -VaultName <String> [-DefaultProfile <PSObject>] [-SubscriptionId <String>] [-Confirm] [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
Membuat kebijakan pencadangan baru di vault cadangan tertentu

## EXAMPLES

### Contoh 1: Membuat kebijakan default
```powershell
PS C:\> $defaultPol = Get-AzDataProtectionPolicyTemplate -DatasourceType AzureDisk
PS C:\> New-AzDataProtectionBackupPolicy -SubscriptionId "xxxx-xxx-xxx" -ResourceGroupName sarath-rg -VaultName sarath-vault -Name "MyPolicy" -Policy $defaultPol

Name              Type
----              ----
MyPolicy       Microsoft.DataProtection/backupVaults/backupPolicies
```

Perintah ini membuat kebijakan default untuk tipe sumber data disk Azure.

### Contoh 2: Buat kebijakan untuk AzureDatabaseForPostgreSQL, contoh ini membahas kebijakan canggih menggunakan powerShell
```powershell
PS C:\> $defaultPol = Get-AzDataProtectionPolicyTemplate -DatasourceType AzureDatabaseForPostgreSQL
PS C:\> $lifeCycleVault = New-AzDataProtectionRetentionLifeCycleClientObject -SourceDataStore VaultStore -SourceRetentionDurationType Months -SourceRetentionDurationCount 3 -TargetDataStore ArchiveStore -CopyOption CopyOnExpiryOption
PS C:\> $lifeCycleArchive = New-AzDataProtectionRetentionLifeCycleClientObject -SourceDataStore ArchiveStore -SourceRetentionDurationType Months -SourceRetentionDurationCount 6
PS C:\> Edit-AzDataProtectionPolicyRetentionRuleClientObject -Policy $defaultPol -Name Default -LifeCycles $lifeCycleVault, $lifeCycleArchive -IsDefault $true
PS C:\> $schDates = @(
 (
     (Get-Date -Year 2021 -Month 08 -Day 18 -Hour 10 -Minute 0 -Second 0)
 ),
 (
     (Get-Date -Year 2021 -Month 08 -Day 22 -Hour 10 -Minute 0 -Second 0) 
 ))

PS C:\> $trigger =  New-AzDataProtectionPolicyTriggerScheduleClientObject -ScheduleDays $schDates -IntervalType Weekly -IntervalCount 1
PS C:\> Edit-AzDataProtectionPolicyTriggerClientObject -Schedule $trigger -Policy $defaultPol   
PS C:\> $lifeCycleVault = New-AzDataProtectionRetentionLifeCycleClientObject -SourceDataStore VaultStore -SourceRetentionDurationType Months -SourceRetentionDurationCount 6 -TargetDataStore ArchiveStore -CopyOption CopyOnExpiryOption
PS C:\> $lifeCycleArchive = New-AzDataProtectionRetentionLifeCycleClientObject -SourceDataStore ArchiveStore -SourceRetentionDurationType Months -SourceRetentionDurationCount 12
PS C:\> Edit-AzDataProtectionPolicyRetentionRuleClientObject -Policy $defaultPol -Name Monthly -LifeCycles $lifeCycleVault, $lifeCycleArchive -IsDefault $false
PS C:\> $tagCriteria = New-AzDataProtectionPolicyTagCriteriaClientObject -AbsoluteCriteria FirstOfMonth
PS C:\> Edit-AzDataProtectionPolicyTagClientObject -Policy $defaultPol -Name Monthly -Criteria $tagCriteria
PS C:\> New-AzDataProtectionBackupPolicy -SubscriptionId "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx" -ResourceGroupName "resourceGroupName" -VaultName "vaultName" -Name "MyPolicy" -Policy $defaultPol


Name              Type
----              ----
MyPolicy       Microsoft.DataProtection/backupVaults/backupPolicies
```

Perintah pertama mendapatkan templat kebijakan default untuk AzureDatabaseForPostgreSQL.
Perintah kedua dan ketiga masing-masing membuat dua siklus hidup cadangan yang berbeda untuk penyimpanan penyimpanan dan arsip.
Cadangan tetap berada di vaultstore selama 3 Bulan, lalu salinan akan kedaluwarsa ke Toko arsip dan akan tetap berada di sana hingga 6 bulan.
Perintah keempat memperbarui objek kebijakan dengan siklus hidup yang dibuat.
Perintah kelima dan keenam membuat objek jadwal kustom untuk kebijakan cadangan, dua kali mingguan dimulai dari $schDates.
Perintah ketujuh memperbarui objek kebijakan dengan jadwal kustom.
Perintah kedelapan, kesepuluh, memperbarui aturan penyimpanan Bulanan dengan siklus hidup kustom.
The sebelas, perintah kedua belas membuat kriteria tag untuk kebijakan Bulanan.
Kriteria tag perlu ditambahkan untuk setiap aturan penyimpanan kustom (ditambahkan secara otomatis untuk aturan penyimpanan default).
Perintah terakhir membuat kebijakan tersebut.

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

### -Nama
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
Policy Request Object To construct, see NOTES section for POLICY properties and create a hash table.

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
Id Langganan

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

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DataProtection.Models.Api20210701.IBaseBackupPolicyResource

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


KEBIJAKAN <IBackupPolicy> : Objek Permintaan Kebijakan
  - `DatasourceType <String[]>`: Tipe sumber data untuk manajemen pencadangan
  - `ObjectType <String>`: 
  - `PolicyRule <IBasePolicyRule[]>`: Kamus aturan kebijakan yang berisi aturan untuk setiap tipe cadangan i.e Penuh/Penambahan/Log dll
    - `Name <String>`: 
    - `ObjectType <String>`: 
    - `DataStoreObjectType <String>`: Tipe objek Datasource, digunakan untuk memulai tipe yang diwariskan ke kanan
    - `DataStoreType <DataStoreTypes>`: tipe penyimpanan data; Operasional/Vault/Arsip
    - `TriggerObjectType <String>`: Tipe objek spesifik - digunakan untuk deserialisasi
    - `Lifecycle <ISourceLifeCycle[]>`: 
      - `DeleteAfterDuration <String>`: Durasi penghapusan setelah jangka waktu tertentu
      - `DeleteAfterObjectType <String>`: Tipe objek spesifik - digunakan untuk deserialisasi
      - `SourceDataStoreObjectType <String>`: Tipe objek Datasource, digunakan untuk memulai tipe yang diwariskan ke kanan
      - `SourceDataStoreType <DataStoreTypes>`: tipe penyimpanan data; Operasional/Vault/Arsip
      - `[TargetDataStoreCopySetting <ITargetCopySetting[]>]`: 
        - `CopyAfterObjectType <String>`: Tipe objek spesifik - digunakan untuk deserialisasi
        - `DataStoreObjectType <String>`: Tipe objek Datasource, digunakan untuk memulai tipe yang diwariskan ke kanan
        - `DataStoreType <DataStoreTypes>`: tipe penyimpanan data; Operasional/Vault/Arsip
    - `[BackupParameterObjectType <String>]`: Tipe objek spesifik - digunakan untuk deserialisasi
    - `[IsDefault <Boolean?>]`: 

## RELATED LINKS

