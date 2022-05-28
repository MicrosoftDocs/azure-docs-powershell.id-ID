---
external help file: ''
Module Name: Az.DnsResolver
online version: https://docs.microsoft.com/powershell/module/az.dnsresolver/new-azdnsresolveripconfigurationobject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DnsResolver/help/New-AzDnsResolverIPConfigurationObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DnsResolver/help/New-AzDnsResolverIPConfigurationObject.md
ms.openlocfilehash: 2db80990f6baf805ce7d4071207fc0de5a1c6e3c
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145515250"
---
# New-AzDnsResolverIPConfigurationObject

## SYNOPSIS
Membuat objek dalam memori untuk IPConfiguration

## SYNTAX

```
New-AzDnsResolverIPConfigurationObject [-PrivateIPAddress <String>]
 [-PrivateIPAllocationMethod <IPAllocationMethod>] [-SubnetId <String>] [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk IPConfiguration

## EXAMPLES

### Contoh 1: Membuat IPConfiguration
```powershell
New-AzDnsResolverIPConfigurationObject -PrivateIPAddress 1.1.2.12 -PrivateIPAllocationMethod Dynamic -SubnetId /subscriptions/0e5a46b1-de0b-4ec3-a5d7-dda908b4e076/resourceGroups/powershell-test-rg/providers/Microsoft.Network/virtualNetworks/psvirtualnetworkname44yqt9mb/subnets/pssubnetname44c6v0lr
```

```output
PrivateIPAddress PrivateIPAllocationMethod
---------------- -------------------------
1.1.2.12         Dynamic
```

Perintah ini membuat IPConfiguration

## PARAMETERS

### -PrivateIPAddress
Alamat IP privat konfigurasi IP.

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

### -PrivateIPAllocationMethod
Metode alokasi alamat IP privat.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DnsResolver.Support.IPAllocationMethod
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubnetId
ID Sumber Daya.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DnsResolver.Models.Api20200401Preview.IPConfiguration

## NOTES

ALIAS

## RELATED LINKS

