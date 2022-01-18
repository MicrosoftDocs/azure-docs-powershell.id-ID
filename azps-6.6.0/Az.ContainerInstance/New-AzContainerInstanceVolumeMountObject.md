---
external help file: ''
Module Name: Az.ContainerInstance
online version: https://docs.microsoft.com/powershell/module/az.ContainerInstance/new-AzContainerInstanceVolumeMountObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/New-AzContainerInstanceVolumeMountObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/New-AzContainerInstanceVolumeMountObject.md
ms.openlocfilehash: 01c976bc8d4851f260d4c3c55f25dbdd13a57633
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/02/2021
ms.locfileid: "136157577"
---
# New-AzContainerInstanceVolumeMountObject

## SYNOPSIS
Membuat objek dalam memori untuk Jumlah Volume

## SYNTAX

```
New-AzContainerInstanceVolumeMountObject -MountPath <String> -Name <String> [-ReadOnly <Boolean>]
 [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk Jumlah Volume

## EXAMPLES

### Contoh 1: Menentukan volume yang terpasang pada contoh wadah
```powershell
PS C:\> New-AzContainerInstanceVolumeMountObject -Name 
"mnt" -MountPath "/mnt/azfile" -ReadOnly $true

MountPath   Name ReadOnly
---------   ---- --------
/mnt/azfile mnt  True
```

Perintah ini menentukan volume yang tersedia pada contoh wadah

## PARAMETERS

### -MountPath
Jalur di dalam wadah tempat volume akan terpasang.
Tidak boleh berisi titik dua (:).

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

### -Nama
Nama volume yang naik.

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

### -ReadOnly
Bendera yang menunjukkan apakah volume naik merupakan baca-saja.

```yaml
Type: System.Boolean
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

### Microsoft.Azure.PowerShell.Cmdlets.ContainerInstance.Models.Api20210301.VolumeMount

## CATATAN

ALIAS

## RELATED LINKS

