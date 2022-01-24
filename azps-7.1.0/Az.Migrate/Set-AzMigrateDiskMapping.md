---
external help file: ''
Module Name: Az.Migrate
online version: https://docs.microsoft.com/powershell/module/az.migrate/set-azmigratediskmapping
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Migrate/help/Set-AzMigrateDiskMapping.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Migrate/help/Set-AzMigrateDiskMapping.md
ms.openlocfilehash: 0d8ea2a7063cf43869530bb5006738065b67749c
ms.sourcegitcommit: e109cc5320478db6aa8a52d49996b133007a65b9
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 01/12/2022
ms.locfileid: "136702005"
---
# Set-AzMigrateDiskMapping

## SYNOPSIS
Memperbarui pemetaan disk

## SYNTAX

```
Set-AzMigrateDiskMapping -DiskID <String> -DiskName <String> [<CommonParameters>]
```

## DESCRIPTION
Cmdlet Set-AzMigrateDiskMapping memperbarui pemetaan disk sumber yang terhubung ke server untuk dimigrasi

## EXAMPLES

### Contoh 1: Buat disk
```powershell
PS C:\> Set-AzMigrateDiskMapping -DiskID "6000C294-1217-dec3-bc18-81f117220424" -DiskName "ContosoDisk_1"

DiskId                               TargetDiskName
------                               --------------
6000C294-1217-dec3-bc18-81f117220424 ContosoDisk_1
```

Dapatkan objek disk untuk menyediakan input bagi Set-AzMigrateServerReplication

## PARAMETERS

### -DiskID
Menentukan ID disk dari disk yang terhubung ke server yang ditemukan untuk dimigrasikan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Migrate.Models.Api20210210.IVMwareCbtUpdateDiskInput

## CATATAN

ALIAS

## RELATED LINKS

