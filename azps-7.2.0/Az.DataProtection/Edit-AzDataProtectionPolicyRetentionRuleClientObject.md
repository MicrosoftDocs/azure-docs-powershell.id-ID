---
external help file: ''
Module Name: Az.DataProtection
online version: https://docs.microsoft.com/powershell/module/az.dataprotection/edit-azdataprotectionpolicyretentionruleclientobject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/Edit-AzDataProtectionPolicyRetentionRuleClientObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/Edit-AzDataProtectionPolicyRetentionRuleClientObject.md
ms.openlocfilehash: 040f56ce068ea079fd6a71d31cb3f3718dc45dc6
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138253819"
---
# Edit-AzDataProtectionPolicyRetentionRuleClientObject

## SYNOPSIS
Menambahkan atau menghapus Aturan Penyimpanan ke Kebijakan yang sudah ada

## SYNTAX

### RemoveRetention (Default)
```
Edit-AzDataProtectionPolicyRetentionRuleClientObject -Name <RetentionRuleName> -Policy <IBackupPolicy>
 -RemoveRule [<CommonParameters>]
```

### AddRetention
```
Edit-AzDataProtectionPolicyRetentionRuleClientObject -IsDefault <Boolean> -LifeCycles <ISourceLifeCycle[]>
 -Name <RetentionRuleName> -Policy <IBackupPolicy> [<CommonParameters>]
```

## DESCRIPTION
Menambahkan atau menghapus Aturan Penyimpanan ke Kebijakan yang sudah ada

## EXAMPLES

### Contoh 1: Tambahkan aturan penyimpanan mingguan
```powershell
PS C:\> $pol = Get-AzDataProtectionPolicyTemplate
PS C:\> $lifecycle = New-AzDataProtectionRetentionLifeCycleClientObject -SourceDataStore OperationalStore -SourceRetentionDurationType Weeks -SourceRetentionDurationCount 5
PS C:\> Edit-AzDataProtectionPolicyRetentionRuleClientObject -Policy $pol -Name Weekly -LifeCycles $lifecycle -IsDefault $false

DatasourceType            ObjectType
--------------            ----------
{Microsoft.Compute/disks} BackupPolicy
```

Perintah pertama mendapatkan templat kebijakan default.
Perintah kedua membuat objek siklus hidup mingguan.
Perintah ketiga menambahkan aturan penyimpanan mingguan ke kebijakan default.

### Contoh 2: Hapus aturan penyimpanan mingguan
```powershell
PS C:\>  Edit-AzDataProtectionPolicyRetentionRuleClientObject -Policy $pol -Name Weekly -RemoveRule

DatasourceType            ObjectType
--------------            ----------
{Microsoft.Compute/disks} BackupPolicy
```

Perintah ini menghapus aturan penyimpanan mingguan jika ada dalam kebijakan pencadangan tertentu.

## PARAMETERS

### -IsDefault
Menentukan jika aturan penyimpanan adalah aturan penyimpanan default.

```yaml
Type: System.Boolean
Parameter Sets: AddRetention
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LifeCysit
Siklus hidup yang terkait dengan aturan penyimpanan.
Untuk membuat, lihat bagian CATATAN untuk properti SIKLUS HIDUP dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DataProtection.Models.Api20210701.ISourceLifeCycle[]
Parameter Sets: AddRetention
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama Aturan Penyimpanan

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DataProtection.Support.RetentionRuleName
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Kebijakan
Objek Kebijakan Cadangan Untuk dibuat, lihat bagian CATATAN untuk properti KEBIJAKAN dan membuat tabel hash.

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

### -RemoveRule
Menentukan apakah akan menghapus aturan penyimpanan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: RemoveRetention
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DataProtection.Models.Api20210701.IBackupPolicy

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


SIKLUS HIDUP <ISourceLifeCycle[]>: Siklus hidup yang terkait dengan aturan penyimpanan.
  - `DeleteAfterDuration <String>`: Durasi penghapusan setelah jangka waktu tertentu
  - `DeleteAfterObjectType <String>`: Tipe objek spesifik - digunakan untuk deserialisasi
  - `SourceDataStoreObjectType <String>`: Tipe objek Datasource, digunakan untuk memulai tipe yang diwariskan ke kanan
  - `SourceDataStoreType <DataStoreTypes>`: tipe penyimpanan data; Operasional/Vault/Arsip
  - `[TargetDataStoreCopySetting <ITargetCopySetting[]>]`: 
    - `CopyAfterObjectType <String>`: Tipe objek spesifik - digunakan untuk deserialisasi
    - `DataStoreObjectType <String>`: Tipe objek Datasource, digunakan untuk memulai tipe yang diwariskan ke kanan
    - `DataStoreType <DataStoreTypes>`: tipe penyimpanan data; Operasional/Vault/Arsip

KEBIJAKAN <IBackupPolicy>: Objek Kebijakan Cadangan
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

