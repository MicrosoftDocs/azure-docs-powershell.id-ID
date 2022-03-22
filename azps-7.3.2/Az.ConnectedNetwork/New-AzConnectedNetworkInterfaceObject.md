---
external help file: ''
Module Name: Az.ConnectedNetwork
online version: https://docs.microsoft.com/powershell/module/az.ConnectedNetwork/new-AzConnectedNetworkInterfaceObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConnectedNetwork/help/New-AzConnectedNetworkInterfaceObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConnectedNetwork/help/New-AzConnectedNetworkInterfaceObject.md
ms.openlocfilehash: ce6e995411b141737c4d21368565444d8df631b2
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140010224"
---
# New-AzConnectedNetworkInterfaceObject

## SYNOPSIS
Membuat objek dalam memori untuk NetworkInterface

## SYNTAX

```
New-AzConnectedNetworkInterfaceObject [-IPConfiguration <INetworkInterfaceIPConfiguration[]>]
 [-MacAddress <String>] [-Name <String>] [-VMSwitchType <VMSwitchType>] [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk NetworkInterface

## EXAMPLES

### Contoh 1: Membuat objek dalam memori untuk NetworkInterface
```powershell
PS C:\> New-AzConnectedNetworkInterfaceObject -IPConfiguration $ipconf1 -Name "mrmmanagementnic1" -VMSwitchType "Management"

MacAddress Name              VMSwitchType
---------- ----              ------------
           mrmmanagementnic1 Management
```

Membuat objek dalam memori untuk NetworkInterface

## PARAMETERS

### -IPConfiguration
Daftar konfigurasi IP antarmuka jaringan.
Untuk membuat, lihat bagian CATATAN untuk properti IPCONFIGURATION dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ConnectedNetwork.Models.Api20210501.INetworkInterfaceIPConfiguration[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MacAddress
Alamat MAC antarmuka jaringan.

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

### -Nama
Nama antarmuka jaringan.

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

### -VMSwitchType
Tipe sakelar VM.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ConnectedNetwork.Support.VMSwitchType
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ConnectedNetwork.Models.Api20210501.NetworkInterface

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


IPCONFIGURATION <INetworkInterfaceIPConfiguration[]>: Daftar konfigurasi IP antarmuka jaringan.
  - `[DnsServer <String[]>]`: Daftar alamat IP server DNS.
  - `[Gateway <String>]`: Nilai gateway.
  - `[IPAddress <String>]`: Nilai alamat IP.
  - `[IPAllocationMethod <IPAllocationMethod?>]`: metode alokasi alamat IP.
  - `[IPVersion <IPVersion?>]`: versi alamat IP.
  - `[Subnet <String>]`: Nilai subnet.

## RELATED LINKS

