---
external help file: Azs.Update.Admin-help.xml
Module Name: Azs.Update.Admin
online version: ''
schema: 2.0.0
ms.openlocfilehash: f8819e4593c79d38e23354b4439bfe3146d1ae19333ea30c75c751772bc1af7d
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132417029"
---
# Get-AzsUpdate

## SYNOPSIS
Dapatkan daftar pembaruan yang tersedia.

## SYNTAX

### Daftar (Default)
```
Get-AzsUpdate [-Location <String>] [-ResourceGroupName <String>] [-Skip <Int32>] [-Top <Int32>]
 [<CommonParameters>]
```

### Dapatkan
```
Get-AzsUpdate [-Name] <String> [-Location <String>] [-ResourceGroupName <String>] [<CommonParameters>]
```

### ResourceId
```
Get-AzsUpdate -ResourceId <String> [<CommonParameters>]
```

## DESCRIPTION
Dapatkan daftar pembaruan yang tersedia. Pembaruan yang dikembalikan dari modul ini mungkin disambung ke 'Install-AzsUpdate', jika ada.

## EXAMPLES

### CONTOH 1
```
Get-AzsUpdate | ft
```

Dapatkan daftar pembaruan yang tersedia.

### CONTOH 2
```
Get-AzsUpdate -Name Microsoft1.0.180305.1
```

Dapatkan pembaruan tertentu.

## PARAMETERS

### -Nama
Nama pembaruan.

```yaml
Type: String
Parameter Sets: Get
Aliases: Update

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lokasi
Nama lokasi pembaruan.

```yaml
Type: String
Parameter Sets: List, Get
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Grup sumber daya sumber daya yang berada di bawahnya.

```yaml
Type: String
Parameter Sets: List, Get
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
Id sumber daya.

```yaml
Type: String
Parameter Sets: ResourceId
Aliases: id

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Lewati
Lewati item N pertama seperti yang ditentukan oleh nilai parameter.

```yaml
Type: Int32
Parameter Sets: List
Aliases:

Required: False
Position: Named
Default value: -1
Accept pipeline input: False
Accept wildcard characters: False
```

### -Top
Mengembalikan item N teratas seperti yang ditentukan oleh nilai parameter.
Berlaku setelah parameter -Skip.

```yaml
Type: Int32
Parameter Sets: List
Aliases:

Required: False
Position: Named
Default value: -1
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

### Microsoft.AzureStack.Management.Update.Admin.Models.Update

## CATATAN

## RELATED LINKS
