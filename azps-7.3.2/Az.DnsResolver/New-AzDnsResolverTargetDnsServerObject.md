---
external help file: ''
Module Name: Az.DnsResolver
online version: https://docs.microsoft.com/powershell/module/az.dnsresolver/new-azdnsresolvertargetdnsserverobject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DnsResolver/help/New-AzDnsResolverTargetDnsServerObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DnsResolver/help/New-AzDnsResolverTargetDnsServerObject.md
ms.openlocfilehash: 90be4b9aa6efae1d919a73fe1315ead07b419818
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143184617"
---
# New-AzDnsResolverTargetDnsServerObject

## SYNOPSIS
Membuat objek dalam memori untuk server DNS Target

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.dnsresolver/new-azdnsresolvertargetdnsserverobject) untuk informasi terbaru.

## SYNTAX

```
New-AzDnsResolverTargetDnsServerObject [-IPAddress <String>] [-Port <Int32>] [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk server DNS Target

## EXAMPLES

### Contoh 1: Membuat server DNS Target
```powershell
New-AzDnsResolverIPConfigurationObject -PrivateIPAddress 10.0.0.3 -PrivateIPAllocationMethod Dynamic -SubnetId /subscriptions/ea40042d-63d8-4d02-9261-fb31450e6c67/resourceGroups/sampleRG/providers/Microsoft.Network/virtualNetworks/vnet-hub/subnets/test-subnet
```

```output
PrivateIPAddress PrivateIPAllocationMethod
---------------- -------------------------
1.1.2.12       Dynamic
```

Perintah ini membuat server DNS target.

## PARAMETERS

### -IPAddress
Alamat IP server DNS.

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

### -Port
Port server DNS.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DnsResolver.Models.Api20200401Preview.TargetDnsServer

## NOTES

ALIAS

## RELATED LINKS

