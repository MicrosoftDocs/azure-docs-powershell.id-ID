---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
Module Name: AzureRM.Network
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.network/remove-azurermloadbalanceroutboundruleconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/Remove-AzureRmLoadBalancerOutboundRuleConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/Remove-AzureRmLoadBalancerOutboundRuleConfig.md
ms.openlocfilehash: 1a21f275850271934e6f95bf0e00d90ff6db78da1d35b043d0c032e683c8b8dc
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "140856947"
---
# Remove-AzureRmLoadBalancerOutboundRuleConfig

## SYNOPSIS
Menghapus konfigurasi aturan keluar dari penyeimbang muat.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Remove-AzureRmLoadBalancerOutboundRuleConfig -LoadBalancer <PSLoadBalancer> -Name <String>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzureRmLoadBalancerOutboundRuleConfig** menghapus konfigurasi aturan keluar dari penyeimbang muat Azure.

## EXAMPLES

### Contoh 1: Menghapus aturan keluar dari penyeimbang muat Azure
```powershell
PS C:\>$slb = Get-AzureRmLoadBalancer -ResourceGroupName "MyResourceGroup" -Name "MyLoadBalancer"
PS C:\>Remove-AzureRmLoadBalancerOutboundRuleConfig -Name "RuleName" -LoadBalancer $slb
PS C:\>Set-AzureRmLoadBalancer -LoadBalancer $slb
```

Perintah pertama mendapatkan penyeimbang muat yang terkait dengan konfigurasi aturan keluar yang ingin Anda hapus, lalu menyimpannya di $slb keluar.
Perintah kedua menghapus konfigurasi aturan keluar terkait dari penyeimbang muat.
Perintah ketiga memperbarui penyeimbang muat.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

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

### -LoadBalancer
Referensi dari sumber daya penyeimbang muat.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSLoadBalancer
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Nama
Nama aturan keluar

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

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak berjalan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Network.Models.PSLoadBalancer

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSLoadBalancer

## CATATAN

## RELATED LINKS
