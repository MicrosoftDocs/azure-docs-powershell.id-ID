---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: 8EED9813-5106-4D6C-B869-97BCBD7845AC
online version: ''
schema: 2.0.0
ms.openlocfilehash: aedae85d848e382ace2324b27669282e9438ae12
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142313485"
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
Topik ini menjelaskan cmdlet dalam versi 0.8.10 modul Microsoft Azure PowerShell.
Untuk mendapatkan versi modul yang Anda gunakan, di konsol Azure PowerShell, ketik .`(Get-Module -Name Azure).Version`

Cmdlet **Get-AzureSchedulerJobCollection** mendapatkan daftar pekerjaan penjadwal atau pekerjaan penjadwal tertentu.

## EXAMPLES

### Contoh 1: Dapatkan semua pekerjaan dalam koleksi
```
PS C:\> Get-AzureSchedulerJob -Location "North Central US" -JobCollectionName "JobCollection01"
```

Perintah ini mendapatkan pekerjaan penjadwal yang merupakan bagian dari koleksi pekerjaan bernama JobCollection01.

### Contoh 2: Dapatkan pekerjaan bernama
```
PS C:\> Get-AzureSchedulerJob -Location "North Central US" -JobCollectionName "JobCollection01" -JobName "Job01"
```

Perintah ini mendapatkan pekerjaan bernama Job01 dari koleksi bernama JobCollection01 di lokasi yang ditentukan.

### Contoh 3: Mendapatkan pekerjaan yang dinonaktifkan dalam koleksi
```
PS C:\> Get-AzureSchedulerJobCollection -Location "North Central US" -JobCollectionName "JobCollection01" -JobState "Disabled"
```

Perintah ini mendapatkan semua pekerjaan penjadwal yang dinonaktifkan yang merupakan bagian dari JobCollection01 di lokasi yang ditentukan.

## PARAMETERS

### -JobCollectionName
Menentukan nama kumpulan yang berisi tugas penjadwal untuk didapatkan.

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
Menentukan nama pekerjaan penjadwal yang akan didapatkan.

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
Menentukan status pekerjaan penjadwal yang akan didapatkan.
Nilai yang dapat diterima untuk parameter ini adalah:

- Diaktifkan
- Tamu penyandang cacat
- Gagal
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

- Di mana saja Asia
- Di mana saja Eropa
- Di mana saja AS
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
Menentukan profil Azure tempat cmdlet ini dibaca.
Jika Anda tidak menentukan profil, cmdlet ini akan dibaca dari profil default lokal.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Hapus-AzureSchedulerJob](./Remove-AzureSchedulerJob.md)


