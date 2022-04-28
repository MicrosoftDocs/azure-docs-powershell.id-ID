---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: 0780CB09-9C3B-468A-A718-3A646FE3D152
online version: https://docs.microsoft.com/powershell/module/az.network/test-azprivateipaddressavailability
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Test-AzPrivateIPAddressAvailability.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Test-AzPrivateIPAddressAvailability.md
ms.openlocfilehash: 228e5ac181aeb272bc898509d3b944f56aec014d
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144210398"
---
# Test-AzPrivateIPAddressAvailability

## SYNOPSIS
Menguji ketersediaan alamat IP privat di jaringan virtual.

## SYNTAX

### TestByResource
```
Test-AzPrivateIPAddressAvailability -VirtualNetwork <PSVirtualNetwork> -IPAddress <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### TestByResourceId
```
Test-AzPrivateIPAddressAvailability -ResourceGroupName <String> -VirtualNetworkName <String>
 -IPAddress <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
**Cmdlet Test-AzPrivateIPAddressAvailability** menguji apakah alamat IP privat tertentu tersedia di jaringan virtual.
Cmdlet ini mengembalikan daftar alamat IP privat yang tersedia jika alamat IP privat yang diminta diambil.

## EXAMPLES

### Contoh 1: Menguji apakah alamat IP tersedia menggunakan alur
```powershell
Get-AzVirtualNetwork -Name $vnetName -ResourceGroupName $rgname | Test-AzPrivateIPAddressAvailability -IPAddress "10.0.1.10"
```

Perintah ini mendapatkan jaringan virtual dan menggunakan operator alur untuk meneruskannya ke **Test-AzPrivateIPAddressAvailability**, yang menguji apakah alamat IP privat yang ditentukan tersedia.

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

### -IPAddress
Menentukan alamat IP yang akan diuji.

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

### -ResourceGroupName
Menentukan nama grup sumber daya untuk jaringan virtual.

```yaml
Type: System.String
Parameter Sets: TestByResourceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualNetwork
Menentukan objek **PSVirtualNetwork** .

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSVirtualNetwork
Parameter Sets: TestByResource
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VirtualNetworkName
Menentukan nama jaringan virtual.

```yaml
Type: System.String
Parameter Sets: TestByResourceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Network.Models.PSVirtualNetwork

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSIPAddressAvailabilityResult

## NOTES

## RELATED LINKS

[Pulihkan-AzSqlDatabase](./Get-AzVirtualNetwork.md)


