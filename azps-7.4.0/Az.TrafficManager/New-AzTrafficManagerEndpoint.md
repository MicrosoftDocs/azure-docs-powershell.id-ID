---
external help file: Microsoft.Azure.PowerShell.Cmdlets.TrafficManager.dll-Help.xml
Module Name: Az.TrafficManager
ms.assetid: A7A908A1-7326-4725-A3F9-4D05E40C5F73
online version: https://docs.microsoft.com/powershell/module/az.trafficmanager/new-aztrafficmanagerendpoint
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/TrafficManager/TrafficManager/help/New-AzTrafficManagerEndpoint.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/TrafficManager/TrafficManager/help/New-AzTrafficManagerEndpoint.md
ms.openlocfilehash: 7633878f067a45fd3c25dd61f42bdc7832a3a2d5
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144612968"
---
# New-AzTrafficManagerEndpoint

## SYNOPSIS
Membuat titik akhir di profil Microsoft Azure Traffic Manager.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.trafficmanager/new-aztrafficmanagerendpoint) untuk informasi terbaru.

## SYNTAX

```
New-AzTrafficManagerEndpoint -Name <String> -ProfileName <String> -ResourceGroupName <String> -Type <String>
 [-TargetResourceId <String>] [-Target <String>] -EndpointStatus <String> [-Weight <UInt32>]
 [-Priority <UInt32>] [-EndpointLocation <String>] [-MinChildEndpoints <UInt32>] [-MinChildEndpointsIPv4 <UInt32>] [-MinChildEndpointsIPv6 <UInt32>]
 [-GeoMapping <System.Collections.Generic.List`1[System.String]>]
 [-SubnetMapping <System.Collections.Generic.List`1[Microsoft.Azure.Commands.TrafficManager.Models.TrafficManagerIpAddressRange]>]
 [-CustomHeader <System.Collections.Generic.List`1[Microsoft.Azure.Commands.TrafficManager.Models.TrafficManagerCustomHeader]>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzTrafficManagerEndpoint** membuat titik akhir di profil Azure Traffic Manager.

Cmdlet ini menerapkan setiap titik akhir baru ke layanan Traffic Manager.
Untuk menambahkan beberapa titik akhir ke objek profil Traffic Manager lokal dan menerapkan perubahan dalam satu operasi, gunakan cmdlet Add-AzTrafficManagerEndpointConfig.

## EXAMPLES

### Contoh 1: Membuat titik akhir eksternal untuk profil
```powershell
New-AzTrafficManagerEndpoint -EndpointStatus Enabled -Name "contoso" -ProfileName "ContosoProfile" -ResourceGroupName "ResourceGroup11" -Type ExternalEndpoints -EndpointLocation "North Europe" -Priority 1 -Target "www.contoso.com" -Weight 10
```

Perintah ini membuat titik akhir eksternal bernama contoso di profil bernama ContosoProfile di grup sumber daya bernama ResourceGroup11.

### Contoh 2: Membuat titik akhir Azure untuk profil
```powershell
New-AzTrafficManagerEndpoint -EndpointStatus Enabled -Name "contoso" -ProfileName "ContosoProfile" -ResourceGroupName "ResourceGroup11" -Type AzureEndpoints -Priority 1 -TargetResourceId "/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/Default-Web-CentralUS/providers/Microsoft.Web/sites/contoso-web-app" -Weight 10
```

Perintah ini membuat titik akhir Azure bernama contoso di profil bernama ContosoProfile dalam grup sumber daya ResourceGroup11.
Titik akhir Azure menunjuk ke Azure Web App yang ID Resource Manager Azure-nya diberikan oleh jalur URI di *TargetResourceId*.
Perintah tidak menentukan parameter *EndpointLocation* karena sumber daya Aplikasi Web menyediakan lokasi.

## PARAMETERS

### -CustomHeader
Daftar nama header kustom dan pasangan nilai untuk permintaan pemeriksaan.

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
Menentukan lokasi titik akhir yang akan digunakan dalam metode perutean lalu lintas performa.
Parameter ini hanya berlaku untuk titik akhir jenis ExternalEndpoints atau NestedEndpoints.
Anda harus menentukan parameter ini ketika metode perutean lalu lintas Performa digunakan.

Tentukan nama wilayah Azure.
Untuk daftar lengkap wilayah Azure, lihat Wilayahhttp://azure.microsoft.com/regions/ Azure (http://azure.microsoft.com/regions/).

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

### -EndpointStatus
Menentukan status titik akhir.
Nilai yang valid adalah: 

- Aktif 
- Nonaktifkan 

Jika status Diaktifkan, titik akhir diselimuti untuk kesehatan titik akhir dan disertakan dalam metode perutean lalu lintas.

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

### -GeoMapping
Daftar wilayah yang dipetakan ke titik akhir ini saat menggunakan metode perutean lalu lintas 'Geografis'. Silakan lihat dokumentasi Traffic Manager untuk daftar lengkap nilai yang diterima.

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
Tentukan nama wilayah Azure.
Untuk daftar lengkap wilayah Azure, lihat Wilayahhttp://azure.microsoft.com/regions/ Azure (http://azure.microsoft.com/regions/).

### -MinChildEndpointsIPv4
Jumlah minimum titik akhir IPv4 (catatan DNS tipe A) yang harus tersedia di profil anak agar Titik Akhir Berlapis di profil induk dianggap tersedia.
Hanya berlaku untuk titik akhir jenis 'NestedEndpoints'.

### -MinChildEndpointsIPv6
Jumlah minimum titik akhir IPv6 (tipe catatan DNS AAAA) yang harus tersedia di profil anak agar Titik Akhir Berlapis di profil induk dianggap tersedia.
Hanya berlaku untuk titik akhir jenis 'NestedEndpoints'.

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

### -Name
Menentukan nama titik akhir Traffic Manager yang dibuat cmdlet ini.

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

### -Prioritas
Menentukan prioritas yang Traffic Manager tetapkan ke titik akhir.
Parameter ini hanya digunakan jika profil Traffic Manager dikonfigurasi dengan untuk metode perutean lalu lintas Prioritas.
Nilai yang valid adalah bilangan bulat dari 1 hingga 1000.
Nilai yang lebih rendah mewakili prioritas yang lebih tinggi.

Jika Anda menentukan prioritas, Anda harus menentukan prioritas pada semua titik akhir di profil, dan tidak ada dua titik akhir yang dapat berbagi nilai prioritas yang sama.
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

### -ProfileName
Menentukan nama profil Traffic Manager tempat cmdlet ini menambahkan titik akhir.
Untuk mendapatkan profil, gunakan cmdlet New-AzTrafficManagerProfile atau Get-AzTrafficManagerProfile.

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

### -ResourceGroupName
Menentukan nama grup sumber daya.
Cmdlet ini membuat titik akhir Traffic Manager dalam grup yang ditentukan parameter ini.

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

### -SubnetMapping
Daftar rentang alamat atau subnet yang dipetakan ke titik akhir ini saat menggunakan metode perutean lalu lintas 'Subnet'.

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
Tentukan parameter ini hanya untuk jenis titik akhir ExternalEndpoints.
Untuk jenis titik akhir lainnya, tentukan parameter *TargetResourceId* sebagai gantinya.

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
Tentukan parameter ini hanya untuk jenis titik akhir AzureEndpoints dan NestedEndpoints.
Untuk jenis titik akhir ExternalEndpoints, tentukan parameter *Target* sebagai gantinya.

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

### -Type
Menentukan jenis titik akhir yang ditambahkan cmdlet ini ke profil Traffic Manager.
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
Nilai yang valid adalah bilangan bulat dari 1 hingga 1000.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.TrafficManager.Models.TrafficManagerEndpoint

## NOTES

## RELATED LINKS

[Disable-AzTrafficManagerEndpoint](./Disable-AzTrafficManagerEndpoint.md)

[Enable-AzTrafficManagerEndpoint](./Enable-AzTrafficManagerEndpoint.md)

[Get-AzTrafficManagerEndpoint](./Get-AzTrafficManagerEndpoint.md)

[Get-AzTrafficManagerProfile](./Get-AzTrafficManagerProfile.md)

[New-AzTrafficManagerProfile](./New-AzTrafficManagerProfile.md)

[Remove-AzTrafficManagerEndpoint](./Remove-AzTrafficManagerEndpoint.md)

[Set-AzTrafficManagerProfile](./Set-AzTrafficManagerProfile.md)


