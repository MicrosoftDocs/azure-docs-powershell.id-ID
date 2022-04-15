---
external help file: ''
Module Name: Az.DataProtection
online version: https://docs.microsoft.com/powershell/module/az.dataprotection/edit-azdataprotectionpolicytagclientobject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/Edit-AzDataProtectionPolicyTagClientObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/Edit-AzDataProtectionPolicyTagClientObject.md
ms.openlocfilehash: 9e65c2dba36f9dec18fb017430a6800b80e19ac3
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142432802"
---
# Edit-AzDataProtectionPolicyTagClientObject

## SYNOPSIS
Menambahkan atau menghapus tag jadwal dalam kebijakan cadangan yang sudah ada.

## SYNTAX

### RemoveTag (Default)
```
Edit-AzDataProtectionPolicyTagClientObject -Name <TagName> -Policy <IBackupPolicy> -RemoveRule
 [<CommonParameters>]
```

### updateTag
```
Edit-AzDataProtectionPolicyTagClientObject -Criteria <IScheduleBasedBackupCriteria[]> -Name <TagName>
 -Policy <IBackupPolicy> [<CommonParameters>]
```

## DESCRIPTION
Menambahkan atau menghapus tag jadwal dalam kebijakan cadangan yang sudah ada.

## EXAMPLES

### Contoh 1: Tambahkan tag Mingguan ke Kebijakan Pencadangan
```powershell
$criteria = New-AzDataProtectionPolicyTagCriteriaClientObject -AbsoluteCriteria FirstOfWeek
Edit-AzDataProtectionPolicyTagClientObject -Policy $pol -Name Weekly -Criteria $criteria
```

```output
DatasourceType            ObjectType
--------------            ----------
{Microsoft.Compute/disks} BackupPolicy
```

Perintah ini menambahkan tag mingguan ke kebijakan cadangan yang diberikan

### Contoh 2: Hapus tag Mingguan dari Kebijakan Cadangan
```powershell
Edit-AzDataProtectionPolicyTagClientObject -Policy $pol -Name Weekly -RemoveRule
```

```output
DatasourceType            ObjectType
--------------            ----------
{Microsoft.Compute/disks} BackupPolicy
```

Perintah ini menghapus tag Mingguan dari kebijakan cadangan.

## PARAMETERS

### -Criteria
Kriteria yang akan dikaitkan dengan tag jadwal.
Untuk membangun, lihat bagian CATATAN untuk properti CRITERIA dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DataProtection.Models.Api20210701.IScheduleBasedBackupCriteria[]
Parameter Sets: updateTag
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama tag Jadwal.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DataProtection.Support.TagName
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Kebijakan
Objek Kebijakan Cadangan.
Untuk membangun, lihat bagian CATATAN untuk properti KEBIJAKAN dan membuat tabel hash.

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
Tentukan apakah akan menghapus tag dari objek kebijakan tertentu.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: RemoveTag
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


CRITERIA <IScheduleBasedBackupCriteria[]>: Kriteria yang akan dikaitkan dengan tag jadwal.
  - `ObjectType <String>`: Tipe objek tertentu - digunakan untuk deserialisasi
  - `[AbsoluteCriterion <AbsoluteMarker[]>]`: berisi nilai mutlak seperti "AllBackup" / "FirstOfDay" / "FirstOfWeek" / "FirstOfMonth" dan harus menjadi bagian dari Enum AbsoluteMarker
  - `[DaysOfMonth <IDay[]>]`: Ini adalah hari dalam sebulan dari 1 sampai 28 bulan terakhir yang bijaksana lainnya
    - `[Date <Int32?>]`: Tanggal bulan
    - `[IsLast <Boolean?>]`: Apakah Tanggal adalah tanggal terakhir bulan
  - `[DaysOfTheWeek <DayOfWeek[]>]`: Seharusnya hari Minggu/Senin/T..../Sabtu
  - `[MonthsOfYear <Month[]>]`: Seharusnya Januari/Februari/.../Desember
  - `[ScheduleTime <DateTime[]>]`: Daftar waktu jadwal untuk pencadangan
  - `[WeeksOfTheMonth <WeekNumber[]>]`: Seharusnya Pertama/Kedua/Ketiga/Keempat/Terakhir

KEBIJAKAN <IBackupPolicy>: Objek Kebijakan Cadangan.
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

