---
external help file: ''
Module Name: Az.DataProtection
online version: https://docs.microsoft.com/powershell/module/az.dataprotection/edit-azdataprotectionpolicytriggerclientobject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/Edit-AzDataProtectionPolicyTriggerClientObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/Edit-AzDataProtectionPolicyTriggerClientObject.md
ms.openlocfilehash: 256ea5a4fd42639a9c3d7db2d9f372149a99220f
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141788666"
---
# Edit-AzDataProtectionPolicyTriggerClientObject

## SYNOPSIS
Pembaruan Jadwal pencadangan kebijakan cadangan yang sudah ada.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.dataprotection/edit-azdataprotectionpolicytriggerclientobject) untuk informasi terbaru.

## SYNTAX

```
Edit-AzDataProtectionPolicyTriggerClientObject -Policy <IBackupPolicy> -Schedule <String[]>
 [<CommonParameters>]
```

## DESCRIPTION
Pembaruan Jadwal pencadangan kebijakan cadangan yang sudah ada.

## EXAMPLES

### Contoh 1: Tambahkan Jadwal harian ke aturan Azure Backup.
```powershell
PS C:\> $schedule = New-AzDataProtectionPolicyTriggerScheduleClientObject -ScheduleDays (get-date) -IntervalType Daily -IntervalCount 1
PS C:\> Edit-AzDataProtectionPolicyTriggerClientObject -Policy $pol -Schedule $schedule

DatasourceType            ObjectType
--------------            ----------
{Microsoft.Compute/disks} BackupPolicy
```

Perintah ini memperbarui jadwal pencadangan kebijakan tertentu untuk cadangan harian.

## PARAMETERS

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DataProtection.Models.Api20210701.IBackupPolicy

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


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

