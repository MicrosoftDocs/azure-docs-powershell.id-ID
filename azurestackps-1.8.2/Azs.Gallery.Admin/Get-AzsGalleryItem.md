---
external help file: Azs.Gallery.Admin-help.xml
Module Name: Azs.Gallery.Admin
online version: ''
schema: 2.0.0
ms.openlocfilehash: 0fa95e34c6a220a496a79f7a72c65c222f1376f1
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142786258"
---
# Get-AzsGalleryItem

## SYNOPSIS
Mencantumkan item galeri.

## SYNTAX

### Daftar (Default)
```
Get-AzsGalleryItem [<CommonParameters>]
```

### Mendapatkan
```
Get-AzsGalleryItem [-Name] <String> [<CommonParameters>]
```

## DESCRIPTION
Dapatkan daftar item galeri yang tersedia di Azure Stack Marketplace

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

Dapatkan item galeri berdasarkan nama.

## PARAMETERS

### -Nama
Identitas item galeri.
Menyertakan nama penerbit, nama item, dan mungkin menyertakan versi yang dipisahkan oleh karakter titik.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.AzureStack.Management.Gallery.Admin.Models.GalleryItem

## NOTES

## RELATED LINKS
