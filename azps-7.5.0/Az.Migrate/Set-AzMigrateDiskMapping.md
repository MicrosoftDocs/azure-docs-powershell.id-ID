---
external help file: ''
Module Name: Az.Migrate
online version: https://docs.microsoft.com/powershell/module/az.migrate/set-azmigratediskmapping
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Migrate/help/Set-AzMigrateDiskMapping.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Migrate/help/Set-AzMigrateDiskMapping.md
ms.openlocfilehash: 8b109407b9349ae931c6b4538df2c5c0507b8f20
ms.sourcegitcommit: 321c644cf2161807a71e1af318fc5c5311d22e25
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/25/2022
ms.locfileid: "145791658"
---
# Set-AzMigrateDiskMapping

## SYNOPSIS
Memperbarui pemetaan disk

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.migrate/set-azmigratediskmapping) untuk informasi terbaru.

## SYNTAX

```
Set-AzMigrateDiskMapping -DiskID <String> -DiskName <String> [<CommonParameters>]
```

## DESCRIPTION
Cmdlet Set-AzMigrateDiskMapping memperbarui pemetaan disk sumber yang terpasang pada server yang akan dimigrasikan

## EXAMPLES

### Contoh 1: Membuat disk
```powershell
Set-AzMigrateDiskMapping -DiskID "6000C294-1217-dec3-bc18-81f117220424" -DiskName "ContosoDisk_1"
```

```output
DiskId                               TargetDiskName
------                               --------------
6000C294-1217-dec3-bc18-81f117220424 ContosoDisk_1
```

Mendapatkan objek disk untuk memberikan input untuk Set-AzMigrateServerReplication

## PARAMETERS

### -DiskID
Menentukan ID disk yang terpasang pada server yang ditemukan yang akan dimigrasikan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DiskName
Menentukan nama disk terkelola yang akan dibuat.

```yaml
Type: System.String
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

### Microsoft.Azure.PowerShell.Cmdlets.Migrate.Models.Api20210210.IVMwareCbtUpdateDiskInput

## NOTES

ALIAS

## RELATED LINKS

