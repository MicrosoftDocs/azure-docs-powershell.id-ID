---
external help file: Microsoft.WindowsAzure.Commands.TrafficManager.dll-Help.xml
ms.assetid: FAEA7859-7E58-4343-AD57-7EFC0D87432E
online version: ''
schema: 2.0.0
ms.openlocfilehash: 531d298dd3a1a96fab47c5ca2c1d275b6eaa2f8b
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142979471"
---
# Set-AzureTrafficManagerEndpoint

## SYNOPSIS
Memperbarui properti titik akhir dalam profil Traffic Manager.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Set-AzureTrafficManagerEndpoint -DomainName <String> [-Location <String>] [-Type <String>] [-Status <String>]
 [-Weight <Int32>] [-MinChildEndpoints <Int32>] -TrafficManagerProfile <IProfileWithDefinition>
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureTrafficManagerEndpoint** memperbarui properti titik akhir dalam profil Microsoft Azure Traffic Manager.
Jika titik akhir tidak ada di profil saat ini, cmdlet ini akan membuatnya.
Setelah menambahkan titik akhir, serahkan hasil ke cmdlet **Set-AzureTrafficManagerProfile** menggunakan operator pipeline.
Cmdlet tersebut tersambung ke Azure untuk menyimpan perubahan Anda.

## EXAMPLES

### Contoh 1: Memperbarui titik akhir untuk profil
```
PS C:\>$TrafficManagerProfile = Get-AzureTrafficManagerProfile -Name "ContosoProfile"
PS C:\> Set-AzureTrafficManagerEndpoint -TrafficManagerProfile $TrafficManagerProfile -DomainName "ContosoApp02.cloudapp.net" -Status "Enabled" -Type "CloudService" -Weight 2 -Location myLocation | Set-AzureTrafficManagerProfile
```

Perintah pertama menggunakan cmdlet **Get-AzureTrafficManagerProfile** untuk mendapatkan profil bernama ContosoProfile, lalu menyimpannya dalam variabel $TrafficManagerProfile.

Perintah kedua memperbarui titik akhir di profil Traffic Manager yang disimpan di $TrafficManagerProfile.
Titik akhir memiliki nama domain ContosoApp02.cloudapp.net.
Perintah juga menentukan status, tipe, berat, dan lokasi titik akhir.
Perintah melewati profil yang diubah ke cmdlet **Set-AzureTrafficManagerProfile** untuk menyambungkan ke Azure untuk menyimpan perubahan Anda.

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
Menentukan lokasi titik akhir yang ditambahkan cmdlet.
Lokasi ini harus berupa Azure.

Parameter ini harus berisi nilai untuk titik akhir dari tipe "Any" atau tipe "TrafficManager" dalam profil yang memiliki metode load balancing yang diatur ke "Performance".
Nilai yang memungkinkan adalah nama kawasan Azure, seperti yang tercantum di  https://azure.microsoft.com/regions/https://azure.microsoft.com/regions/.

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
Menentukan jumlah titik akhir minimum yang harus dimiliki profil bertumpuk secara online agar titik akhir ini dapat dipertimbangkan secara online.

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
Menentukan profil Azure tempat cmdlet ini dibaca. Jika Anda tidak menentukan profil, cmdlet ini akan dibaca dari profil default lokal.

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
Nilai yang valid adalah: 

- Diaktifkan
- Tamu penyandang cacat

Jika Anda menentukan nilai Diaktifkan, Traffic Manager memantau titik akhir dan metode penyeimbangan beban mempertimbangkannya saat mengelola lalu lintas.

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
Menentukan objek profil Traffic Manager untuk mengubah titik akhir.

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
Nilai yang valid adalah: 

- CloudService
- AzureWebsite
- TrafficManager

- Setiap 

Jika terdapat lebih dari satu titik akhir AzureWebsite, titik akhir harus berada di pusat data yang berbeda.

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

### -Berat
Menentukan berat titik akhir yang ditambahkan cmdlet.
Rentang nilai yang valid untuk parameter ini adalah \[1.1000\].

Parameter ini hanya digunakan untuk kebijakan penyeimbangan beban RoundRobin.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.WindowsAzure.Commands.Utilities.TrafficManager.Models.IProfileWithDefinition
Cmdlet ini menghasilkan objek profil Traffic Manager, yang berisi informasi tentang profil yang diperbarui.

## NOTES

## RELATED LINKS

[Add-AzureTrafficManagerEndpoint](./Add-AzureTrafficManagerEndpoint.md)

[Hapus-AzureTrafficManagerEndpoint](./Remove-AzureTrafficManagerEndpoint.md)

[Get-AzureTrafficManagerProfile](./Get-AzureTrafficManagerProfile.md)

[Set-AzureTrafficManagerProfile](./Set-AzureTrafficManagerProfile.md)


