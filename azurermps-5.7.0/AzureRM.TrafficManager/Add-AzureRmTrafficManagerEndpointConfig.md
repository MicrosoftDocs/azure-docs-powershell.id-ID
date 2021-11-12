---
external help file: Microsoft.Azure.Commands.TrafficManager.dll-Help.xml
Module Name: AzureRM
ms.assetid: 25E3F297-1D91-4102-B4D3-1E7195A5D33D
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.trafficmanager/add-azurermtrafficmanagerendpointconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/TrafficManager/Commands.TrafficManager2/help/Add-AzureRmTrafficManagerEndpointConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/TrafficManager/Commands.TrafficManager2/help/Add-AzureRmTrafficManagerEndpointConfig.md
ms.openlocfilehash: e9e6817d9a290acf1e91067edfd90cdf8081f1f0
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132421745"
---
# Add-AzureRmTrafficManagerEndpointConfig

## SYNOPSIS
Menambahkan titik akhir ke objek Traffic Manager profil lokal.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Add-AzureRmTrafficManagerEndpointConfig -EndpointName <String> -TrafficManagerProfile <TrafficManagerProfile>
 -Type <String> [-TargetResourceId <String>] [-Target <String>] -EndpointStatus <String> [-Weight <UInt32>]
 [-Priority <UInt32>] [-EndpointLocation <String>] [-MinChildEndpoints <UInt32>]
 [-GeoMapping <System.Collections.Generic.List`1[System.String]>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Add-AzureRmTrafficManagerEndpointConfig** menambahkan titik akhir ke objek Azure Traffic Manager profil lokal.
Anda dapat memperoleh profil menggunakan cmdlet New-AzureRmTrafficManagerProfile Get-AzureRmTrafficManagerProfile.

Cmdlet ini beroperasi pada objek profil lokal.
Lakukan perubahan ke profil untuk Traffic Manager dengan menggunakan cmdlet Set-AzureRmTrafficManagerProfile cmdlet.
Untuk membuat titik akhir dan melakukan perubahan dalam satu operasi, gunakan cmdlet New-AzureRmTrafficManagerEndpoint cmdlet.

## EXAMPLES

### Contoh 1: Menambahkan titik akhir ke profil
```
PS C:\>$TrafficManagerProfile = Get-AzureRmTrafficManagerProfile -Name "ContosoProfile" -ResourceGroupName "ResourceGroup11"
PS C:\> Add-AzureRmTrafficManagerEndpointConfig -EndpointName "contoso" -EndpointStatus Enabled -Target "www.contoso.com" -TrafficManagerProfile $TrafficManagerProfile -Type ExternalEndpoints -EndpointLocation "North Europe" -Priority 1 -Weight 10
PS C:\> Set-AzureRmTrafficManagerProfile -TrafficManagerProfile $TrafficManagerProfile
```

Perintah pertama mendapatkan profil Azure Traffic Manager dengan menggunakan cmdlet **Get-AzureRmTrafficManagerProfile.**
Perintah menyimpan profil lokal di $TrafficManagerProfile variabel.

Perintah kedua menambahkan titik akhir yang bernama contoso ke profil yang disimpan di $TrafficManagerProfile.
Perintah tersebut menyertakan data konfigurasi untuk titik akhir.
Perintah ini hanya mengubah objek lokal.

Perintah terakhir memperbarui profil Traffic Manager di Azure agar sesuai dengan nilai lokal di $TrafficManagerProfile.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EndpointLocation
Menentukan lokasi titik akhir yang akan digunakan dalam metode Perutean lalu lintas kinerja.
Parameter ini hanya berlaku untuk titik akhir tipe ExternalEndpoints atau NestedEndpoints.
Anda harus menentukan parameter ini ketika metode Perutean lalu lintas kinerja digunakan.

Tentukan nama kawasan Azure.
Untuk daftar lengkap kawasan Azure, lihat Azure Regions https://azure.microsoft.com/regions/ ( https://azure.microsoft.com/regions/) .

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

### -EndpointName
Menentukan nama titik akhir Traffic Manager cmdlet ini.

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

### -EndpointStatus
Menentukan status titik akhir.
Nilai valid adalah: 

- Diaktifkan 
- Dinonaktifkan 

Jika status Diaktifkan, titik akhir disederhkan untuk kesehatan titik akhir dan disertakan dalam metode perutean lalu lintas.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Accepted values: Enabled, Disabled

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GeoMapping
Daftar kawasan yang dipetakan ke titik akhir ini saat menggunakan metode perutean lalu lintas 'Geografis'. Bacalah Traffic Manager ini untuk daftar [lengkap nilai yang diterima.](https://docs.microsoft.com/en-us/azure/traffic-manager/traffic-manager-geographic-regions)
```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinChildEndpoints
Tentukan nama kawasan Azure.
Untuk daftar lengkap kawasan Azure, lihat Azure Regions https://azure.microsoft.com/regions/ ( https://azure.microsoft.com/regions/) .

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Prioritas
Menentukan prioritas yang Traffic Manager tetapkan ke titik akhir.
Parameter ini hanya digunakan jika profil Traffic Manager dikonfigurasi dengan metode perutean lalu lintas Prioritas.
Nilai valid adalah bilangan bulat dari 1 sampai 1000.
Nilai yang lebih rendah menunjukkan prioritas yang lebih tinggi.

Jika menentukan prioritas, Anda harus menentukan prioritas di semua titik akhir dalam profil, dan tidak ada dua titik akhir yang dapat berbagi nilai prioritas yang sama.
Jika Anda tidak menentukan prioritas, Traffic Manager menetapkan nilai prioritas default ke titik akhir, dimulai dengan satu (1), dalam urutan profil akan mencantumkan titik akhir.

```yaml
Type: UInt32
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Target
Menentukan nama DNS titik akhir yang sepenuhnya memenuhi syarat.
Traffic Manager mengembalikan nilai ini dalam respons DNS ketika mengarahkan lalu lintas ke titik akhir ini.
Tentukan parameter ini hanya untuk tipe titik akhir ExternalEndpoints.
Untuk tipe titik akhir lainnya, tentukan parameter *TargetResourceId* sebagai gantinya.

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

### -TargetResourceId
Menentukan ID sumber daya target.
Tentukan parameter ini hanya untuk tipe titik akhir AzureEndpoints dan NestedEndpoints.
Untuk tipe titik akhir ExternalEndpoints, tentukan parameter *Target* sebagai gantinya.

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
Menentukan objek **TrafficManagerProfile** lokal.
Cmdlet ini mengubah objek lokal ini.
Untuk mendapatkan objek **TrafficManagerProfile,** gunakan cmdlet Get-AzureRmTrafficManagerProfile baru.

```yaml
Type: TrafficManagerProfile
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Tipe
Menentukan tipe titik akhir yang tambahkan cmdlet ini ke Azure Traffic Manager profil.
Nilai valid adalah: 

- AzureEndpoints
- ExternalEndpoints
- NestedEndpoints

```yaml
Type: String
Parameter Sets: (All)
Aliases: 
Accepted values: AzureEndpoints, ExternalEndpoints, NestedEndpoints

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Bobot
Menentukan bobot yang Traffic Manager tetapkan ke titik akhir.
Nilai valid adalah bilangan bulat dari 1 sampai 1000.
Nilai defaultnya adalah satu (1).
Parameter ini hanya digunakan jika profil Traffic Manager dikonfigurasi dengan metode perutean lalu lintas tertimbang.

```yaml
Type: UInt32
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

### Microsoft.Azure.Commands.Network.TrafficManagerProfile
Cmdlet ini menerima objek **TrafficManagerProfile** ke cmdlet ini.

## OUTPUTS

### Microsoft.Azure.Commands.Network.TrafficManagerProfile
Cmdlet ini mengembalikan objek **TrafficManagerProfile yang** diubah.

## CATATAN

## RELATED LINKS

[Get-AzureRmTrafficManagerProfile](./Get-AzureRmTrafficManagerProfile.md)

[New-AzureRmTrafficManagerEndpoint](./New-AzureRmTrafficManagerEndpoint.md)

[Remove-AzureRmTrafficManagerEndpointConfig](./Remove-AzureRmTrafficManagerEndpointConfig.md)

[Set-AzureRmTrafficManagerProfile](./Set-AzureRmTrafficManagerProfile.md)


