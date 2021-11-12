---
external help file: Azs.Compute.Admin-help.xml
Module Name: Azs.Compute.Admin
online version: ''
schema: 2.0.0
ms.openlocfilehash: fbecbcb981b17c2e1291d57c9582bbd12265302fd2af4581a4db3e108099cd56
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132417166"
---
# Get-AzsComputeQuota

## SYNOPSIS
Mengembalikan kuota yang menentukan batas kuota untuk objek perhitungan.

## SYNTAX

### Daftar (Default)
```
Get-AzsComputeQuota [-Location <String>] [<CommonParameters>]
```

### Dapatkan
```
Get-AzsComputeQuota [-Name] <String> [-Location <String>] [<CommonParameters>]
```

### ResourceId
```
Get-AzsComputeQuota -ResourceId <String> [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan daftar kuota yang ada.

## EXAMPLES

### -------------------------- CONTOH 1 --------------------------
```
Get-AzsComputeQuota -Location 'local'
```

Dapatkan semua kuota perhitungan di lokasi tertentu.

### -------------------------- CONTOH 2 --------------------------
```
Get-AzsComputeQuota 'Default Quota'
```

Dapatkan kuota perhitungan tertentu.

## PARAMETERS

### -Lokasi
{{fill location description}}

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

### -Nama
Nama kuota.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

### ComputeQuotaObject

## CATATAN

## RELATED LINKS

