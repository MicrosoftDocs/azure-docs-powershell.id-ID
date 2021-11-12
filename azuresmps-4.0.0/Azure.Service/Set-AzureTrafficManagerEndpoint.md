---
external help file: Microsoft.WindowsAzure.Commands.TrafficManager.dll-Help.xml
ms.assetid: FAEA7859-7E58-4343-AD57-7EFC0D87432E
online version: ''
schema: 2.0.0
ms.openlocfilehash: 531d298dd3a1a96fab47c5ca2c1d275b6eaa2f8b
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132422052"
---
# Set-AzureTrafficManagerEndpoint

## SYNOPSIS
Memperbarui properti titik akhir di Traffic Manager terkait.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Set-AzureTrafficManagerEndpoint -DomainName <String> [-Location <String>] [-Type <String>] [-Status <String>]
 [-Weight <Int32>] [-MinChildEndpoints <Int32>] -TrafficManagerProfile <IProfileWithDefinition>
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureTrafficManagerEndpoint** memperbarui properti titik akhir di profil Microsoft Azure Traffic Manager.
Jika titik akhir tidak ada di profil saat ini, cmdlet ini akan membuatnya.
Setelah menambahkan titik akhir, kirim hasilnya ke cmdlet **Set-AzureTrafficManagerProfile** menggunakan operator pipeline.
Cmdlet tersebut tersambung ke Azure untuk menyimpan perubahan Anda.

## EXAMPLES

### Contoh 1: Memperbarui titik akhir untuk profil
```
PS C:\>$TrafficManagerProfile = Get-AzureTrafficManagerProfile -Name "ContosoProfile"
PS C:\> Set-AzureTrafficManagerEndpoint -TrafficManagerProfile $TrafficManagerProfile -DomainName "ContosoApp02.cloudapp.net" -Status "Enabled" -Type "CloudService" -Weight 2 -Location myLocation | Set-AzureTrafficManagerProfile
```

Perintah pertama menggunakan cmdlet **Get-AzureTrafficManagerProfile** untuk mendapatkan profil bernama ContosoProfile, lalu menyimpannya di variabel $TrafficManagerProfile tertentu.

Perintah kedua memperbarui titik akhir di profil Traffic Manager yang disimpan di $TrafficManagerProfile.
Titik akhir memiliki nama domain ContosoApp02.cloudapp.net.
Perintah juga menentukan status, tipe, bobot, dan lokasi titik akhir.
Perintah meneruskan profil yang diubah ke cmdlet **Set-AzureTrafficManagerProfile** agar tersambung ke Azure untuk menyimpan perubahan Anda.

## PARAMETERS

### -DomainName
Menentukan nama domain titik akhir untuk diubah.

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

### -Lokasi
Menentukan lokasi titik akhir yang menambahkan cmdlet.
Ini harus merupakan lokasi Azure.

Parameter ini harus berisi nilai untuk titik akhir tipe "Any" atau tipe "TrafficManager" di profil yang memiliki metode keseimbangan muat yang disetel ke "Kinerja".
Nilai yang mungkin ada adalah nama kawasan Azure, seperti yang tercantum di  https://azure.microsoft.com/regions/https://azure.microsoft.com/regions/ .

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

### -MinChildEndpoints
Menentukan jumlah minimum titik akhir profil bertumpuk harus online agar titik akhir ini dapat dianggap online.

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

### -Profil
Menentukan profil Azure yang akan dibaca cmdlet ini. Jika Anda tidak menentukan profil, cmdlet ini akan membaca dari profil default lokal.

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

### -Status
Menentukan status titik akhir pemantauan.
Nilai valid adalah: 

- Diaktifkan
- Dinonaktifkan

Jika menentukan nilai Diaktifkan, Traffic Manager akan memantau titik akhir dan metode keseimbangan muat mempertimbangkannya saat mengelola lalu lintas.

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

### -TrafficManagerProfile
Menentukan objek Traffic Manager profil yang ingin anda ubah titik akhirnya.

```yaml
Type: IProfileWithDefinition
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Tipe
Menentukan tipe titik akhir.
Nilai valid adalah: 

- CloudService
- AzureWebsite
- TrafficManager

- Apa pun 

Jika ada lebih dari satu titik akhir AzureWebsite, titik akhir harus berada di pusat data yang berbeda.

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

### -Bobot
Menentukan bobot titik akhir yang menambahkan cmdlet.
Rentang nilai yang valid untuk parameter ini adalah \[ 1.1000 \] .

Parameter ini hanya digunakan untuk kebijakan keseimbangan muat RoundRobin.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

### Microsoft.WindowsAzure.Commands.Utilities.TrafficManager.Models.IProfileWithDefinition
Cmdlet ini menghasilkan objek Traffic Manager profil baru, yang berisi informasi tentang profil yang diperbarui.

## CATATAN

## RELATED LINKS

[Add-AzureTrafficManagerEndpoint](./Add-AzureTrafficManagerEndpoint.md)

[Remove-AzureTrafficManagerEndpoint](./Remove-AzureTrafficManagerEndpoint.md)

[Get-AzureTrafficManagerProfile](./Get-AzureTrafficManagerProfile.md)

[Set-AzureTrafficManagerProfile](./Set-AzureTrafficManagerProfile.md)


