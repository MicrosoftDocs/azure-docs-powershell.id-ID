---
external help file: Azs.Fabric.Admin-help.xml
Module Name: Azs.Fabric.Admin
online version: ''
schema: 2.0.0
ms.openlocfilehash: d46be487796e3843b2c14ed13153b143fc9bd37232fdb8aa7438465639f98765
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132418065"
---
# Add-AzsScaleUnitNode

## SYNOPSIS
Membuat skala unit.

## SYNTAX

```
Add-AzsScaleUnitNode [-NodeList] <ScaleOutScaleUnitParameters[]> [[-ResourceGroupName] <String>]
 [-ScaleUnit] <String> [[-Location] <String>] [-AwaitStorageConvergence] [-AsJob] [<CommonParameters>]
```

## DESCRIPTION
Tambahkan node unit skala baru ke kluster unit skala Anda.

## EXAMPLES

### -------------------------- CONTOH 1 --------------------------
```
Add-AzsScaleUnitNode -NodeList $Nodes -ScaleUnit $ScaleUnitName
```

Menambahkan daftar node ke unit skala.

## PARAMETERS

### -AsJob
Jalankan asinkron sebagai pekerjaan dan kembalikan objek pekerjaan.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -AwaitStorageConvergence
Tunggu hingga replikasi penyimpanan selesai sebelum kembali ke keberhasilan.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lokasi
Lokasi sumber daya.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NodeList
Daftar data input yang memungkinkan penambahan rangkaian simpul unit skala.

```yaml
Type: ScaleOutScaleUnitParameters[]
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

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

### -ScaleUnit
Nama unit skala.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

