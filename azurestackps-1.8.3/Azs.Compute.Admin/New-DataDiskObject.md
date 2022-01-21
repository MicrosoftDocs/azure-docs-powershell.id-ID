---
external help file: Azs.Compute.Admin-help.xml
Module Name: Azs.Compute.Admin
online version: ''
schema: 2.0.0
ms.openlocfilehash: b37d41ae2ec772cc755436bc01c3c4009c9c30f5
ms.sourcegitcommit: 1cf30f43dda849e046415dd10e55625f12ef21c4
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/09/2021
ms.locfileid: "136578396"
---
# New-DataDiskObject

## SYNOPSIS
Membuat disk data yang digunakan untuk membuat gambar platform mesin virtual baru.

## SYNTAX

```
New-DataDiskObject [[-Lun] <Int32>] [[-Uri] <String>] [<CommonParameters>]
```

## DESCRIPTION
Membuat objek yang berisi informasi tentang disk data.

## EXAMPLES

### -------------------------- CONTOH 1 --------------------------
```
New-DataDiskObject -Lun 5 -URI test.blob.windows.net/disks/datadisk5.vhd
```

Membuat objek disk data baru.

## PARAMETERS

### -Lun
Nomor unit logika.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: 0
Accept pipeline input: False
Accept wildcard characters: False
```

### -Uri
Lokasi templat disk.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

