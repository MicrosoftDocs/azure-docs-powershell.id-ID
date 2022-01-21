---
external help file: Azs.Compute.Admin-help.xml
Module Name: Azs.Compute.Admin
online version: ''
schema: 2.0.0
ms.openlocfilehash: 3e7eac7b9d23914aa909a111958d64cc9d4247d3
ms.sourcegitcommit: 1cf30f43dda849e046415dd10e55625f12ef21c4
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/09/2021
ms.locfileid: "136578410"
---
# Get-AzsVMExtension

## SYNOPSIS
Mengembalikan ekstensi gambar mesin virtual yang saat ini tersedia.

## SYNTAX

### Daftar (Default)
```
Get-AzsVMExtension [-Publisher <String>] [-Type <String>] [-Location <String>] [<CommonParameters>]
```

### Dapatkan
```
Get-AzsVMExtension -Publisher <String> -Type <String> -Version <String> [-Location <String>]
 [<CommonParameters>]
```

### ResourceId
```
Get-AzsVMExtension -ResourceId <String> [<CommonParameters>]
```

## DESCRIPTION
Mengembalikan ekstensi gambar mesin virtual.

## EXAMPLES

### -------------------------- CONTOH 1 --------------------------
```
Get-AzsVMExtension
```

Dapatkan semua ekstensi VM pada satu lokasi.

### -------------------------- CONTOH 2 --------------------------
```
Get-AzsVMExtension -Publisher "Microsoft" -Type "MicroExtension" -Version "0.1.0"
```

Dapatkan ekstensi VM tertentu.

## PARAMETERS

### -Lokasi
Lokasi sumber daya.

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

### -Publisher
Nama penerbit.

```yaml
Type: String
Parameter Sets: List
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: Get
Aliases: 

Required: True
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

### -Tipe
Tipe ekstensi.

```yaml
Type: String
Parameter Sets: List
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: String
Parameter Sets: Get
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Versi
Versi ekstensi gambar mesin virtual.

```yaml
Type: String
Parameter Sets: Get
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

### VmExtensionObject

## CATATAN

## RELATED LINKS

