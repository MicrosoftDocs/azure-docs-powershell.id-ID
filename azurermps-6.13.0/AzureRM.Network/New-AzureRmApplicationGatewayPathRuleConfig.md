---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
Module Name: AzureRM.Network
ms.assetid: A1F949A9-7AEF-41C1-B757-114421B79493
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.network/new-azurermapplicationgatewaypathruleconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/New-AzureRmApplicationGatewayPathRuleConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/New-AzureRmApplicationGatewayPathRuleConfig.md
ms.openlocfilehash: f8d9a4266474f18a2dd20fd4ddc0746320359f59
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143217521"
---
# New-AzureRmApplicationGatewayPathRuleConfig

## SYNOPSIS
Membuat aturan jalur gateway aplikasi.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### SetByResourceId
```
New-AzureRmApplicationGatewayPathRuleConfig -Name <String>
 -Paths <System.Collections.Generic.List`1[System.String]> [-BackendAddressPoolId <String>]
 [-BackendHttpSettingsId <String>] [-RedirectConfigurationId <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### SetByResource
```
New-AzureRmApplicationGatewayPathRuleConfig -Name <String>
 -Paths <System.Collections.Generic.List`1[System.String]>
 [-BackendAddressPool <PSApplicationGatewayBackendAddressPool>]
 [-BackendHttpSettings <PSApplicationGatewayBackendHttpSettings>]
 [-RedirectConfiguration <PSApplicationGatewayRedirectConfiguration>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzureRmApplicationGatewayPathRuleConfig** membuat aturan jalur gateway aplikasi.
Aturan yang dibuat oleh cmdlet ini bisa ditambahkan ke kumpulan pengaturan konfigurasi peta jalur URL lalu ditetapkan ke gateway.
Pengaturan konfigurasi peta jalur digunakan dalam penyeimbangan muatan gateway aplikasi.

## EXAMPLES

### Contoh 1
```
PS C:\>$Gateway = Get-AzureRmApplicationGateway -Name "ContosoApplicationGateway"
PS C:\> $AddressPool = New-AzureRmApplicationGatewayBackendAddressPool -Name "ContosoAddressPool" -BackendIPAddresses "192.168.1.1", "192.168.1.2"
PS C:\> $HttpSettings = New-AzureRmApplicationGatewayBackendHttpSettings -Name "ContosoHttpSetings" -Port 80 -Protocol "Http" -CookieBasedAffinity "Disabled"
PS C:\> $PathRuleConfig = New-AzureRmApplicationGatewayPathRuleConfig -Name "base" -Paths "/base" -BackendAddressPool $AddressPool -BackendHttpSettings $HttpSettings
PS C:\> Add-AzureRmApplicationGatewayUrlPathMapConfig -ApplicationGateway $Gateway -Name "ContosoUrlPathMap" -PathRules $PathRuleConfig -DefaultBackendAddressPool $AddressPool -DefaultBackendHttpSettings $HttpSettings
```

Perintah ini membuat aturan jalur gateway aplikasi baru lalu menggunakan cmdlet **Add-AzureRmApplicationGatewayUrlPathMapConfig** untuk menetapkan aturan tersebut ke gateway aplikasi.
Untuk melakukan ini, perintah pertama membuat referensi objek ke gateway ContosoApplicationGateway.
Referensi objek ini disimpan dalam variabel bernama $Gateway.
Dua perintah berikutnya membuat kumpulan alamat backend dan objek pengaturan HTTP backend; objek ini (disimpan dalam variabel $AddressPool dan $HttpSettings) diperlukan untuk membuat objek aturan jalur.
Perintah keempat membuat objek aturan jalur dan disimpan dalam variabel bernama $PathRuleConfig.
Perintah kelima menggunakan **Add-AzureRmApplicationGatewayUrlPathMapConfig** untuk menambahkan pengaturan konfigurasi dan aturan jalur baru yang terdapat dalam pengaturan tersebut ke ContosoApplicationGateway.

## PARAMETERS

### -BackendAddressPool
Menentukan referensi objek ke kumpulan pengaturan kumpulan alamat backend untuk ditambahkan ke pengaturan konfigurasi aturan jalur gateway.
Anda dapat membuat referensi objek ini menggunakan cmdlet dan sintaks New-AzureRmApplicationGatewayBackendAddressPool yang serupa dengan ini: `$AddressPool = New-AzureRmApplicationGatewayBackendAddressPool -Name "ContosoAddressPool" -BackendIPAddresses "192.168.1.1", "192.168.1.2"`
Perintah sebelumnya menambahkan dua alamat IP (192.16.1.1 dan 192.168.1.2) ke kumpulan alamat.
Perhatikan bahwa alamat IP diapit dalam tanda kutip dan dipisahkan dengan menggunakan koma.
Variabel yang dihasilkan, $AddressPool, kemudian dapat digunakan sebagai nilai parameter untuk parameter *DefaultBackendAddressPool* .
Kumpulan alamat backend mewakili alamat IP di server backend.
Alamat IP ini harus dimiliki oleh subnet jaringan virtual atau harus alamat IP publik.
Jika menggunakan parameter ini, Anda tidak dapat menggunakan parameter *DefaultBackendAddressPoolId* dalam perintah yang sama.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayBackendAddressPool
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
ID kumpulan alamat dapat dikembalikan menggunakan cmdlet Get-AzureRmApplicationGatewayBackendAddressPool.
Setelah memiliki ID, Anda dapat menggunakan parameter *DefaultBackendAddressPoolId* , bukan parameter *DefaultBackendAddressPool* .
Misalnya: -DefaultBackendAddressPoolId "/subscriptions/39c54063-01d3-4abf-8f4c-234777bc1f10/resourceGroups/appgw-rg/providers/Microsoft.Network/applicationGateways/appgwtest/backendAddressPools/ContosoAddressPool" Kumpulan alamat backend mewakili alamat IP di server backend.
Alamat IP ini harus dimiliki oleh subnet jaringan virtual atau harus alamat IP publik.

```yaml
Type: System.String
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
Anda dapat membuat referensi objek ini menggunakan cmdlet dan sintaks New-AzureRmApplicationGatewayBackendHttpSettings serupa dengan ini: $HttpSettings = New-AzureRmApplicationGatewayBackendHttpSettings -Name "ContosoHttpSetings" -Port 80 -Protocol "Http" -CookieBasedAffinity "Disabled" Variabel yang dihasilkan, $HttpSettings, dapat digunakan sebagai nilai parameter untuk parameter *DefaultBackendAddressPool* : -DefaultBackendHttpSettings $HttpSettings Pengaturan HTTP backend mengonfigurasi properti seperti port, protokol, dan affinity berbasis cookie untuk kumpulan backend.
Jika menggunakan parameter ini, Anda tidak dapat menggunakan parameter *DefaultBackendHttpSettingsId* dalam perintah yang sama.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayBackendHttpSettings
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
ID pengaturan HTTP dapat dikembalikan menggunakan cmdlet Get-AzureRmApplicationGatewayBackendHttpSettings.
Setelah memiliki ID, Anda dapat menggunakan parameter *DefaultBackendHttpSettingsId* , bukan parameter *DefaultBackendHttpSettings* .
Misalnya: -DefaultBackendSettings Id "/subscriptions/39c54063-01d3-4abf-8f4c-234777bc1f10/resourceGroups/appgw-rg/providers/Microsoft.Network/applicationGateways/appgwtest/backendHttpSettingsCollection/ContosoHttpSettings" Pengaturan HTTP backend mengonfigurasi properti seperti port, protokol, dan affinity berbasis cookie untuk kolam backend.
Jika menggunakan parameter ini, Anda tidak dapat menggunakan parameter *DefaultBackendHttpSettings* dalam perintah yang sama.

```yaml
Type: System.String
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
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
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
Type: System.String
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
Type: Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayRedirectConfiguration
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
Type: System.String
Parameter Sets: SetByResourceId
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

### Tidak

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayPathRule

## NOTES

## RELATED LINKS

[Add-AzureRmApplicationGatewayUrlPathMapConfig](./Add-AzureRmApplicationGatewayUrlPathMapConfig.md)

[Get-AzureRmApplicationGateway](./Get-AzureRmApplicationGateway.md)

[Get-AzureRmApplicationGatewayUrlPathMapConfig](./Get-AzureRmApplicationGatewayUrlPathMapConfig.md)

[New-AzureRmApplicationGatewayBackendAddressPool](./New-AzureRmApplicationGatewayBackendAddressPool.md)

[New-AzureRmApplicationGatewayBackendHttpSettings](./New-AzureRmApplicationGatewayBackendHttpSettings.md)

[New-AzureRmApplicationGatewayPathRuleConfig](./New-AzureRmApplicationGatewayPathRuleConfig.md)

[New-AzureRmApplicationGatewayUrlPathMapConfig](./New-AzureRmApplicationGatewayUrlPathMapConfig.md)

[Remove-AzureRmApplicationGatewayUrlPathMapConfig](./Remove-AzureRmApplicationGatewayUrlPathMapConfig.md)

[Set-AzureRmApplicationGatewayUrlPathMapConfig](./Set-AzureRmApplicationGatewayUrlPathMapConfig.md)


