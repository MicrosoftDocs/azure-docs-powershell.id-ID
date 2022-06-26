---
external help file: ''
Module Name: Az.DataProtection
online version: https://docs.microsoft.com/powershell/module/az.dataprotection/edit-azdataprotectionpolicytriggerclientobject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/Edit-AzDataProtectionPolicyTriggerClientObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/Edit-AzDataProtectionPolicyTriggerClientObject.md
ms.openlocfilehash: b7997a216b7d794b3b1d34406a24dc9d15853a54
ms.sourcegitcommit: 5df8b100721844736630242c724da453a2168434
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/26/2022
ms.locfileid: "146592528"
---
# Edit-AzDataProtectionPolicyTriggerClientObject

## SYNOPSIS
Updates Jadwal pencadangan dari kebijakan pencadangan yang ada.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.dataprotection/edit-azdataprotectionpolicytriggerclientobject) untuk informasi terbaru.

## SYNTAX

```
Edit-AzDataProtectionPolicyTriggerClientObject -Policy <IBackupPolicy> -Schedule <String[]>
 [<CommonParameters>]
```

## DESCRIPTION
Updates Jadwal pencadangan dari kebijakan pencadangan yang ada.

## EXAMPLES

### Contoh 1: Tambahkan jadwal Harian ke aturan Azure Backup.
```powershell
$schedule = New-AzDataProtectionPolicyTriggerScheduleClientObject -ScheduleDays (Get-Date) -IntervalType Daily -IntervalCount 1
Edit-AzDataProtectionPolicyTriggerClientObject -Policy $pol -Schedule $schedule
```

```output
DatasourceType            ObjectType
--------------            ----------
{Microsoft.Compute/disks} BackupPolicy
```

Perintah ini memperbarui jadwal pencadangan kebijakan yang diberikan ke pencadangan harian.

## PARAMETERS

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

### -Jadwal
Jadwalkan untuk dikaitkan dengan kebijakan pencadangan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DataProtection.Models.Api20210701.IBackupPolicy

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


KEBIJAKAN `<IBackupPolicy>`: Objek Kebijakan Pencadangan.
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

