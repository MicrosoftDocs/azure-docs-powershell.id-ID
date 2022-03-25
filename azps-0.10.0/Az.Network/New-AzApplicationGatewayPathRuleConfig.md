---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: A1F949A9-7AEF-41C1-B757-114421B79493
online version: https://docs.microsoft.com/en-us/powershell/module/az.network/new-azapplicationgatewaypathruleconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Network/Network/help/New-AzApplicationGatewayPathRuleConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Network/Network/help/New-AzApplicationGatewayPathRuleConfig.md
ms.openlocfilehash: b6722412717d0ef087c2540ff49d3d7a5b87913c
ms.sourcegitcommit: d28d7d5f6278862d833182868a9dcde2c31e657b
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/24/2022
ms.locfileid: "132414573"
---
# New-AzApplicationGatewayPathRuleConfig

## SYNOPSIS
Membuat aturan jalur gateway aplikasi.

## SYNTAX

### SetByResourceId
```
New-AzApplicationGatewayPathRuleConfig -Name <String>
 -Paths <System.Collections.Generic.List`1[System.String]> [-BackendAddressPoolId <String>]
 [-BackendHttpSettingsId <String>] [-RedirectConfigurationId <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### SetByResource
```
New-AzApplicationGatewayPathRuleConfig -Name <String>
 -Paths <System.Collections.Generic.List`1[System.String]>
 [-BackendAddressPool <PSApplicationGatewayBackendAddressPool>]
 [-BackendHttpSettings <PSApplicationGatewayBackendHttpSettings>]
 [-RedirectConfiguration <PSApplicationGatewayRedirectConfiguration>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzApplicationGatewayPathRuleConfig** membuat aturan jalur gateway aplikasi.
Aturan yang dibuat oleh cmdlet ini bisa ditambahkan ke kumpulan pengaturan konfigurasi peta jalur URL lalu ditetapkan ke gateway.

Pengaturan konfigurasi peta jalur digunakan dalam penyeimbangan muat gateway aplikasi.

## EXAMPLES

### Contoh 1
```
PS C:\>$Gateway = Get-AzApplicationGateway -Name "ContosoApplicationGateway"
PS C:\> $AddressPool = New-AzApplicationGatewayBackendAddressPool -Name "ContosoAddressPool" -BackendIPAddresses "192.168.1.1", "192.168.1.2"
PS C:\> $HttpSettings = New-AzApplicationGatewayBackendHttpSetting -Name "ContosoHttpSetings" -Port 80 -Protocol "Http" -CookieBasedAffinity "Disabled"
PS C:\> $PathRuleConfig = New-AzApplicationGatewayPathRuleConfig -Name "base" -Paths "/base" -BackendAddressPool $AddressPool -BackendHttpSettings $HttpSettings
PS C:\> Add-AzApplicationGatewayUrlPathMapConfig -ApplicationGateway $Gateway -Name "ContosoUrlPathMap" -PathRules $PathRuleConfig -DefaultBackendAddressPool $AddressPool -DefaultBackendHttpSettings $HttpSettings
```

Perintah ini membuat aturan jalur gateway aplikasi baru lalu menggunakan cmdlet **Add-AzApplicationGatewayUrlPathMapConfig** untuk menetapkan aturan tersebut ke gateway aplikasi.
Untuk melakukan ini, perintah pertama membuat referensi objek ke gateway ContosoApplicationGateway.
Referensi objek ini disimpan dalam variabel yang bernama $Gateway.

Dua perintah berikutnya membuat sebuah pool alamat backend dan objek pengaturan HTTP backend; objek ini (disimpan dalam variabel $AddressPool dan $HttpSettings) diperlukan untuk membuat objek aturan jalur.

Perintah keempat membuat objek aturan jalur dan disimpan dalam variabel yang bernama $PathRuleConfig.

Perintah kelima menggunakan **Add-AzApplicationGatewayUrlPathMapConfig** untuk menambahkan pengaturan konfigurasi dan aturan jalur baru yang terdapat di dalam pengaturan tersebut ke ContosoApplicationGateway.

## PARAMETERS

### -BackendAddressPool
Menentukan referensi objek untuk kumpulan pengaturan kumpulan alamat backend yang akan ditambahkan ke pengaturan konfigurasi aturan jalur gateway.
Anda dapat membuat referensi objek ini menggunakan cmdlet New-AzApplicationGatewayBackendAddressPool sintaks yang mirip dengan ini:

`$AddressPool = New-AzApplicationGatewayBackendAddressPool -Name "ContosoAddressPool" -BackendIPAddresses "192.168.1.1", "192.168.1.2"`

Perintah sebelumnya menambahkan dua alamat IP (192.16.1.1 dan 192.168.1.2) ke pool alamat.
Perhatikan bahwa alamat IP dimasukkan di dalam tanda petik dan dipisahkan dengan menggunakan koma.

Variabel yang dihasilkan, $AddressPool, lalu bisa digunakan sebagai nilai parameter untuk parameter *DefaultBackendAddressPool* .

The backend address pool represents the IP addresses on the backend servers.
Alamat IP ini harus termasuk dalam subnet jaringan virtual atau harus merupakan alamat IP publik.
Jika Anda menggunakan parameter ini Anda tidak bisa menggunakan *parameter DefaultBackendAddressPoolId* di perintah yang sama.

```yaml
Type: PSApplicationGatewayBackendAddressPool
Parameter Sets: SetByResource
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BackendAddressPoolId
Menentukan ID sebuah pool alamat backend yang sudah ada yang bisa ditambahkan ke pengaturan konfigurasi aturan jalur gateway.
ADDRESS pool IDs can be returned by using the Get-AzApplicationGatewayBackendAddressPool cmdlet.
Setelah Mendapatkan ID, Anda kemudian dapat menggunakan parameter *DefaultBackendAddressPoolId* dan bukan parameter *DefaultBackendAddressPool* .
Misalnya:

-DefaultBackendAddressPoolId "/subscriptions/39c54063-01d3-4abf-8f4c-234777bc1f10/resourceGroups/appgw-rg/providers/Microsoft.Network/applicationGateway/appgwtest/backendAddressPools/ContosoAddressPool"

The backend address pool represents the IP addresses on the backend servers.
Alamat IP ini harus termasuk dalam subnet jaringan virtual atau harus merupakan alamat IP publik.

```yaml
Type: String
Parameter Sets: SetByResourceId
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BackendHttpSettings
Menentukan referensi objek ke kumpulan pengaturan HTTP backend untuk ditambahkan ke pengaturan konfigurasi aturan jalur gateway.
Anda dapat membuat referensi objek ini menggunakan cmdlet New-AzApplicationGatewayBackendHttpSetting sintaks yang mirip dengan ini:

$HttpSettings = New-AzApplicationGatewayBackendHttpSetting -Name "ContosoHttpSetings" -Port 80 -Protocol "Http" -CookieBasedAffinity "Disabled"

Variabel yang dihasilkan, $HttpSettings, lalu bisa digunakan sebagai nilai parameter untuk parameter *DefaultBackendAddressPool* :

-DefaultBackendHttpSettings $HttpSettings

Pengaturan HTTP backend mengonfigurasi properti seperti port, protokol, dan afiliasi berbasis cookie untuk pool backend.
Jika menggunakan parameter ini, Anda tidak dapat menggunakan *parameter DefaultBackendHttpSettingsId* dalam perintah yang sama.

```yaml
Type: PSApplicationGatewayBackendHttpSettings
Parameter Sets: SetByResource
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BackendHttpSettingsId
Menentukan ID kumpulan pengaturan backend HTTP yang sudah ada yang bisa ditambahkan ke pengaturan konfigurasi aturan jalur gateway.
ID pengaturan HTTP bisa dikembalikan dengan menggunakan cmdlet Get-AzApplicationGatewayBackendHttpSetting.
Setelah mendapatkan ID, Anda kemudian dapat menggunakan parameter *DefaultBackendHttpSettingsId* dan bukan parameter *DefaultBackendHttpSettings* .
Misalnya:

-DefaultBackendSettings Id "/subscriptions/39c54063-01d3-4abf-8f4c-234777bc1f10/resourceGroups/appgw-rg/providers/Microsoft.Network/applicationGateway/appgwtest/backendHttpSettingsCollection/ContosoHttpSettings"

Pengaturan HTTP backend mengonfigurasi properti seperti port, protokol, dan afiliasi berbasis cookie untuk pool backend.
Jika Menggunakan parameter ini, Anda tidak dapat menggunakan parameter *DefaultBackendHttpSettings* dalam perintah yang sama.

```yaml
Type: String
Parameter Sets: SetByResourceId
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
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Menentukan nama konfigurasi aturan jalur yang dibuat cmdlet ini.

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

### -Jalur
Menentukan satu atau beberapa aturan jalur gateway aplikasi.

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RedirectConfiguration
Application gateway RedirectConfiguration

```yaml
Type: PSApplicationGatewayRedirectConfiguration
Parameter Sets: SetByResource
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RedirectConfigurationId
ID gateway aplikasi RedirectConfiguration

```yaml
Type: String
Parameter Sets: SetByResourceId
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

###  
**New-AzApplicationGatewayPathRuleConfig** tidak menerima input saluran.

## OUTPUTS

###  
**New-AzApplicationGatewayPathRuleConfig** membuat contoh baru objek **Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayPathRule** .

## CATATAN

## RELATED LINKS

[Add-AzApplicationGatewayUrlPathMapConfig](./Add-AzApplicationGatewayUrlPathMapConfig.md)

[Get-AzApplicationGateway](./Get-AzApplicationGateway.md)

[Get-AzApplicationGatewayUrlPathMapConfig](./Get-AzApplicationGatewayUrlPathMapConfig.md)

[New-AzApplicationGatewayBackendAddressPool](./New-AzApplicationGatewayBackendAddressPool.md)

[New-AzApplicationGatewayBackendHttpSetting](./New-AzApplicationGatewayBackendHttpSetting.md)

[New-AzApplicationGatewayPathRuleConfig](./New-AzApplicationGatewayPathRuleConfig.md)

[New-AzApplicationGatewayUrlPathMapConfig](./New-AzApplicationGatewayUrlPathMapConfig.md)

[Remove-AzApplicationGatewayUrlPathMapConfig](./Remove-AzApplicationGatewayUrlPathMapConfig.md)

[Set-AzApplicationGatewayUrlPathMapConfig](./Set-AzApplicationGatewayUrlPathMapConfig.md)


