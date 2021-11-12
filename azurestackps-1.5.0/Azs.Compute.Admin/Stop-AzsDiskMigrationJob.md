---
external help file: Azs.Compute.Admin-help.xml
Module Name: Azs.Compute.Admin
online version: ''
schema: 2.0.0
ms.openlocfilehash: 2cc0c67c0eba9ec5551ca9f765af82078486601099cb3248515cec8e1d63f47e
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132417600"
---
# Stop-AzsDiskMigrationJob

## SYNOPSIS
Membatalkan pekerjaan migrasi disk terkelola.

## SYNTAX

```
Stop-AzsDiskMigrationJob [[-Location] <String>] [[-Name] <String>] [<CommonParameters>]
```

## DESCRIPTION
Membatalkan pekerjaan migrasi disk.

## EXAMPLES

### -------------------------- CONTOH 1 --------------------------
```
Stop-AzsDiskMigrationJob -Location local -MigrationId $migration.MigrationId
```

Membatalkan pekerjaan migrasi disk terkelola.

## PARAMETERS

### -Lokasi
Lokasi sumber daya.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama guid pekerjaan migrasi.

```yaml
Type: String
Parameter Sets: (All)
Aliases: MigrationId

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

### Microsoft.AzureStack.Management.Compute.Admin.Models.DiskMigrationJob

## CATATAN

## RELATED LINKS

