---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: D4349562-1392-44B6-9353-6231F0CB5C51
online version: ''
schema: 2.0.0
ms.openlocfilehash: 399da4221c75f9f410f31e0e56d46d812e4ed319
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132423202"
---
# Remove-AzureSchedulerJobCollection

## SYNOPSIS
Menghapus kumpulan pekerjaan penjadwal.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Remove-AzureSchedulerJobCollection [-Force] [-Location <String>] -JobCollectionName <String>
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Topik ini menguraikan cmdlet dalam modul Microsoft Azure PowerShell versi 0.8.10.
Untuk mendapatkan versi modul yang Anda gunakan, di konsol Azure PowerShell, ketik `(Get-Module -Name Azure).Version` .

Cmdlet **Remove-AzureSchedulerJobCollection** menghapus kumpulan pekerjaan penjadwal dan pekerjaan apa pun di bawah kumpulan itu.

## EXAMPLES

### Contoh 1: Menghapus kumpulan pekerjaan untuk lokasi
```
PS C:\> Remove-AzureSchedulerJobCollection -Location "North Central US" -JobCollectionName "JobCollection01"
```

Perintah ini menghapus kumpulan pekerjaan penjadwal bernama JobCollection01 di lokasi AS Pusat Utara.
Perintah juga menghapus pekerjaan di bawah JobCollection01.

### Contoh 2: Menghapus lokasi pekerjaan
```
PS C:\> Remove-AzureSchedulerJobCollection -JobCollectionName "JobCollection02"
```

Perintah ini menghapus kumpulan pekerjaan penjadwal bernama JobCollection02.
Perintah tersebut juga menghapus pekerjaan di bawah JobCollection02.

## PARAMETERS

### -Force
Menunjukkan bahwa cmdlet ini menghapus kumpulan pekerjaan penjadwal tanpa meminta konfirmasi Anda.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobCollectionName
Menentukan nama kumpulan pekerjaan penjadwal untuk dihapus.

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

[New-AzureSchedulerJobCollection](./New-AzureSchedulerJobCollection.md)

[Set-AzureSchedulerJobCollection](./Set-AzureSchedulerJobCollection.md)


