---
external help file: Azs.Gallery.Admin-help.xml
Module Name: Azs.Gallery.Admin
online version: ''
schema: 2.0.0
ms.openlocfilehash: c706ae2bae500ced4a558244e2be49bc014bf304e2b3175de5791a8135543a1b
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132415159"
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
