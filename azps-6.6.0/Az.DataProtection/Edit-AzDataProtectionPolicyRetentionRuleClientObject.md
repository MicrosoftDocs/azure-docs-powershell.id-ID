---
external help file: ''
Module Name: Az.DataProtection
online version: https://docs.microsoft.com/powershell/module/az.dataprotection/edit-azdataprotectionpolicyretentionruleclientobject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/Edit-AzDataProtectionPolicyRetentionRuleClientObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/Edit-AzDataProtectionPolicyRetentionRuleClientObject.md
ms.openlocfilehash: 58540ce122aa1bb8fb7dfe14646ea5391315ab7e
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142085811"
---
# Edit-AzDataProtectionPolicyRetentionRuleClientObject

## SYNOPSIS
Menambahkan atau menghapus Aturan Penyimpanan ke Kebijakan yang sudah ada

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.dataprotection/edit-azdataprotectionpolicyretentionruleclientobject) untuk informasi terbaru.

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

### Contoh 1: Tambahkan Aturan Penyimpanan Mingguan
```powershell
PS C:\> $pol = Get-AzDataProtectionPolicyTemplate
PS C:\> $lifecycle = New-AzDataProtectionRetentionLifeCycleClientObject -SourceDataStore OperationalStore -SourceRetentionDurationType Weeks -SourceRetentionDurationCount 5
PS C:\> Edit-AzDataProtectionPolicyRetentionRuleClientObject -Policy $pol -Name Weekly -LifeCycles $lifecycle -IsDefault $false

DatasourceType            ObjectType
--------------            ----------
{Microsoft.Compute/disks} BackupPolicy
```

Perintah pertama akan mendapatkan templat kebijakan default.
Perintah kedua membuat objek siklus hidup mingguan.
Perintah ketiga menambahkan aturan penyimpanan mingguan ke kebijakan default.

### Contoh 2: Hapus Aturan Penyimpanan Mingguan
```powershell
PS C:\>  Edit-AzDataProtectionPolicyRetentionRuleClientObject -Policy $pol -Name Weekly -RemoveRule

DatasourceType            ObjectType
--------------            ----------
{Microsoft.Compute/disks} BackupPolicy
```

Perintah ini menghapus aturan penyimpanan mingguan jika ada dalam kebijakan cadangan tertentu.

## PARAMETERS

### -IsDefault
Menentukan apakah aturan penyimpanan adalah aturan penyimpanan default.

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
Siklus hidup yang terkait dengan aturan penyimpanan.
Untuk membangun, lihat bagian CATATAN untuk properti LIFECYCLES dan membuat tabel hash.

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
Objek Kebijakan Cadangan Untuk dibangun, lihat bagian CATATAN untuk properti KEBIJAKAN dan membuat tabel hash.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DataProtection.Models.Api20210701.IBackupPolicy

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


LIFECYCLES <ISourceLifeCycle[]>: Siklus hidup yang terkait dengan aturan penyimpanan.
  - `DeleteAfterDuration <String>`: Durasi penghapusan setelah diberikan rentang waktu
  - `DeleteAfterObjectType <String>`: Tipe objek tertentu - digunakan untuk deserialisasi
  - `SourceDataStoreObjectType <String>`: Tipe objek Datasource, digunakan untuk menginisialisasi tipe yang diwariskan ke kanan
  - `SourceDataStoreType <DataStoreTypes>`: jenis datastore; Operasional/Vault/Archive
  - `[TargetDataStoreCopySetting <ITargetCopySetting[]>]`: 
    - `CopyAfterObjectType <String>`: Tipe objek tertentu - digunakan untuk deserialisasi
    - `DataStoreObjectType <String>`: Tipe objek Datasource, digunakan untuk menginisialisasi tipe yang diwariskan ke kanan
    - `DataStoreType <DataStoreTypes>`: jenis datastore; Operasional/Vault/Archive

KEBIJAKAN <IBackupPolicy>: Objek Kebijakan Cadangan
  - `DatasourceType <String[]>`: Tipe sumber data untuk manajemen cadangan
  - `ObjectType <String>`: 
  - `PolicyRule <IBasePolicyRule[]>`: Kamus aturan kebijakan yang berisi aturan untuk setiap tipe cadangan yaitu Full/Incremental/Logs etc
    - `Name <String>`: 
    - `ObjectType <String>`: 
    - `DataStoreObjectType <String>`: Tipe objek Datasource, digunakan untuk menginisialisasi tipe yang diwariskan ke kanan
    - `DataStoreType <DataStoreTypes>`: jenis datastore; Operasional/Vault/Archive
    - `TriggerObjectType <String>`: Tipe objek tertentu - digunakan untuk deserialisasi
    - `Lifecycle <ISourceLifeCycle[]>`: 
      - `DeleteAfterDuration <String>`: Durasi penghapusan setelah diberikan rentang waktu
      - `DeleteAfterObjectType <String>`: Tipe objek tertentu - digunakan untuk deserialisasi
      - `SourceDataStoreObjectType <String>`: Tipe objek Datasource, digunakan untuk menginisialisasi tipe yang diwariskan ke kanan
      - `SourceDataStoreType <DataStoreTypes>`: jenis datastore; Operasional/Vault/Archive
      - `[TargetDataStoreCopySetting <ITargetCopySetting[]>]`: 
        - `CopyAfterObjectType <String>`: Tipe objek tertentu - digunakan untuk deserialisasi
        - `DataStoreObjectType <String>`: Tipe objek Datasource, digunakan untuk menginisialisasi tipe yang diwariskan ke kanan
        - `DataStoreType <DataStoreTypes>`: jenis datastore; Operasional/Vault/Archive
    - `[BackupParameterObjectType <String>]`: Tipe objek tertentu - digunakan untuk deserialisasi
    - `[IsDefault <Boolean?>]`: 

## RELATED LINKS

