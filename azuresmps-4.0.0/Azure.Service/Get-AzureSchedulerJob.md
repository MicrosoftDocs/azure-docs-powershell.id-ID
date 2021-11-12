---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: 8EED9813-5106-4D6C-B869-97BCBD7845AC
online version: ''
schema: 2.0.0
ms.openlocfilehash: aedae85d848e382ace2324b27669282e9438ae12
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132422928"
---
# Get-AzureSchedulerJob

## SYNOPSIS
Mendapatkan daftar pekerjaan penjadwal atau pekerjaan penjadwal tertentu.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureSchedulerJob -Location <String> -JobCollectionName <String> [-JobName <String>] [-JobState <String>]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Topik ini menguraikan cmdlet dalam modul Microsoft Azure PowerShell versi 0.8.10.
Untuk mendapatkan versi modul yang Anda gunakan, di konsol Azure PowerShell, ketik `(Get-Module -Name Azure).Version` .

Cmdlet **Get-AzureSchedulerJobCollection** mendapatkan daftar pekerjaan penjadwal atau pekerjaan penjadwal tertentu.

## EXAMPLES

### Contoh 1: Dapatkan semua pekerjaan dalam koleksi
```
PS C:\> Get-AzureSchedulerJob -Location "North Central US" -JobCollectionName "JobCollection01"
```

Perintah ini mendapatkan pekerjaan penjadwal yang merupakan bagian dari kumpulan pekerjaan bernama JobCollection01.

### Contoh 2: Mendapatkan pekerjaan bernama
```
PS C:\> Get-AzureSchedulerJob -Location "North Central US" -JobCollectionName "JobCollection01" -JobName "Job01"
```

Perintah ini mendapatkan pekerjaan yang bernama Job01 dari kumpulan bernama JobCollection01 di lokasi yang ditentukan.

### Contoh 3: Mendapatkan pekerjaan dinonaktifkan dalam koleksi
```
PS C:\> Get-AzureSchedulerJobCollection -Location "North Central US" -JobCollectionName "JobCollection01" -JobState "Disabled"
```

Perintah ini akan menonaktifkan semua pekerjaan penjadwal yang merupakan bagian dari JobCollection01 dalam lokasi yang ditentukan.

## PARAMETERS

### -JobCollectionName
Menentukan nama koleksi yang berisi tugas penjadwal yang akan datang.

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

### -JobName
Menentukan nama pekerjaan penjadwal yang akan mendapatkan.

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

### -JobState
Menentukan status pekerjaan penjadwal untuk mendapatkan.
Nilai yang dapat diterima untuk parameter ini adalah:

- Diaktifkan
- Dinonaktifkan
- Disalahkan
- Selesai

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

### -Lokasi
Menentukan nama lokasi yang menjadi host layanan awan.
Nilai yang dapat diterima untuk parameter ini adalah:

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

[Remove-AzureSchedulerJob](./Remove-AzureSchedulerJob.md)


