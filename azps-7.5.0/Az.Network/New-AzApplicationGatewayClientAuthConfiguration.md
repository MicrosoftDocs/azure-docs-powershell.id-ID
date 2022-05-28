---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/new-azapplicationgatewayclientauthconfiguration
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzApplicationGatewayClientAuthConfiguration.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzApplicationGatewayClientAuthConfiguration.md
ms.openlocfilehash: 3c20b9c19a61c7ebc573e897d65a5d0a9fdde0e7
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145678324"
---
# New-AzApplicationGatewayClientAuthConfiguration

## SYNOPSIS
Membuat konfigurasi autentikasi klien baru untuk profil SSL.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.network/new-azapplicationgatewayclientauthconfiguration) untuk informasi terbaru.

## SYNTAX

```
New-AzApplicationGatewayClientAuthConfiguration [-VerifyClientCertIssuerDN]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzApplicationGatewayClientAuthConfiguration** membuat konfigurasi autentikasi klien baru untuk profil SSL.

## EXAMPLES

### Contoh 1
```powershell
$clientAuthConfig = New-AzApplicationGatewayClientAuthConfiguration -VerifyClientCertIssuerDN
```

Perintah membuat konfigurasi autentikasi klien baru dan menyimpannya dalam variabel $clientAuthConfig yang akan digunakan dalam profil SSL.

## PARAMETERS

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

### -VerifyClientCertIssuerDN
Verifikasi nama penerbit sertifikat klien.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayClientAuthConfiguration

## NOTES

## RELATED LINKS

[Get-AzApplicationGatewayClientAuthConfiguration](./Get-AzApplicationGatewayClientAuthConfiguration.md)

[Remove-AzApplicationGatewayClientAuthConfiguration](./Remove-AzApplicationGatewayClientAuthConfiguration.md)

[Set-AzApplicationGatewayClientAuthConfiguration](./Set-AzApplicationGatewayClientAuthConfiguration.md)
