---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/get-azvpnclientipsecparameter
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzVpnClientIpsecParameter.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzVpnClientIpsecParameter.md
ms.openlocfilehash: 0e25f30f113cfd2bc11ead7d1a01d4531f62ffeb
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144222050"
---
# Get-AzVpnClientIpsecParameter

## SYNOPSIS
Mendapatkan parameter vpn Ipsec yang diatur di Virtual Network Gateway untuk koneksi Titik ke situs.

## SYNTAX

```
Get-AzVpnClientIpsecParameter [-Name <String>] -ResourceGroupName <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Gateway Virtual Network adalah objek yang mewakili gateway Anda di Azure.
Cmdlet **Get-AzVpnClientIpsecParameter** mengembalikan objek parameter ipsec vpn Anda yang diatur pada gateway di Azure berdasarkan Nama Gateway dan Nama Grup Sumber Daya.

## EXAMPLES

### Contoh 1: Mendapatkan parameter vpn Ipsec yang diatur pada Virtual Network Gateway untuk koneksi Titik ke situs.
```powershell
$VpnClientIPsecParameters = Get-AzVpnClientIpsecParameter -Name myGateway -ResourceGroupName myRG
```

Mengembalikan objek parameter ipsec vpn yang diatur pada gateway Virtual Network dengan nama "myGateway" dalam grup sumber daya "myRG"

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

### -Name
Nama sumber daya.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ResourceName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSVpnClientIPsecParameters

## NOTES

## RELATED LINKS

[New-AzVpnClientIpsecParameter](./New-AzVpnClientIpsecParameter.md)

[Remove-AzVpnClientIpsecParameter](./Remove-AzVpnClientIpsecParameter.md)

[Set-AzVpnClientIpsecParameter](./Set-AzVpnClientIpsecParameter.md)
