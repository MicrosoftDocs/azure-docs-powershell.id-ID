---
external help file: Microsoft.Azure.Commands.AnalysisServices.dll-Help.xml
Module Name: AzureRM.AnalysisServices
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.analysisservices/new-azurermanalysisservicesfirewallconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/AnalysisServices/Commands.AnalysisServices/help/New-AzureRmAnalysisServicesFirewallConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/AnalysisServices/Commands.AnalysisServices/help/New-AzureRmAnalysisServicesFirewallConfig.md
ms.openlocfilehash: 2369720eb3a2df1e1c65df727cb02c1464ddc218
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132425941"
---
# New-AzureRmAnalysisServicesFirewallConfig

## SYNOPSIS
Membuat konfigurasi firewall Analysis Services baru 

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
New-AzureRmAnalysisServicesFirewallConfig [-EnablePowerBIService]
 [-FirewallRule <System.Collections.Generic.List`1[Microsoft.Azure.Commands.AnalysisServices.Models.PsAzureAnalysisServicesFirewallRule]>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
The New-AzureRmAnalysisServicesFirewallConfig creates a new firewall config object

## EXAMPLES

### Contoh 1
```
PS C:\> $rule1 = New-AzureRmAnalysisServicesFirewallRule -FirewallRuleName rule1 -RangeStart 0.0.0.0 -RangeEnd 255.255.255.255
PS C:\> $rule2 = New-AzureRmAnalysisServicesFirewallRule -FirewallRuleName rule2 -RangeStart 6.6.6.6 -RangeEnd 7.7.7.7
PS C:\> $config = New-AzureRmAnalysisServicesFirewallConfig -EnablePowerBIService -FirewallRule $rule1,$rule2
```

Membuat objek konfigurasi firewall dengan dua aturan sekaligus mengaktifkan akses dari Power BI lainnya.

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

### -EnablePowerBIService
Bendera untuk mengindikasikan apakah firewall mengizinkan akses dari Power BI

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FirewallRule
Daftar aturan firewall

```yaml
Type: System.Collections.Generic.List`1[Microsoft.Azure.Commands.AnalysisServices.Models.PsAzureAnalysisServicesFirewallRule]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### System.Collections.Generic.List'1[[Microsoft.Azure.Commands.AnalysisServices.Models.PsAzureAnalysisServicesFirewallRule, Microsoft.Azure.Commands.AnalysisServices, Version=0.6.11.0, Culture=neutral, PublicKeyToken=null]]

## OUTPUTS

### Microsoft.Azure.Commands.AnalysisServices.Models.PsAzureAnalysisServicesFirewallConfig

## CATATAN

## RELATED LINKS

[New-AzureRmAnalysisServicesFirewallRule](./New-AzureRmAnalysisServicesFirewallRule.md)
