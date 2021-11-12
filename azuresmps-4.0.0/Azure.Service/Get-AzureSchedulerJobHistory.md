---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: 2BF5BDF8-3743-46FC-8E04-1A4EA920A2AF
online version: ''
schema: 2.0.0
ms.openlocfilehash: 2839752bc84bd763bc996b4b17aeb262b7227472
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132426282"
---
# Get-AzureSchedulerJobHistory

## SYNOPSIS
Mendapatkan riwayat pekerjaan penjadwal.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureSchedulerJobHistory -Location <String> -JobCollectionName <String> -JobName <String>
 [-JobStatus <String>] [-Profile <AzureSMProfile>] [-IncludeTotalCount] [-Skip <UInt64>] [-First <UInt64>]
 [<CommonParameters>]
```

## DESCRIPTION
Topik ini menguraikan cmdlet dalam modul Microsoft Azure PowerShell versi 0.8.10.
Untuk mendapatkan versi modul yang Anda gunakan, di konsol Azure PowerShell, ketik `(Get-Module -Name Azure).Version` .

Cmdlet **Get-AzureSchedulerJobHistory** mendapatkan riwayat pekerjaan penjadwal.

## EXAMPLES

### Contoh 1: Mendapatkan riwayat pekerjaan menggunakan namanya
```
PS C:\> Get-AzureSchedulerJobHistory -Location "North Central US" -JobCollectionName "JobCollection01" -JobName "Job01"
```

Perintah ini memperoleh riwayat pekerjaan bernama Pekerjaan01.
Pekerjaan tersebut termasuk dalam kumpulan pekerjaan bernama JobCollection01 di lokasi yang ditentukan.

### Contoh 2: Mendapatkan riwayat pekerjaan yang gagal menggunakan namanya
```
PS C:\> Get-AzureSchedulerJobHistory -Location "North Central US" -JobCollectionName "JobCollection01" -JobName "Job12" -JobStatus "Failed"
```

Perintah ini mendapatkan riwayat pekerjaan bernama Pekerjaan12 yang memiliki status Gagal.
Pekerjaan tersebut termasuk dalam kumpulan pekerjaan bernama JobCollection01 di lokasi yang ditentukan.

## PARAMETERS

### -First
Hanya mendapatkan jumlah objek yang ditentukan.
Masukkan jumlah objek yang akan dapatkan.

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncludeTotalCount
Melaporkan jumlah total objek dalam rangkaian data (bilangan bulat) diikuti dengan objek yang dipilih.
Jika cmdlet tidak dapat menentukan hitungan total, cmdlet menampilkan "Penghitungan total tidak diketahui." Bilangan bulat memiliki properti Accuracy yang menunjukkan keandalan nilai perhitungan total.
Nilai Akurasi berkisar dari 0,0 hingga 1,0 di mana 0,0 berarti bahwa cmdlet tidak bisa menghitung objek, 1,0 berarti bahwa hitungan tepat, dan nilai antara 0,0 dan 1,0 menunjukkan perkiraan yang semakin andal.

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

### -JobCollectionName
Menentukan nama kumpulan pekerjaan penjadwal.
Cmdlet ini mendapatkan riwayat pekerjaan bagi kumpulan yang ditentukan parameter ini.

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
Menentukan nama pekerjaan penjadwal yang akan mendapatkan riwayat.

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

### -JobStatus
Menentukan status pekerjaan penjadwal yang akan mendapatkan riwayat.
Nilai yang dapat diterima untuk parameter ini adalah:

- Selesai
- Gagal

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

### -Lewati
Mengabaikan jumlah objek tertentu lalu mendapatkan objek yang tersisa.
Masukkan jumlah objek yang akan dilewati.

```yaml
Type: UInt64
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Get-AzureSchedulerJob](./Get-AzureSchedulerJob.md)

[Get-AzureSchedulerJobCollection](./Get-AzureSchedulerJobCollection.md)


