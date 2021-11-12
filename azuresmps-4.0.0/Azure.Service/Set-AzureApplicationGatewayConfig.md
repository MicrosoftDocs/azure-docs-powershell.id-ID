---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.Network.dll-Help.xml
ms.assetid: D7D99AFA-A85E-43DA-9F2F-8FFD34048E00
online version: ''
schema: 2.0.0
ms.openlocfilehash: 7d6224fcb961b0ac60829ab067574f09e1199fb24da306907ae715da8e43f0e9
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132417714"
---
# Set-AzureApplicationGatewayConfig

## SYNOPSIS
Mengonfigurasi gateway aplikasi.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### configFile
```
Set-AzureApplicationGatewayConfig -Name <String> -ConfigFile <String> [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

### configObject
```
Set-AzureApplicationGatewayConfig -Name <String> -Config <ApplicationGatewayConfiguration>
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureApplicationGatewayConfig** mengonfigurasi gateway aplikasi.

## EXAMPLES

### Contoh 1: Mengonfigurasi gateway aplikasi dengan menggunakan objek konfigurasi
```
PS C:\> $ConfigReturnObject = Get-AzureApplicationGatewayConfig -Name "ApplicationGateway02"
PS C:\> Set-AzureApplicationGatewayConfig -Name "ApplicationGateway06" -Config $ConfigReturnObject
```

Perintah pertama mendapatkan objek konfigurasi untuk gateway aplikasi yang bernama ApplicationGateway02 dengan menggunakan cmdlet **Get-AzureApplicationGatewayConfig.**
Perintah menyimpannya di $ConfigReturnObject variabel.

Perintah kedua mengatur konfigurasi untuk aplikasi bernama ApplicationGateway06 dengan menggunakan objek konfigurasi gateway aplikasi yang disimpan di $ConfigReturnObject lain.

### Contoh 2: Mengonfigurasi gateway aplikasi dengan menggunakan file konfigurasi
```
PS C:\> Set-AzureApplicationGatewayConfig -Name "ApplicationGateway06" -ConfigFile "D:\config.xml"
```

Perintah ini mengatur konfigurasi untuk aplikasi bernama ApplicationGateway06 dengan menggunakan file konfigurasi gateway aplikasi di lokasi yang ditentukan.

### Contoh 3: Mengubah konfigurasi menggunakan objek konfigurasi
```
PS C:\> $ConfigReturnObject = Get-AzureApplicationGatewayConfig -Name "ApplicationGateway06"
PS C:\> $ConfigReturnObject.Config.FrontendPorts[0].Port = 443
PS C:\> $ConfigReturnObject | Set-AzureApplicationGatewayConfig -Name "ApplicationGateway06"
```

Perintah pertama mendapatkan objek konfigurasi untuk gateway aplikasi yang bernama ApplicationGateway06 dengan menggunakan cmdlet **Get-AzureApplicationGatewayConfig.**
Perintah menyimpannya di $ConfigReturnObject variabel.

Perintah kedua menetapkan nilai port ke properti **Port** dalam objek yang disimpan di $ConfigReturnObject.

Perintah terakhir melewati pembaruan $ConfigReturnObject cmdlet saat ini.

## PARAMETERS

### -Config
Menentukan objek konfigurasi gateway aplikasi.
Cmdlet ini menetapkan konfigurasi yang ditentukan parameter ini ke gateway aplikasi.

```yaml
Type: ApplicationGatewayConfiguration
Parameter Sets: configObject
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ConfigFile
Menentukan jalur file konfigurasi, dalam format XML, untuk gateway aplikasi.
Cmdlet ini menetapkan konfigurasi yang ditentukan parameter ini ke gateway aplikasi.

```yaml
Type: String
Parameter Sets: configFile
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nama
Menentukan nama gateway aplikasi yang dikonfigurasi cmdlet ini.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### System.String, Microsoft.Azure.Networking.ApplicationGatewayObjectModel.ApplicationGatewayConfiguration

## OUTPUTS

### Microsoft.WindowsAzure.Management.ApplicationGateway.Models.ApplicationGatewayOperationResponse

## CATATAN

## RELATED LINKS

[Get-AzureApplicationGatewayConfig](./Get-AzureApplicationGatewayConfig.md)


