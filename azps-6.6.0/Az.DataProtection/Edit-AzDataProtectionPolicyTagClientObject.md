---
external help file: ''
Module Name: Az.DataProtection
online version: https://docs.microsoft.com/powershell/module/az.dataprotection/edit-azdataprotectionpolicytagclientobject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/Edit-AzDataProtectionPolicyTagClientObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/Edit-AzDataProtectionPolicyTagClientObject.md
ms.openlocfilehash: 79bc2eff51406c6a95b5eba81cb0c003e84f1860
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140107829"
---
# Edit-AzDataProtectionPolicyTagClientObject

## SYNOPSIS
Menambahkan atau menghapus tag jadwal dalam kebijakan pencadangan yang sudah ada.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.dataprotection/edit-azdataprotectionpolicytagclientobject) untuk informasi terkini.

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
Menambahkan atau menghapus tag jadwal dalam kebijakan pencadangan yang sudah ada.

## EXAMPLES

### Contoh 1: Tambahkan tag Mingguan ke Kebijakan Pencadangan
```powershell
PS C:\> $criteria = New-AzDataProtectionPolicyTagCriteriaClientObject -AbsoluteCriteria FirstOfWeek
PS C:\> Edit-AzDataProtectionPolicyTagClientObject -Policy $pol -Name Weekly -Criteria $criteria

DatasourceType            ObjectType
--------------            ----------
{Microsoft.Compute/disks} BackupPolicy
```

Perintah ini menambahkan tag mingguan ke kebijakan pencadangan tertentu

### Contoh 2: Hapus tag Weeky dari Kebijakan Cadangan
```powershell
PS C:\> Edit-AzDataProtectionPolicyTagClientObject -Policy $pol -Name Weekly -RemoveRule

DatasourceType            ObjectType
--------------            ----------
{Microsoft.Compute/disks} BackupPolicy
```

Perintah ini menghapus tag Mingguan dari kebijakan pencadangan.

## PARAMETERS

### -Criteria
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
Untuk membuat, lihat bagian CATATAN untuk properti KEBIJAKAN dan membuat tabel hash.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DataProtection.Models.Api20210701.IBackupPolicy

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


CRITERIA <IScheduleBasedBackupCriteria[]>: Kriteria yang akan dikaitkan dengan tag jadwal.
  - `ObjectType <String>`: Tipe objek spesifik - digunakan untuk deserialisasi
  - `[AbsoluteCriterion <AbsoluteMarker[]>]`: berisi nilai absolut seperti "AllBackup" / "FirstOfDay" / "FirstOfWeek" / "FirstOfMonth" dan harus menjadi bagian dari AbsoluteMarker enum
  - `[DaysOfMonth <IDay[]>]`: This is day of the month from 1 to 28 other wise last of month
    - `[Date <Int32?>]`: Tanggal dari bulan
    - `[IsLast <Boolean?>]`: Apakah Tanggal adalah tanggal terakhir bulan
  - `[DaysOfTheWeek <DayOfWeek[]>]`: Seharusnya Minggu/Senin/T..../Sabtu
  - `[MonthsOfYear <Month[]>]`: Seharusnya Bulan Januari/Februari/.../Desember
  - `[ScheduleTime <DateTime[]>]`: Daftar waktu jadwal untuk cadangan
  - `[WeeksOfTheMonth <WeekNumber[]>]`: Harus menjadi Pertama/Kedua/Ketiga/Keempat/Terakhir

KEBIJAKAN <IBackupPolicy>: Objek Kebijakan Pencadangan.
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

