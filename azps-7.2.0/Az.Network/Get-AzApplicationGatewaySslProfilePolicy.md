---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/get-azapplicationgatewaysslprofilepolicy
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzApplicationGatewaySslProfilePolicy.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzApplicationGatewaySslProfilePolicy.md
ms.openlocfilehash: d88a93b08c142ecb6363b4d2a18e11f028b5a736
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140086625"
---
# Get-AzApplicationGatewaySslProfilePolicy

## SYNOPSIS
Mendapatkan kebijakan SSL profil SSL gateway aplikasi.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.network/get-azapplicationgatewaysslprofilepolicy) untuk informasi terkini.

## SYNTAX

```
Get-AzApplicationGatewaySslProfilePolicy -SslProfile <PSApplicationGatewaySslProfile>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzApplicationGatewaySslProfilePolicy** mendapatkan kebijakan SSL profil SSL gateway aplikasi.

## EXAMPLES

### Contoh 1
```powershell
PS C:\>$AppGW = Get-AzApplicationGateway -Name "ApplicationGateway01" -ResourceGroupName "ResourceGroup01"
PS C:\> $SslProfile  = Get-AzApplicationGatewaySslProfile -Name "SslProfile01" -ApplicationGateway $AppGw
PS C:\> $sslpolicy = Get-AzApplicationGatewaySslProfilePolicy -SslProfile $SslProfile
```

Perintah pertama mendapatkan gateway aplikasi bernama ApplicationGateway01 dalam grup sumber daya yang bernama ResourceGroup01 dan menyimpannya dalam $AppGw sumber daya. Perintah kedua mendapatkan profil SSL bernama SslProfile01 untuk $AppGw dan menyimpannya $SslProfile variabel. Perintah terakhir mendapatkan kebijakan SSL dari profil SSL $SslProfile menyimpannya di variabel $sslpolicy.

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

### -SslProfile
Profil SSL Gateway aplikasi

```yaml
Type: PSApplicationGatewaySslProfile
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewaySslProfile

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewaySslPolicy

## CATATAN

## RELATED LINKS

[Remove-AzApplicationGatewaySslProfilePolicy](./Remove-AzApplicationGatewaySslProfilePolicy.md)

[Set-AzApplicationGatewaySslProfilePolicy](./Set-AzApplicationGatewaySslProfilePolicy.md)
