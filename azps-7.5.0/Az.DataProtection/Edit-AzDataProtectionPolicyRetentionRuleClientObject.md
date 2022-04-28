---
external help file: ''
Module Name: Az.DataProtection
online version: https://docs.microsoft.com/powershell/module/az.dataprotection/edit-azdataprotectionpolicyretentionruleclientobject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/Edit-AzDataProtectionPolicyRetentionRuleClientObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/Edit-AzDataProtectionPolicyRetentionRuleClientObject.md
ms.openlocfilehash: cd48c464bb0c965bc1d64dc1820ce9edc11058f8
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144219035"
---
# Edit-AzDataProtectionPolicyRetentionRuleClientObject

## SYNOPSIS
Menambahkan atau menghapus Aturan Retensi ke Kebijakan yang ada

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
Menambahkan atau menghapus Aturan Retensi ke Kebijakan yang ada

## EXAMPLES

### Contoh 1: Tambahkan Aturan Retensi Mingguan
```powershell
$pol = Get-AzDataProtectionPolicyTemplate
$lifecycle = New-AzDataProtectionRetentionLifeCycleClientObject -SourceDataStore OperationalStore -SourceRetentionDurationType Weeks -SourceRetentionDurationCount 5
Edit-AzDataProtectionPolicyRetentionRuleClientObject -Policy $pol -Name Weekly -LifeCycles $lifecycle -IsDefault $false
```

```output
DatasourceType            ObjectType
--------------            ----------
{Microsoft.Compute/disks} BackupPolicy
```

Perintah pertama mendapatkan templat kebijakan default.
Perintah kedua membuat objek siklus hidup mingguan.
Perintah ketiga menambahkan aturan retensi mingguan ke kebijakan default.

### Contoh 2: Menghapus Aturan Retensi Mingguan
```powershell
Edit-AzDataProtectionPolicyRetentionRuleClientObject -Policy $pol -Name Weekly -RemoveRule
```

```output
DatasourceType            ObjectType
--------------            ----------
{Microsoft.Compute/disks} BackupPolicy
```

Perintah ini menghapus aturan retensi mingguan jika ada dalam kebijakan pencadangan yang diberikan.

## PARAMETERS

### -IsDefault
Menentukan apakah aturan retensi adalah aturan retensi default.

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

### -Siklus Hidup
Siklus hidup yang terkait dengan aturan retensi.
Untuk membuat, lihat bagian CATATAN untuk properti LIFECYCLES dan membuat tabel hash.

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

### -Name
Nama Aturan Retensi

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
Objek Kebijakan Pencadangan Untuk membangun, lihat bagian CATATAN untuk properti POLICY dan buat tabel hash.

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
Menentukan apakah akan menghapus aturan retensi.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DataProtection.Models.Api20210701.IBackupPolicy

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


LIFECYCLES <ISourceLifeCycle[]>: Siklus hidup yang terkait dengan aturan retensi.
  - `DeleteAfterDuration <String>`: Durasi penghapusan setelah rentang waktu yang diberikan
  - `DeleteAfterObjectType <String>`: Jenis objek tertentu - digunakan untuk deserialisasi
  - `SourceDataStoreObjectType <String>`: Jenis objek Datasource, digunakan untuk menginisialisasi jenis warisan yang tepat
  - `SourceDataStoreType <DataStoreTypes>`: jenis datastore; Operasional/Vault/Arsip
  - `[TargetDataStoreCopySetting <ITargetCopySetting[]>]`: 
    - `CopyAfterObjectType <String>`: Jenis objek tertentu - digunakan untuk deserialisasi
    - `DataStoreObjectType <String>`: Jenis objek Datasource, digunakan untuk menginisialisasi jenis warisan yang tepat
    - `DataStoreType <DataStoreTypes>`: jenis datastore; Operasional/Vault/Arsip

KEBIJAKAN <IBackupPolicy>: Objek Kebijakan Pencadangan
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

