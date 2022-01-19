---
external help file: ''
Module Name: Az.DataProtection
online version: https://docs.microsoft.com/powershell/module/az.dataprotection/new-azdataprotectionretentionlifecycleclientobject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/New-AzDataProtectionRetentionLifeCycleClientObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataProtection/help/New-AzDataProtectionRetentionLifeCycleClientObject.md
ms.openlocfilehash: e2c57a5d8140f7f7659c8d7fe501bb37d48137a3
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136204854"
---
# New-AzDataProtectionRetentionLifeCycleClientObject

## SYNOPSIS
Membuat objek Siklus Hidup baru

## SYNTAX

```
New-AzDataProtectionRetentionLifeCycleClientObject -SourceDataStore <DataStoreType>
 -SourceRetentionDurationCount <Int32> -SourceRetentionDurationType <DurationType> [-CopyOption <CopyOption>]
 [-TargetDataStore <DataStoreType>] [<CommonParameters>]
```

## DESCRIPTION
Membuat objek Siklus Hidup baru

## EXAMPLES

### Contoh 1: Membuat siklus hidup penyimpanan harian
```powershell
PS C:\> New-AzDataProtectionRetentionLifeCycleClientObject -SourceDataStore OperationalStore -SourceRetentionDurationType Days -SourceRetentionDurationCount 30

DeleteAfterDuration        : P30D
DeleteAfterObjectType      : AbsoluteDeleteOption
SourceDataStoreObjectType  : DataStoreInfoBase
SourceDataStoreType        : OperationalStore
TargetDataStoreCopySetting :
```

Perintah ini membuat objek siklus hidup yang menyimpan data cadangan di penyimpanan operasional selama 30 hari.

### Contoh 2: Buat siklus hidup penyimpanan mingguan.
```powershell
PS C:\> New-AzDataProtectionRetentionLifeCycleClientObject -SourceDataStore OperationalStore -SourceRetentionDurationType Weeks -SourceRetentionDurationCount 20

DeleteAfterDuration        : P20W
DeleteAfterObjectType      : AbsoluteDeleteOption
SourceDataStoreObjectType  : DataStoreInfoBase
SourceDataStoreType        : OperationalStore
TargetDataStoreCopySetting :
```

Perintah ini membuat objek siklus hidup yang menyimpan data cadangan di toko operasional selama 20 minggu.

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
Penyimpanan Data Sumber

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
Jumlah Durasi Penyimpanan

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
Tipe Durasi Penyimpanan

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
Penyimpanan Data Target

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DataProtection.Models.Api20210701.ISourceLifeCycle

## CATATAN

ALIAS

## RELATED LINKS

