---
external help file: Azs.Update.Admin-help.xml
Module Name: Azs.Update.Admin
online version: ''
schema: 2.0.0
ms.openlocfilehash: d2a29dc62a190fce4a5a9b02d1d9cfe36bb141b1ef26276621c72bd9f0861621
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132415992"
---
# Get-AzsUpdateLocation

## SYNOPSIS
Dapatkan daftar lokasi pembaruan.

## SYNTAX

### Daftar (Default)
```
Get-AzsUpdateLocation [-ResourceGroupName <String>] [<CommonParameters>]
```

### Dapatkan
```
Get-AzsUpdateLocation [-Name <String>] [-ResourceGroupName <String>] [<CommonParameters>]
```

### ResourceId
```
Get-AzsUpdateLocation -ResourceId <String> [<CommonParameters>]
```

## DESCRIPTION
Dapatkan daftar lokasi pembaruan. Lokasi yang dikembalikan bisa digunakan untuk mendapatkan pembaruan yang tersedia di lokasi tertentu menggunakan Get-AzsUpdate.

## EXAMPLES

### -------------------------- CONTOH 1 --------------------------
```
Get-AzsUpdateLocation
```

Dapatkan daftar lokasi pembaruan.

## PARAMETERS

### -Nama
Nama lokasi pembaruan.

```yaml
Type: String
Parameter Sets: Get
Aliases: Location

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
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

### Microsoft.AzureStack.Management.Update.Admin.Models.UpdateLocation

## CATATAN

## RELATED LINKS

