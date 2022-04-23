---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.Network.dll-Help.xml
ms.assetid: 88AB3621-7C80-41BA-BE49-4F8F9C46BCF5
online version: ''
schema: 2.0.0
ms.openlocfilehash: b3e927cb9ce65a21442c0fec99f2d3ad00cf626d
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143104679"
---
# Get-AzureVirtualNetworkGatewayConnection

## SYNOPSIS
Mendapatkan koneksi gateway jaringan virtual.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureVirtualNetworkGatewayConnection [-GatewayId <String>] [-ConnectedEntityId <String>]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureVirtualNetworkGatewayConnection** mendapatkan koneksi gateway jaringan virtual Azure.

## EXAMPLES

## PARAMETERS

### -ConnectedEntityId
Menentukan ID entitas yang tersambung.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GatewayId
Menentukan ID gateway.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profil
Menentukan profil Azure tempat cmdlet ini dibaca.
Jika Anda tidak menentukan profil, cmdlet ini akan dibaca dari profil default lokal.

```yaml
Type: AzureSMProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Baru-AzureVirtualNetworkGatewayConnection](./New-AzureVirtualNetworkGatewayConnection.md)

[Hapus-AzureVirtualNetworkGatewayConnection](./Remove-AzureVirtualNetworkGatewayConnection.md)

[Mengatur ulang AzureVirtualNetworkGatewayConnection](./Reset-AzureVirtualNetworkGatewayConnection.md)
