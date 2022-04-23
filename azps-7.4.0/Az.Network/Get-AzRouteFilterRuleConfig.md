---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/get-azroutefilterruleconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzRouteFilterRuleConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzRouteFilterRuleConfig.md
ms.openlocfilehash: fb1057660f79bf2e6b22aa3b8679b3a1c2c23c7b
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143313947"
---
# Get-AzRouteFilterRuleConfig

## SYNOPSIS
Mendapatkan aturan filter rute dalam filter rute.

## SYNTAX

```
Get-AzRouteFilterRuleConfig [-Name <String>] -RouteFilter <PSRouteFilter>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzRouteFilterRuleConfig** mendapatkan aturan filter rute atau daftar aturan filter rute dalam filter rute.

## EXAMPLES

### Contoh 1
```powershell
$rf = Get-AzRouteFilter -Name "MyRouteFilter" -ResourceGroupName "MyResourceGroup"
Get-AzRouteFilterRuleConfig -RouteFilter $rf -Name "Rule01"
Get-AzRouteFilterRuleConfig -RouteFilter $rf
```

Perintah pertama mendapatkan filter rute bernama MyRouteFilter, lalu menyimpannya dalam variabel $rf.
Perintah kedua mendapatkan aturan filter rute bernama Rule01 yang terkait dengan filter rute tersebut.
Perintah ketiga mendapatkan daftar aturan filter rute yang terkait dengan filter rute tersebut.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

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

### -Nama
Nama aturan filter rute

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

### -RouteFilter
The RouteFilter

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSRouteFilter
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Network.Models.PSRouteFilter

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSRouteFilterRule

## NOTES

## RELATED LINKS

[Add-AzRouteFilterRuleConfig](./Add-AzRouteFilterRuleConfig.md)

[New-AzRouteFilterRuleConfig](./New-AzRouteFilterRuleConfig.md)

[Remove-AzRouteFilterRuleConfig](./Remove-AzRouteFilterRuleConfig.md)

[Set-AzRouteFilterRuleConfig](./Set-AzRouteFilterRuleConfig.md)

[Get-AzRouteFilter](./Get-AzRouteFilter.md)

[Filter AzRoute Baru](./New-AzRouteFilter.md)

[Hapus-AzRouteFilter](./Remove-AzRouteFilter.md)

[Set-AzRouteFilter](./Set-AzRouteFilter.md)
