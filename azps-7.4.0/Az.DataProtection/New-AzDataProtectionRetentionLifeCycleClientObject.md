---
external help file: ''
Module Name: Az.DataProtection
online version: https://docs.microsoft.com/powershell/module/az.dataprotection/new-azdataprotectionretentionlifecycleclientobject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/New-AzDataProtectionRetentionLifeCycleClientObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/New-AzDataProtectionRetentionLifeCycleClientObject.md
ms.openlocfilehash: 86c7776f1e12d174d269c551929a0bf783d5faa0
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144678724"
---
# New-AzDataProtectionRetentionLifeCycleClientObject

## SYNOPSIS
Membuat objek Siklus Hidup baru

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.dataprotection/new-azdataprotectionretentionlifecycleclientobject) untuk informasi terbaru.

## SYNTAX

```
New-AzDataProtectionRetentionLifeCycleClientObject -SourceDataStore <DataStoreType>
 -SourceRetentionDurationCount <Int32> -SourceRetentionDurationType <DurationType> [-CopyOption <CopyOption>]
 [-TargetDataStore <DataStoreType>] [<CommonParameters>]
```

## DESCRIPTION
Membuat objek Siklus Hidup baru

## EXAMPLES

### Contoh 1: Membuat siklus hidup retensi harian
```powershell
New-AzDataProtectionRetentionLifeCycleClientObject -SourceDataStore OperationalStore -SourceRetentionDurationType Days -SourceRetentionDurationCount 30
```

```output
DeleteAfterDuration        : P30D
DeleteAfterObjectType      : AbsoluteDeleteOption
SourceDataStoreObjectType  : DataStoreInfoBase
SourceDataStoreType        : OperationalStore
TargetDataStoreCopySetting :
```

Perintah ini membuat objek siklus hidup yang menyimpan data cadangan di penyimpanan operasional selama 30 hari.

### Contoh 2: Membuat siklus hidup retensi mingguan.
```powershell
New-AzDataProtectionRetentionLifeCycleClientObject -SourceDataStore OperationalStore -SourceRetentionDurationType Weeks -SourceRetentionDurationCount 20
```

```output
DeleteAfterDuration        : P20W
DeleteAfterObjectType      : AbsoluteDeleteOption
SourceDataStoreObjectType  : DataStoreInfoBase
SourceDataStoreType        : OperationalStore
TargetDataStoreCopySetting :
```

Perintah ini membuat objek siklus hidup yang menyimpan data cadangan di penyimpanan operasional selama 20 minggu.

## PARAMETERS

### -CopyOption
CopyOption

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DataProtection.Support.CopyOption
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceDataStore
Datastore Sumber

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DataProtection.Support.DataStoreType
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceRetentionDurationCount
Jumlah Durasi Retensi

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceRetentionDurationType
Jenis Durasi Retensi

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DataProtection.Support.DurationType
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetDataStore
Target Datastore

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DataProtection.Support.DataStoreType
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DataProtection.Models.Api20210701.ISourceLifeCycle

## NOTES

ALIAS

## RELATED LINKS

