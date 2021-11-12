---
external help file: Microsoft.Azure.PowerShell.Cmdlets.TrafficManager.dll-Help.xml
Module Name: Az.TrafficManager
ms.assetid: A7A908A1-7326-4725-A3F9-4D05E40C5F73
online version: https://docs.microsoft.com/en-us/powershell/module/az.trafficmanager/new-aztrafficmanagerendpoint
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/TrafficManager/TrafficManager/help/New-AzTrafficManagerEndpoint.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/TrafficManager/TrafficManager/help/New-AzTrafficManagerEndpoint.md
ms.openlocfilehash: 9a32176afba8f4182ee1300e9b38936e9f35746c
ms.sourcegitcommit: b4a38bcb0501a9016a4998efd377aa75d3ef9ce8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/27/2020
ms.locfileid: "132406868"
---
# New-AzTrafficManagerEndpoint

## SYNOPSIS
Membuat titik akhir di Traffic Manager terkait.

## SINTAKS

```
New-AzTrafficManagerEndpoint -Name <String> -ProfileName <String> -ResourceGroupName <String> -Type <String>
 [-TargetResourceId <String>] [-Target <String>] -EndpointStatus <String> [-Weight <UInt32>]
 [-Priority <UInt32>] [-EndpointLocation <String>] [-MinChildEndpoints <UInt32>]
 [-GeoMapping <System.Collections.Generic.List`1[System.String]>]
 [-SubnetMapping <System.Collections.Generic.List`1[Microsoft.Azure.Commands.TrafficManager.Models.TrafficManagerIpAddressRange]>]
 [-CustomHeader <System.Collections.Generic.List`1[Microsoft.Azure.Commands.TrafficManager.Models.TrafficManagerCustomHeader]>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESKRIPSI
Cmdlet **New-AzTrafficManagerEndpoint** membuat titik akhir di Azure Traffic Manager profil.

Cmdlet ini akan melakukan setiap titik akhir baru ke Traffic Manager baru.
Untuk menambahkan beberapa titik akhir ke objek Traffic Manager profil lokal dan melakukan perubahan dalam satu operasi, gunakan cmdlet Add-AzTrafficManagerEndpointConfig cmdlet.

## CONTOH

### Contoh 1: Membuat titik akhir eksternal untuk profil
```
PS C:\>New-AzTrafficManagerEndpoint -EndpointStatus Enabled -Name "contoso" -ProfileName "ContosoProfile" -ResourceGroupName "ResourceGroup11" -Type ExternalEndpoints -EndpointLocation "North Europe" -Priority 1 -Target "www.contoso.com" -Weight 10
```

Perintah ini akan membuat titik akhir eksternal yang bernama contoso dalam profil yang bernama ContosoProfile dalam grup sumber daya yang bernama ResourceGroup11.

### Contoh 2: Membuat titik akhir Azure untuk profil
```
PS C:\>New-AzTrafficManagerEndpoint -EndpointStatus Enabled -Name "contoso" -ProfileName "ContosoProfile" -ResourceGroupName "ResourceGroup11" -Type AzureEndpoints -Priority 1 -TargetResourceId "/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/Default-Web-CentralUS/providers/Microsoft.Web/sites/contoso-web-app" -Weight 10
```

Perintah ini membuat titik akhir Azure yang bernama contoso dalam profil yang bernama ContosoProfile dalam grup sumber daya ResourceGroup11.
Titik akhir Azure akan menunjuk ke Azure Web App dengan ID Azure Resource Manager miliknya diberikan oleh jalur URI dalam *TargetResourceId*.
Perintah tidak menentukan parameter *EndpointLocation* karena sumber daya Web App menyediakan lokasi tersebut.

## PARAMETERS

### -CustomHeader
Daftar nama header dan pasangan nilai kustom untuk permintaan header kustom.

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
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

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
Menentukan lokasi titik akhir yang akan digunakan dalam metode Perutean lalu lintas kinerja.
Parameter ini hanya berlaku untuk titik akhir tipe ExternalEndpoints atau NestedEndpoints.
Anda harus menentukan parameter ini ketika metode Perutean lalu lintas kinerja digunakan.

Tentukan nama kawasan Azure.
Untuk daftar lengkap kawasan Azure, lihat Azure Regions http://azure.microsoft.com/regions/ ( http://azure.microsoft.com/regions/) .

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
Nilai valid adalah: 

- Diaktifkan 
- Dinonaktifkan 

Jika status Diaktifkan, titik akhir disederhkan untuk kesehatan titik akhir dan disertakan dalam metode perutean lalu lintas.

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
Daftar kawasan yang dipetakan ke titik akhir ini saat menggunakan metode perutean lalu lintas 'Geografis'. Bacalah Traffic Manager dokumentasi lengkap tentang nilai yang diterima.

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
Untuk daftar lengkap kawasan Azure, lihat Azure Regions http://azure.microsoft.com/regions/ ( http://azure.microsoft.com/regions/) .

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

### -Nama
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
Parameter ini hanya digunakan jika profil Traffic Manager dikonfigurasi dengan metode perutean lalu lintas Prioritas.
Nilai valid adalah bilangan bulat dari 1 sampai 1000.
Nilai yang lebih rendah menunjukkan prioritas yang lebih tinggi.

Jika menentukan prioritas, Anda harus menentukan prioritas di semua titik akhir dalam profil, dan tidak ada dua titik akhir yang dapat berbagi nilai prioritas yang sama.
Jika Anda tidak menentukan prioritas, Traffic Manager menetapkan nilai prioritas default ke titik akhir, dimulai dengan satu (1), dalam urutan profil akan mencantumkan titik akhir.

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
Menentukan nama profil Traffic Manager cmdlet ini menambahkan titik akhir.
Untuk mendapatkan profil, gunakan cmdlet New-AzTrafficManagerProfile Get-AzTrafficManagerProfile cmdlet.

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
Cmdlet ini membuat Traffic Manager titik akhir dalam grup yang ditentukan parameter ini.

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
Traffic Manager mengembalikan nilai ini dalam respons DNS ketika mengarahkan lalu lintas ke titik akhir ini.
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

### -Tipe
Menentukan tipe titik akhir yang tambahkan cmdlet ini ke Traffic Manager profil.
Nilai valid adalah: 

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

### -Bobot
Menentukan bobot yang Traffic Manager tetapkan ke titik akhir.
Nilai valid adalah bilangan bulat dari 1 sampai 1000.
Nilai defaultnya adalah satu (1).
Parameter ini hanya digunakan jika profil Traffic Manager dikonfigurasi dengan metode perutean lalu lintas tertimbang.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUT

### Tidak ada

## OUTPUT

### Microsoft.Azure.Commands.TrafficManager.Models.TrafficManagerEndpoint

## CATATAN

## LINK TERKAIT

[Disable-AzTrafficManagerEndpoint](./Disable-AzTrafficManagerEndpoint.md)

[Enable-AzTrafficManagerEndpoint](./Enable-AzTrafficManagerEndpoint.md)

[Get-AzTrafficManagerEndpoint](./Get-AzTrafficManagerEndpoint.md)

[Get-AzTrafficManagerProfile](./Get-AzTrafficManagerProfile.md)

[New-AzTrafficManagerProfile](./New-AzTrafficManagerProfile.md)

[Remove-AzTrafficManagerEndpoint](./Remove-AzTrafficManagerEndpoint.md)

[Set-AzTrafficManagerProfile](./Set-AzTrafficManagerProfile.md)


