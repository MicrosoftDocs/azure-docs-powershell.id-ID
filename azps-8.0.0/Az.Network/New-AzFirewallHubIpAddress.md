---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/new-azfirewallhubipaddress
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzFirewallHubIpAddress.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzFirewallHubIpAddress.md
ms.openlocfilehash: 12bd0b8ba0161a88f3bcb70b49fcd1cd1501d551
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145512646"
---
# New-AzFirewallHubIpAddress

## SYNOPSIS
Alamat IP diasosiasikan ke firewall di hub virtual

## SYNTAX

```
New-AzFirewallHubIpAddress [-PrivateIPAddress <String>] [-PublicIP <PSAzureFirewallHubPublicIpAddresses>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Alamat IP diasoicated ke firewall di hub virtual. Ini bisa berupa alamat publik dan privat

## EXAMPLES

### Contoh 1
```powershell
$fwpips = New-AzFirewallHubPublicIpAddress -Count 2
New-AzFirewallHubIpAddress -PublicIP $fwpips
```

Contoh ini membuat objek alamat Ip Hub dengan hitungan 2 IP publik. Objek HubIPAddress dikaitkan dengan firewall di hub virtual.

## PARAMETERS

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

### -PrivateIPAddress
Alamat IP privat Firewall yang dilampirkan ke Hub

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

### -PublicIP
Alamat IP Firewall yang dilampirkan ke hub

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSAzureFirewallHubPublicIpAddresses
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

### Microsoft.Azure.Commands.Network.Models.PSAzureFirewallHubIpAddresses

## NOTES

## RELATED LINKS
