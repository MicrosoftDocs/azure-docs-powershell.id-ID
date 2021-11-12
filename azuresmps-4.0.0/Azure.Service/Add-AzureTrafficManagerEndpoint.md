---
external help file: Microsoft.WindowsAzure.Commands.TrafficManager.dll-Help.xml
ms.assetid: CF1FC482-812D-4BAD-BA3A-D88E614A5165
online version: ''
schema: 2.0.0
ms.openlocfilehash: 0b8f097cc0d7e6b8ccf9712f8e909f8d32a5af74
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132424152"
---
# Add-AzureTrafficManagerEndpoint

## SYNOPSIS
Menambahkan titik akhir ke Traffic Manager profil.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Add-AzureTrafficManagerEndpoint -DomainName <String> [-Location <String>] -Type <String> -Status <String>
 [-Weight <Int32>] [-MinChildEndpoints <Int32>] -TrafficManagerProfile <IProfileWithDefinition>
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Add-AzureTrafficManagerEndpoint** menambahkan titik akhir ke Microsoft Azure Traffic Manager baru.
Setelah menambahkan titik akhir, kirim hasilnya ke cmdlet **Set-AzureTrafficManagerProfile** menggunakan operator pipeline.
Cmdlet tersebut tersambung ke Azure untuk menyimpan perubahan Anda.

## EXAMPLES

### Contoh 1: Menambahkan titik akhir ke profil
```
PS C:\>$TrafficManagerProfile = Get-AzureTrafficManagerProfile -Name "ContosoProfile"
PS C:\> Add-AzureTrafficManagerEndpoint -TrafficManagerProfile $TrafficManagerProfile -DomainName "Contoso02App.cloudapp.net" -Status "Enabled" -Type "CloudService" | Set-AzureTrafficManagerProfile
```

Perintah pertama menggunakan cmdlet **Get-AzureTrafficManagerProfile** untuk mendapatkan profil bernama ContosoProfile, lalu menyimpannya di variabel $TrafficManagerProfile berbeda.

Perintah kedua menambahkan titik akhir ke Traffic Manager profil pengguna yang disimpan di $TrafficManagerProfile.
Titik akhir memiliki nama domain Contoso02App.couldapp.net.
Perintah juga menentukan apakah diaktifkan dan tipenya.
Perintah melewati objek profil ke cmdlet **Set-AzureTrafficManagerProfile** agar tersambung ke Azure untuk menyimpan perubahan Anda.

### Contoh 2: Tambahkan titik akhir yang memiliki lokasi dan bobot yang ditentukan
```
PS C:\>Add-AzureTrafficManagerEndpoint -TrafficManagerProfile ContosoTrafficManagerProfile -DomainName " Contoso02App.cloudapp.net" -Status Enabled -Type CloudService -Weight 2 -Location myLocation | Set-AzureTrafficManagerProfile
```

Perintah ini menambahkan titik akhir ke Traffic Manager profil.
Titik akhir memiliki nama domain Contoso02App.couldapp.net.
Perintah juga menentukan apakah diaktifkan dan tipenya.
Perintah juga menentukan bobot dan lokasi untuk titik akhir.
Perintah melewati objek profil ke **Set-AzureTrafficManagerProfile** agar tersambung ke Azure untuk menyimpan perubahan Anda.

## PARAMETERS

### -DomainName
Menentukan nama domain titik akhir untuk ditambahkan.

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

Parameter ini harus berisi nilai untuk titik akhir tipe "Any" atau tipe "TrafficManager" di profil yang memiliki metode keseimbangan muat yang diatur ke "Kinerja".
Nilai yang mungkin ada adalah nama kawasan Azure, seperti yang tercantum di https://azure.microsoft.com/regions/ .

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

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TrafficManagerProfile
Menentukan Traffic Manager profil pengguna yang ingin Anda tambahkan titik akhir.

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

Required: True
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

[Remove-AzureTrafficManagerEndpoint](./Remove-AzureTrafficManagerEndpoint.md)

[Set-AzureTrafficManagerEndpoint](./Set-AzureTrafficManagerEndpoint.md)

[Get-AzureTrafficManagerProfile](./Get-AzureTrafficManagerProfile.md)

[Set-AzureTrafficManagerProfile](./Set-AzureTrafficManagerProfile.md)


