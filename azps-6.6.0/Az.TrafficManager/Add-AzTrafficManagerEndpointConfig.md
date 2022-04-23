---
external help file: Microsoft.Azure.PowerShell.Cmdlets.TrafficManager.dll-Help.xml
Module Name: Az.TrafficManager
ms.assetid: 25E3F297-1D91-4102-B4D3-1E7195A5D33D
online version: https://docs.microsoft.com/powershell/module/az.trafficmanager/add-aztrafficmanagerendpointconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/TrafficManager/TrafficManager/help/Add-AzTrafficManagerEndpointConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/TrafficManager/TrafficManager/help/Add-AzTrafficManagerEndpointConfig.md
ms.openlocfilehash: e12b44c860363914c419c99982aefa7678c8e852
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143082449"
---
# Add-AzTrafficManagerEndpointConfig

## SYNOPSIS
Menambahkan titik akhir ke objek profil Traffic Manager lokal.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.trafficmanager/add-aztrafficmanagerendpointconfig) untuk informasi terbaru.

## SYNTAX

```
Add-AzTrafficManagerEndpointConfig -EndpointName <String> -TrafficManagerProfile <TrafficManagerProfile>
 -Type <String> [-TargetResourceId <String>] [-Target <String>] -EndpointStatus <String> [-Weight <UInt32>]
 [-Priority <UInt32>] [-EndpointLocation <String>] [-MinChildEndpoints <UInt32>]
 [-GeoMapping <System.Collections.Generic.List`1[System.String]>]
 [-SubnetMapping <System.Collections.Generic.List`1[Microsoft.Azure.Commands.TrafficManager.Models.TrafficManagerIpAddressRange]>]
 [-CustomHeader <System.Collections.Generic.List`1[Microsoft.Azure.Commands.TrafficManager.Models.TrafficManagerCustomHeader]>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Add-AzTrafficManagerEndpointConfig** menambahkan titik akhir ke objek profil Azure Traffic Manager lokal.
Anda bisa mendapatkan profil dengan menggunakan cmdlet New-AzTrafficManagerProfile atau Get-AzTrafficManagerProfile.

Cmdlet ini beroperasi pada objek profil lokal.
Lakukan perubahan anda ke profil untuk Traffic Manager dengan menggunakan cmdlet Set-AzTrafficManagerProfile.
Untuk membuat titik akhir dan melakukan perubahan dalam satu operasi, gunakan cmdlet New-AzTrafficManagerEndpoint.

## EXAMPLES

### Contoh 1: Menambahkan titik akhir ke profil
```
PS C:\>$TrafficManagerProfile = Get-AzTrafficManagerProfile -Name "ContosoProfile" -ResourceGroupName "ResourceGroup11"
PS C:\> Add-AzTrafficManagerEndpointConfig -EndpointName "contoso" -EndpointStatus Enabled -Target "www.contoso.com" -TrafficManagerProfile $TrafficManagerProfile -Type ExternalEndpoints -EndpointLocation "North Europe" -Priority 1 -Weight 10
PS C:\> Set-AzTrafficManagerProfile -TrafficManagerProfile $TrafficManagerProfile
```

Perintah pertama mendapatkan profil Azure Traffic Manager dengan menggunakan cmdlet **Get-AzTrafficManagerProfile**.
Perintah menyimpan profil lokal dalam variabel $TrafficManagerProfile.

Perintah kedua menambahkan titik akhir bernama contoso ke profil yang disimpan di $TrafficManagerProfile.
Perintah ini menyertakan data konfigurasi untuk titik akhir.
Perintah ini hanya mengubah objek lokal.

Perintah terakhir memperbarui profil Traffic Manager di Azure agar sesuai dengan nilai lokal di $TrafficManagerProfile.

## PARAMETERS

### -CustomHeader
Daftar nama header kustom dan pasangan nilai untuk permintaan probe.

```yaml
Type: System.Collections.Generic.List`1[Microsoft.Azure.Commands.TrafficManager.Models.TrafficManagerCustomHeader]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EndpointLocation
Menentukan lokasi titik akhir untuk digunakan dalam metode Perutean lalu lintas kinerja.
Parameter ini hanya berlaku untuk titik akhir dari tipe ExternalEndpoints atau NestedEndpoints.
Anda harus menentukan parameter ini saat metode Perutean lalu lintas kinerja digunakan.

Tentukan nama kawasan Azure.
Untuk daftar lengkap kawasan Azure, lihat Kawasanhttp://azure.microsoft.com/regions/ Azure (http://azure.microsoft.com/regions/).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EndpointName
Menentukan nama titik akhir Traffic Manager yang ditambahkan cmdlet ini.

```yaml
Type: System.String
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
Nilai yang valid adalah: 

- Diaktifkan 
- Tamu penyandang cacat 

Jika status Diaktifkan, titik akhir diprobed untuk kesehatan titik akhir dan disertakan dalam metode perutean lalu lintas.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Enabled, Disabled

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Geomapping
Daftar kawasan yang dipetakan ke titik akhir ini ketika menggunakan metode perutean lalu lintas 'Geografis'. Silakan konsultasikan dokumentasi Traffic Manager untuk [daftar lengkap nilai yang diterima](https://docs.microsoft.com/azure/traffic-manager/traffic-manager-geographic-regions).

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
Jumlah minimum titik akhir yang harus tersedia di profil anak agar Titik Akhir Bertumpuk di profil induk dapat dianggap tersedia.
Hanya berlaku untuk titik akhir tipe 'NestedEndpoints'.

```yaml
Type: System.Nullable`1[System.UInt32]
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
Nilai yang valid adalah bilangan bulat dari 1 sampai 1000.
Nilai yang lebih rendah mewakili prioritas yang lebih tinggi.

Jika Anda menentukan prioritas, Anda harus menentukan prioritas pada semua titik akhir di profil, dan tidak ada dua titik akhir yang bisa berbagi nilai prioritas yang sama.
Jika Anda tidak menentukan prioritas, Traffic Manager menetapkan nilai prioritas default ke titik akhir, dimulai dengan satu (1), dalam urutan profil mencantumkan titik akhir.

```yaml
Type: System.Nullable`1[System.UInt32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubnetMapping
Daftar rentang alamat atau subnet yang dipetakan ke titik akhir ini ketika menggunakan metode perutean lalu lintas 'Subnet'.

```yaml
Type: System.Collections.Generic.List`1[Microsoft.Azure.Commands.TrafficManager.Models.TrafficManagerIpAddressRange]
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
Traffic Manager mengembalikan nilai ini dalam respons DNS saat mengarahkan lalu lintas ke titik akhir ini.
Tentukan parameter ini hanya untuk tipe titik akhir ExternalEndpoints.
Untuk tipe titik akhir lainnya, tentukan parameter *TargetResourceId* sebagai gantinya.

```yaml
Type: System.String
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
Type: System.String
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
Untuk mendapatkan objek **TrafficManagerProfile** , gunakan cmdlet Get-AzTrafficManagerProfile.

```yaml
Type: Microsoft.Azure.Commands.TrafficManager.Models.TrafficManagerProfile
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Tipe
Menentukan tipe titik akhir yang ditambahkan cmdlet ini ke profil Azure Traffic Manager.
Nilai yang valid adalah: 

- AzureEndpoints
- ExternalEndpoints
- NestedEndpoints

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: AzureEndpoints, ExternalEndpoints, NestedEndpoints

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Berat
Menentukan bobot yang Traffic Manager tetapkan ke titik akhir.
Nilai yang valid adalah bilangan bulat dari 1 sampai 1000.
Nilai defaultnya adalah satu (1).
Parameter ini hanya digunakan jika profil Traffic Manager dikonfigurasi dengan metode perutean lalu lintas Tertimbang.

```yaml
Type: System.Nullable`1[System.UInt32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.TrafficManager.Models.TrafficManagerProfile

## OUTPUTS

### Microsoft.Azure.Commands.TrafficManager.Models.TrafficManagerProfile

## NOTES

## RELATED LINKS

[Get-AzTrafficManagerProfile](./Get-AzTrafficManagerProfile.md)

[New-AzTrafficManagerEndpoint](./New-AzTrafficManagerEndpoint.md)

[Remove-AzTrafficManagerEndpointConfig](./Remove-AzTrafficManagerEndpointConfig.md)

[Set-AzTrafficManagerProfile](./Set-AzTrafficManagerProfile.md)


