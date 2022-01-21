---
external help file: Azs.Gallery.Admin-help.xml
Module Name: Azs.Gallery.Admin
online version: ''
schema: 2.0.0
ms.openlocfilehash: 0fa95e34c6a220a496a79f7a72c65c222f1376f1
ms.sourcegitcommit: 1cf30f43dda849e046415dd10e55625f12ef21c4
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/09/2021
ms.locfileid: "136580563"
---
# Get-AzsGalleryItem

## SYNOPSIS
Mencantumkan item galeri.

## SYNTAX

### Daftar (Default)
```
Get-AzsGalleryItem [<CommonParameters>]
```

### Dapatkan
```
Get-AzsGalleryItem [-Name] <String> [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan daftar item galeri yang tersedia di Azure Stack Marketplace

## EXAMPLES

### CONTOH 1
```
Get-AzsGalleryItem
```

Item galeri daftar.

### CONTOH 2
```
Get-AzsGalleryItem -Name 'microsoft.vmss.1.3.6'
```

Dapatkan item galeri menurut nama.

## PARAMETERS

### -Nama
Identitas item galeri.
Menyertakan nama penerbit, nama item, dan mungkin menyertakan versi yang dipisahkan oleh karakter periode.

```yaml
Type: String
Parameter Sets: Get
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

### Microsoft.AzureStack.Management.Gallery.Admin.Models.GalleryItem

## CATATAN

## RELATED LINKS
