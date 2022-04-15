---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: A1F949A9-7AEF-41C1-B757-114421B79493
online version: https://docs.microsoft.com/en-us/powershell/module/az.network/new-azapplicationgatewaypathruleconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Network/Network/help/New-AzApplicationGatewayPathRuleConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Network/Network/help/New-AzApplicationGatewayPathRuleConfig.md
ms.openlocfilehash: b6722412717d0ef087c2540ff49d3d7a5b87913c
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142497113"
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

Pengaturan konfigurasi peta jalur digunakan dalam penyeimbangan muatan gateway aplikasi.

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
Referensi objek ini disimpan dalam variabel bernama $Gateway.

Dua perintah berikutnya membuat kumpulan alamat backend dan objek pengaturan HTTP backend; objek ini (disimpan dalam variabel $AddressPool dan $HttpSettings) diperlukan untuk membuat objek aturan jalur.

Perintah keempat membuat objek aturan jalur dan disimpan dalam variabel bernama $PathRuleConfig.

Perintah kelima menggunakan **Add-AzApplicationGatewayUrlPathMapConfig** untuk menambahkan pengaturan konfigurasi dan aturan jalur baru yang terdapat dalam pengaturan tersebut ke ContosoApplicationGateway.

## PARAMETERS

### -BackendAddressPool
Menentukan referensi objek ke kumpulan pengaturan kumpulan alamat backend untuk ditambahkan ke pengaturan konfigurasi aturan jalur gateway.
Anda dapat membuat referensi objek ini menggunakan cmdlet dan sintaks New-AzApplicationGatewayBackendAddressPool yang serupa dengan ini:

`$AddressPool = New-AzApplicationGatewayBackendAddressPool -Name "ContosoAddressPool" -BackendIPAddresses "192.168.1.1", "192.168.1.2"`

Perintah sebelumnya menambahkan dua alamat IP (192.16.1.1 dan 192.168.1.2) ke kumpulan alamat.
Perhatikan bahwa alamat IP diapit dalam tanda kutip dan dipisahkan dengan menggunakan koma.

Variabel yang dihasilkan, $AddressPool, kemudian dapat digunakan sebagai nilai parameter untuk parameter *DefaultBackendAddressPool* .

Kumpulan alamat backend mewakili alamat IP di server backend.
Alamat IP ini harus dimiliki oleh subnet jaringan virtual atau harus alamat IP publik.
Jika menggunakan parameter ini, Anda tidak dapat menggunakan parameter *DefaultBackendAddressPoolId* dalam perintah yang sama.

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
Menentukan ID kumpulan alamat backend yang sudah ada yang bisa ditambahkan ke pengaturan konfigurasi aturan jalur gateway.
ID kumpulan alamat dapat dikembalikan menggunakan cmdlet Get-AzApplicationGatewayBackendAddressPool.
Setelah memiliki ID, Anda dapat menggunakan parameter *DefaultBackendAddressPoolId* , bukan parameter *DefaultBackendAddressPool* .
Misalnya:

-DefaultBackendAddressPoolId "/subscriptions/39c54063-01d3-4abf-8f4c-234777bc1f10/resourceGroups/appgw-rg/providers/Microsoft.Network/applicationGateways/appgwtest/backendAddressPools/ContosoAddressPool"

Kumpulan alamat backend mewakili alamat IP di server backend.
Alamat IP ini harus dimiliki oleh subnet jaringan virtual atau harus alamat IP publik.

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
Menentukan referensi objek ke kumpulan pengaturan HTTP backend yang akan ditambahkan ke pengaturan konfigurasi aturan jalur gateway.
Anda dapat membuat referensi objek ini menggunakan cmdlet dan sintaks New-AzApplicationGatewayBackendHttpSetting yang serupa dengan ini:

$HttpSettings = New-AzApplicationGatewayBackendHttpSetting -Name "ContosoHttpSetings" -Port 80 -Protocol "Http" -CookieBasedAffinity "Disabled"

Variabel yang dihasilkan, $HttpSettings, kemudian dapat digunakan sebagai nilai parameter untuk parameter *DefaultBackendAddressPool* :

-DefaultBackendHttpSettings $HttpSettings

Pengaturan HTTP backend mengonfigurasi properti seperti port, protokol, dan afinitas berbasis cookie untuk kumpulan backend.
Jika menggunakan parameter ini, Anda tidak dapat menggunakan parameter *DefaultBackendHttpSettingsId* dalam perintah yang sama.

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
Menentukan ID kumpulan pengaturan HTTP backend yang sudah ada yang bisa ditambahkan ke pengaturan konfigurasi aturan jalur gateway.
ID pengaturan HTTP dapat dikembalikan menggunakan cmdlet Get-AzApplicationGatewayBackendHttpSetting.
Setelah memiliki ID, Anda dapat menggunakan parameter *DefaultBackendHttpSettingsId* , bukan parameter *DefaultBackendHttpSettings* .
Misalnya:

-DefaultBackendSettings Id "/subscriptions/39c54063-01d3-4abf-8f4c-234777bc1f10/resourceGroups/appgw-rg/providers/Microsoft.Network/applicationGateways/appgwtest/backendHttpSettingsCollection/ContosoHttpSettings"

Pengaturan HTTP backend mengonfigurasi properti seperti port, protokol, dan afinitas berbasis cookie untuk kumpulan backend.
Jika menggunakan parameter ini, Anda tidak dapat menggunakan parameter *DefaultBackendHttpSettings* dalam perintah yang sama.

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
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

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

### -Konfigurasi Ulang
Konfigurasi Ulang gateway aplikasi

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
ID konfigurasi ulang gateway aplikasi

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

###  
**New-AzApplicationGatewayPathRuleConfig** tidak menerima input pipelined.

## OUTPUTS

###  
**New-AzApplicationGatewayPathRuleConfig** membuat instans baru objek **Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayPathRule** .

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


