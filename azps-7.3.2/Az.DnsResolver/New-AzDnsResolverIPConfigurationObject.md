---
external help file: ''
Module Name: Az.DnsResolver
online version: https://docs.microsoft.com/powershell/module/az.dnsresolver/new-azdnsresolveripconfigurationobject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DnsResolver/help/New-AzDnsResolverIPConfigurationObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DnsResolver/help/New-AzDnsResolverIPConfigurationObject.md
ms.openlocfilehash: b7699c6c366f56209cc5042abbce45d8662034c7
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142110761"
---
# New-AzDnsResolverIPConfigurationObject

## SYNOPSIS
Membuat objek dalam memori untuk IPConfiguration

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.dnsresolver/new-azdnsresolveripconfigurationobject) untuk informasi terbaru.

## SYNTAX

```
New-AzDnsResolverIPConfigurationObject [-PrivateIPAddress <String>]
 [-PrivateIPAllocationMethod <IPAllocationMethod>] [-SubnetId <String>] [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk IPConfiguration

## EXAMPLES

### Contoh 1: Membuat Konfigurasi IP
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DnsResolver.Models.Api20200401Preview.IPConfiguration

## CATATAN

ALIAS

## RELATED LINKS

