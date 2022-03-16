---
external help file: ''
Module Name: Az.DataProtection
online version: https://docs.microsoft.com/powershell/module/az.dataprotection/edit-azdataprotectionpolicytriggerclientobject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/Edit-AzDataProtectionPolicyTriggerClientObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/Edit-AzDataProtectionPolicyTriggerClientObject.md
ms.openlocfilehash: 256ea5a4fd42639a9c3d7db2d9f372149a99220f
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140058143"
---
# Edit-AzDataProtectionPolicyTriggerClientObject

## SYNOPSIS
Pembaruan Jadwal pencadangan kebijakan pencadangan yang sudah ada.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.dataprotection/edit-azdataprotectionpolicytriggerclientobject) untuk informasi terkini.

## SYNTAX

```
Edit-AzDataProtectionPolicyTriggerClientObject -Policy <IBackupPolicy> -Schedule <String[]>
 [<CommonParameters>]
```

## DESCRIPTION
Pembaruan Jadwal pencadangan kebijakan pencadangan yang sudah ada.

## EXAMPLES

### Contoh 1: Tambahkan jadwal Harian ke aturan Cadangan Azure.
```powershell
PS C:\> $schedule = New-AzDataProtectionPolicyTriggerScheduleClientObject -ScheduleDays (get-date) -IntervalType Daily -IntervalCount 1
PS C:\> Edit-AzDataProtectionPolicyTriggerClientObject -Policy $pol -Schedule $schedule

DatasourceType            ObjectType
--------------            ----------
{Microsoft.Compute/disks} BackupPolicy
```

Perintah ini memperbarui jadwal pencadangan kebijakan yang diberikan untuk pencadangan harian.

## PARAMETERS

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

### -Schedule
Jadwalkan untuk dikaitkan ke kebijakan pencadangan.

```yaml
Type: System.String[]
Parameter Sets: (All)
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

