---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: DF12406D-894C-4732-95EE-D75524023B82
online version: ''
schema: 2.0.0
ms.openlocfilehash: a8f69f26a2e3ac471fef0959f5826fab66047e4c
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132421144"
---
# New-AzureSchedulerJobCollection

## SYNOPSIS
Membuat kumpulan pekerjaan penjadwal.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
New-AzureSchedulerJobCollection -Location <String> -JobCollectionName <String> [-Plan <String>]
 [-MaxJobCount <Int32>] [-Frequency <String>] [-Interval <Int32>] [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
Topik ini menguraikan cmdlet dalam modul Microsoft Azure PowerShell versi 0.8.10.
Untuk mendapatkan versi modul yang Anda gunakan, di konsol Azure PowerShell, ketik `(Get-Module -Name Azure).Version` .

Cmdlet **New-AzureSchedulerJobCollection** membuat kumpulan pekerjaan penjadwal.
Jika Anda tidak menentukan nilai untuk parameter *Rencanakan,* cmdlet membuat kumpulan pekerjaan standar.

## EXAMPLES

### Contoh 1: Membuat kumpulan pekerjaan penjadwal yang menyertakan nilai default
```
PS C:\> New-AzureSchedulerJobCollection -JobCollectionName "JobCollection01" -Location "North Central US" -Plan "Standard"
```

Perintah ini membuat kumpulan pekerjaan penjadwal standar bernama JobCollection01.
Kumpulan baru memiliki jumlah pekerjaan default dan nilai pengulangan maksimum untuk kumpulan pekerjaan penjadwal standar.

### Contoh 2: Membuat kumpulan pekerjaan penjadwal dengan nilai tertentu
```
PS C:\> New-AzureSchedulerJobCollection -JobCollectionName "JobCollection02" -Location "North Central US" -Frequency "Hour" -Interval 12 -MaxJobCount 30 -Plan "Standard"
```

Perintah ini membuat kumpulan pekerjaan penjadwal standar bernama JobCollection02.
Kumpulan baru memiliki maksimum jumlah pekerjaan 30 dan maksimum pengulangan 12 per jam.

## PARAMETERS

### -Frequency
Menentukan frekuensi maksimum yang dapat ditentukan pada pekerjaan apa pun dalam kumpulan pekerjaan penjadwal ini.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Interval
Menentukan interval pengulangan pada frekuensi yang ditentukan dengan menggunakan parameter *Frequency.*

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobCollectionName
Menentukan nama untuk kumpulan pekerjaan penjadwal baru.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Lokasi
Menentukan nama lokasi yang menjadi host layanan awan.
Nilai valid adalah: 

- Asia mana pun
- Eropa di mana saja
- US di mana saja
- Asia Timur
- AS Timur
- As Tengah Utara
- Eropa Utara
- As Tengah Selatan
- Asia Tenggara
- Eropa Barat
- AS Barat

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxJobCount
Menentukan jumlah maksimum pekerjaan yang bisa dibuat dalam kumpulan pekerjaan penjadwal.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Rencana
Menentukan paket kumpulan pekerjaan penjadwal.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Profil
Menentukan profil Azure yang akan dibaca cmdlet ini.
Jika Anda tidak menentukan profil, cmdlet ini akan membaca dari profil default lokal.

```yaml
Type: AzureSMProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
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

[Get-AzureSchedulerJobCollection](./Get-AzureSchedulerJobCollection.md)

[Remove-AzureSchedulerJobCollection](./Remove-AzureSchedulerJobCollection.md)

[Set-AzureSchedulerJobCollection](./Set-AzureSchedulerJobCollection.md)


