---
external help file: ''
Module Name: Az.DataProtection
online version: https://docs.microsoft.com/powershell/module/az.dataprotection/edit-azdataprotectionpolicytagclientobject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/Edit-AzDataProtectionPolicyTagClientObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/Edit-AzDataProtectionPolicyTagClientObject.md
ms.openlocfilehash: e5e34bbcda3c36c7f01de666facb0d4a27325999
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144656336"
---
# Edit-AzDataProtectionPolicyTagClientObject

## SYNOPSIS
Menambahkan atau menghapus tag jadwal dalam kebijakan pencadangan yang ada.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.dataprotection/edit-azdataprotectionpolicytagclientobject) untuk informasi terbaru.

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
Menambahkan atau menghapus tag jadwal dalam kebijakan pencadangan yang ada.

## EXAMPLES

### Contoh 1: Menambahkan tag Mingguan ke Kebijakan Pencadangan
```powershell
$criteria = New-AzDataProtectionPolicyTagCriteriaClientObject -AbsoluteCriteria FirstOfWeek
Edit-AzDataProtectionPolicyTagClientObject -Policy $pol -Name Weekly -Criteria $criteria
```

```output
DatasourceType            ObjectType
--------------            ----------
{Microsoft.Compute/disks} BackupPolicy
```

Perintah ini menambahkan tag mingguan ke kebijakan pencadangan yang diberikan

### Contoh 2: Hapus tag Mingguan dari Kebijakan Pencadangan
```powershell
Edit-AzDataProtectionPolicyTagClientObject -Policy $pol -Name Weekly -RemoveRule
```

```output
DatasourceType            ObjectType
--------------            ----------
{Microsoft.Compute/disks} BackupPolicy
```

Perintah ini menghapus tag Mingguan dari kebijakan pencadangan.

## PARAMETERS

### -Kriteria
Kriteria yang akan dikaitkan dengan tag jadwal.
Untuk membuat, lihat bagian CATATAN untuk properti CRITERIA dan membuat tabel hash.

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

### -Name
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
Objek Kebijakan Pencadangan.
Untuk membuat, lihat bagian CATATAN untuk properti POLICY dan membuat tabel hash.

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
Tentukan apakah akan menghapus tag dari objek kebijakan yang diberikan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DataProtection.Models.Api20210701.IBackupPolicy

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


KRITERIA <IScheduleBasedBackupCriteria[]>: Kriteria yang akan dikaitkan dengan tag jadwal.
  - `ObjectType <String>`: Jenis objek tertentu - digunakan untuk deserialisasi
  - `[AbsoluteCriterion <AbsoluteMarker[]>]`: berisi nilai absolut seperti "AllBackup" / "FirstOfDay" / "FirstOfWeek" / "FirstOfMonth" dan harus menjadi bagian dari enum AbsoluteMarker
  - `[DaysOfMonth <IDay[]>]`: Ini adalah hari dalam sebulan dari 1 hingga 28 bijaksana lainnya bulan lalu
    - `[Date <Int32?>]`: Tanggal bulan
    - `[IsLast <Boolean?>]`: Apakah Tanggal adalah tanggal terakhir bulan
  - `[DaysOfTheWeek <DayOfWeek[]>]`: Seharusnya Hari Minggu/Senin/T..../Sabtu
  - `[MonthsOfYear <Month[]>]`: Seharusnya Januari/Februari/....../Desember
  - `[ScheduleTime <DateTime[]>]`: Daftar waktu jadwal untuk pencadangan
  - `[WeeksOfTheMonth <WeekNumber[]>]`: Seharusnya Pertama/Detik/Ketiga/Keempat/Terakhir

KEBIJAKAN <IBackupPolicy>: Objek Kebijakan Pencadangan.
  - `DatasourceType <String[]>`: Jenis sumber data untuk manajemen cadangan
  - `ObjectType <String>`: 
  - `PolicyRule <IBasePolicyRule[]>`: Kamus aturan kebijakan yang berisi aturan untuk setiap jenis cadangan yaitu Penuh/Inkremental/Logs dll
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

