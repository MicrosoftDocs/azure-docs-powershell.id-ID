---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.Network.dll-Help.xml
ms.assetid: F6A89D39-18AD-4087-823C-63FA0A3690E7
online version: ''
schema: 2.0.0
ms.openlocfilehash: f30f76bea004aea74d4b42e100fc00dc79f4d879
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143104648"
---
# Get-AzureVirtualNetworkGatewayDiagnostics

## SYNOPSIS
Mendapatkan hasil diagnostik gateway jaringan virtual Azure.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureVirtualNetworkGatewayDiagnostics -GatewayId <String> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureVirtualNetworkGatewayDiagnostics** mendapatkan hasil diagnostik gateway jaringan virtual Azure.

## EXAMPLES

## PARAMETERS

### -GatewayId
Menentukan ID gateway.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profil
Menentukan profil Azure tempat cmdlet ini dibaca. Jika Anda tidak menentukan profil, cmdlet ini akan dibaca dari profil default lokal.

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

[Start-AzureVirtualNetworkGatewayDiagnostics](./Start-AzureVirtualNetworkGatewayDiagnostics.md)

[Stop-AzureVirtualNetworkGatewayDiagnostics](./Stop-AzureVirtualNetworkGatewayDiagnostics.md)


