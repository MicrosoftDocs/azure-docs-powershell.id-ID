---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/new-azfirewallhubpublicipaddress
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzFirewallHubPublicIpAddress.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzFirewallHubPublicIpAddress.md
ms.openlocfilehash: b2758d74b7b59d1102c27e3fddb10f02ca63d130
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145676056"
---
# New-AzFirewallHubPublicIpAddress

## SYNOPSIS
Ip Publik diasoicated ke firewall di hub virtual

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.network/new-azfirewallhubpublicipaddress) untuk informasi terbaru.

## SYNTAX

```
New-AzFirewallHubPublicIpAddress [-Count <Int32>] [-Addresses <PSAzureFirewallPublicIpAddress[]>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Ip Publik diasoicated ke firewall di hub virtual

## EXAMPLES

### Contoh 1
```powershell
New-AzFirewallHubPublicIpAddress -Count 2
```

Ini akan membuat 2 ip publik pada firewall yang dilampirkan ke hub virtual. Ini akan membuat alamat ip di backend. Kami tidak dapat menyediakan ipaddress secara eksplisit untuk firewall baru.

### Contoh 2
```powershell
$publicIp1 = New-AzFirewallPublicIpAddress -Address 10.2.3.4
$publicIp2 = New-AzFirewallPublicIpAddress -Address 20.56.37.46
New-AzFirewallHubPublicIpAddress -Count 3 -Addresses $publicIp1, $publicIp2
```

Ini akan membuat 1 ip publik baru pada firewall dengan mempertahankan $publicIp 1, $publicIp 2 yang sudah ada di firewall.

## PARAMETERS

### -Alamat
Alamat IP Publik Firewall yang dilampirkan ke hub

```yaml
Type: PSAzureFirewallPublicIpAddress[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Count
Jumlah alamat IP publik

```yaml
Type: Int32
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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSAzureFirewallHubPublicIpAddresses

## NOTES

## RELATED LINKS
