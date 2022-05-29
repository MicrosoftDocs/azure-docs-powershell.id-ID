---
external help file: ''
Module Name: Az.ConnectedNetwork
online version: https://docs.microsoft.com/powershell/module/az.ConnectedNetwork/new-AzConnectedNetworkInterfaceIPConfigurationObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConnectedNetwork/help/New-AzConnectedNetworkInterfaceIPConfigurationObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConnectedNetwork/help/New-AzConnectedNetworkInterfaceIPConfigurationObject.md
ms.openlocfilehash: b7d8a40f53ea236504278abffb620b3546a2b671
ms.sourcegitcommit: 321c644cf2161807a71e1af318fc5c5311d22e25
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/25/2022
ms.locfileid: "145785916"
---
# New-AzConnectedNetworkInterfaceIPConfigurationObject

## SYNOPSIS
Membuat objek dalam memori untuk NetworkInterfaceIPConfiguration

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.connectednetwork/new-azconnectednetworkinterfaceipconfigurationobject) untuk informasi terbaru.

## SYNTAX

```
New-AzConnectedNetworkInterfaceIPConfigurationObject [-DnsServer <String[]>] [-Gateway <String>]
 [-IPAddress <String>] [-IPAllocationMethod <IPAllocationMethod>] [-IPVersion <IPVersion>] [-Subnet <String>]
 [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk NetworkInterfaceIPConfiguration

## EXAMPLES

### Contoh 1: Membuat objek dalam memori untuk NetworkInterfaceIPConfiguration
```powershell
PS C:\> New-AzConnectedNetworkInterfaceIPConfigurationObject -IPAllocationMethod "Dynamic" -IPVersion "IPv4"

DnsServer Gateway IPAddress IPAllocationMethod IPVersion Subnet
--------- ------- --------- ------------------ --------- ------
                            Dynamic            IPv4
```

Membuat objek dalam memori untuk NetworkInterfaceIPConfiguration

## PARAMETERS

### -DnsServer
Daftar alamat IP server DNS.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Gateway
Nilai gateway.

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

### -IPAddress
Nilai alamat IP.

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

### -IPAllocationMethod
Metode alokasi alamat IP.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ConnectedNetwork.Support.IPAllocationMethod
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPVersion
Versi alamat IP.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ConnectedNetwork.Support.IPVersion
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Subnet
Nilai subnet.

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

### Microsoft.Azure.PowerShell.Cmdlets.ConnectedNetwork.Models.Api20210501.NetworkInterfaceIPConfiguration

## NOTES

ALIAS

## RELATED LINKS

