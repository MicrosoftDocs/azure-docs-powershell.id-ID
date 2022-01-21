---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/set-azapplicationgatewaysslprofile
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Set-AzApplicationGatewaySslProfile.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Set-AzApplicationGatewaySslProfile.md
ms.openlocfilehash: 4b769344cd310aaf921b0a6b50b5e0c8460d6d50
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136382085"
---
# Set-AzApplicationGatewaySslProfile

## SYNOPSIS
Memperbarui profil ssl untuk gateway aplikasi.

## SYNTAX

```
Set-AzApplicationGatewaySslProfile -ApplicationGateway <PSApplicationGateway> -Name <String>
 [-SslPolicy <PSApplicationGatewaySslPolicy>]
 [-ClientAuthConfiguration <PSApplicationGatewayClientAuthConfiguration>]
 [-TrustedClientCertificates <PSApplicationGatewayTrustedClientCertificate[]>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzApplicationGatewaySslProfile** memperbarui profil ssl untuk gateway aplikasi Azure.

## EXAMPLES

### Contoh 1
```powershell
PS C:\>$AppGw = Get-AzApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
PS C:\> $AppGw = Set-AzApplicationGatewaySslProfile -ApplicationGateway $AppGw -Name "Profile01" -ClientAuthConfiguration $newclientconfig
```

Perintah pertama mendapatkan gateway aplikasi bernama ApplicationGateway01 yang dimiliki oleh grup sumber daya yang bernama ResourceGroup01 dan menyimpannya di $AppGw lokal. Perintah kedua memperbarui profil ssl gateway aplikasi di variabel $AppGw untuk memperbarui konfigurasi auth klien ke nilai baru yang disimpan di $newclientconfig.

## PARAMETERS

### -ApplicationGateway
ApplicationGateway

```yaml
Type: PSApplicationGateway
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ClientAuthConfiguration
Pengaturan konfigurasi autentikasi klien

```yaml
Type: PSApplicationGatewayClientAuthConfiguration
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
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama profil SSL

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

### -SslPolicy
Kebijakan SSL

```yaml
Type: PSApplicationGatewaySslPolicy
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TrustedClientCertificates
Rantai sertifikat CA klien tepercaya

```yaml
Type: PSApplicationGatewayTrustedClientCertificate[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGateway

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGateway

## CATATAN

## RELATED LINKS

[Add-AzApplicationGatewaySslProfile](./Add-AzApplicationGatewaySslProfile.md)

[New-AzApplicationGatewaySslProfile](./New-AzApplicationGatewaySslProfile.md)

[Get-AzApplicationGatewaySslProfile](./Get-AzApplicationGatewaySslProfile.md)

[Remove-AzApplicationGatewaySslProfile](./Remove-AzApplicationGatewaySslProfile.md)