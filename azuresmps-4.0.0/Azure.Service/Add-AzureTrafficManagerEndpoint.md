---
external help file: Microsoft.WindowsAzure.Commands.TrafficManager.dll-Help.xml
ms.assetid: CF1FC482-812D-4BAD-BA3A-D88E614A5165
online version: ''
schema: 2.0.0
ms.openlocfilehash: 0b8f097cc0d7e6b8ccf9712f8e909f8d32a5af74
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143044397"
---
# Add-AzureTrafficManagerEndpoint

## SYNOPSIS
Menambahkan titik akhir ke profil Traffic Manager.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Add-AzureTrafficManagerEndpoint -DomainName <String> [-Location <String>] -Type <String> -Status <String>
 [-Weight <Int32>] [-MinChildEndpoints <Int32>] -TrafficManagerProfile <IProfileWithDefinition>
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Add-AzureTrafficManagerEndpoint** menambahkan titik akhir ke profil Microsoft Azure Traffic Manager.
Setelah Anda menambahkan titik akhir, teruskan hasilnya ke cmdlet **Set-AzureTrafficManagerProfile** dengan menggunakan operator alur.
Cmdlet tersebut tersambung ke Azure untuk menyimpan perubahan Anda.

## EXAMPLES

### Contoh 1: Menambahkan titik akhir ke profil
```
PS C:\>$TrafficManagerProfile = Get-AzureTrafficManagerProfile -Name "ContosoProfile"
PS C:\> Add-AzureTrafficManagerEndpoint -TrafficManagerProfile $TrafficManagerProfile -DomainName "Contoso02App.cloudapp.net" -Status "Enabled" -Type "CloudService" | Set-AzureTrafficManagerProfile
```

Perintah pertama menggunakan cmdlet **Get-AzureTrafficManagerProfile** untuk mendapatkan profil bernama ContosoProfile, lalu menyimpannya dalam variabel $TrafficManagerProfile.

Perintah kedua menambahkan titik akhir ke profil Traffic Manager yang disimpan di $TrafficManagerProfile.
Titik akhir memiliki nama domain Contoso02App.couldapp.net.
Perintah juga menentukan apakah diaktifkan dan jenisnya.
Perintah meneruskan objek profil ke cmdlet **Set-AzureTrafficManagerProfile** untuk menyambungkan ke Azure untuk menyimpan perubahan Anda.

### Contoh 2: Menambahkan titik akhir yang memiliki lokasi dan berat tertentu
```
PS C:\>Add-AzureTrafficManagerEndpoint -TrafficManagerProfile ContosoTrafficManagerProfile -DomainName " Contoso02App.cloudapp.net" -Status Enabled -Type CloudService -Weight 2 -Location myLocation | Set-AzureTrafficManagerProfile
```

Perintah ini menambahkan titik akhir ke profil Traffic Manager.
Titik akhir memiliki nama domain Contoso02App.couldapp.net.
Perintah juga menentukan apakah diaktifkan dan jenisnya.
Perintah ini juga menentukan bobot dan lokasi untuk titik akhir.
Perintah meneruskan objek profil ke **Set-AzureTrafficManagerProfile** untuk menyambungkan ke Azure untuk menyimpan perubahan Anda.

## PARAMETERS

### -DomainName
Menentukan nama domain titik akhir yang akan ditambahkan.

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
Ini harus menjadi lokasi Azure.

Parameter ini harus berisi nilai untuk titik akhir jenis "Apa pun" atau jenis "TrafficManager" di profil yang memiliki metode penyeimbangan beban yang diatur ke "Performa".
Nilai yang mungkin adalah nama wilayah Azure, seperti yang tercantum di https://azure.microsoft.com/regions/.

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
Menentukan jumlah minimum titik akhir yang harus dimiliki profil berlapis secara online agar titik akhir ini dipertimbangkan secara online.

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
Menentukan profil Azure tempat cmdlet ini dibaca. Jika Anda tidak menentukan profil, cmdlet ini akan membaca dari profil default lokal.

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

- Aktif
- Nonaktifkan

Jika Anda menentukan nilai Diaktifkan, Traffic Manager memantau titik akhir dan metode penyeimbangan beban mempertimbangkannya saat mengelola lalu lintas.

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

### -TrafficManagerProfile
Menentukan objek profil Traffic Manager untuk menambahkan titik akhir.

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

### -Type
Menentukan jenis titik akhir.
Nilai yang valid adalah: 

- CloudService
- AzureWebsite
- TrafficManager

- Apa pun 

Jika ada lebih dari satu titik akhir AzureWebsite, titik akhir harus berada di pusat data yang berbeda.

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

### -Berat
Menentukan bobot titik akhir yang ditambahkan cmdlet.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.WindowsAzure.Commands.Utilities.TrafficManager.Models.IProfileWithDefinition
Cmdlet ini menghasilkan objek profil Traffic Manager, yang berisi informasi tentang profil yang diperbarui.

## NOTES

## RELATED LINKS

[Remove-AzureTrafficManagerEndpoint](./Remove-AzureTrafficManagerEndpoint.md)

[Set-AzureTrafficManagerEndpoint](./Set-AzureTrafficManagerEndpoint.md)

[Get-AzureTrafficManagerProfile](./Get-AzureTrafficManagerProfile.md)

[Set-AzureTrafficManagerProfile](./Set-AzureTrafficManagerProfile.md)


