---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/get-azexpressrouteportslocation
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzExpressRoutePortsLocation.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzExpressRoutePortsLocation.md
ms.openlocfilehash: 1383a677ce430a4e51f37847f2e97f46bda0cd0e
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144247639"
---
# Get-AzExpressRoutePortsLocation

## SYNOPSIS
Mendapatkan lokasi tempat sumber daya ExpressRoutePort tersedia.

## SYNTAX

```
Get-AzExpressRoutePortsLocation [-LocationName <String>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzExpressRoutePortsLocation** digunakan untuk mengambil lokasi tempat sumber daya ExpressRoutePort tersedia. Mengingat lokasi tertentu sebagai input, cmdlet menampilkan detail lokasi tersebut yaitu, daftar bandwidth yang tersedia di lokasi tersebut.

## EXAMPLES

### Contoh 1
```powershell
Get-AzExpressRoutePortsLocation
```

Mencantumkan lokasi tempat sumber daya ExpressRoutePort tersedia.

### Contoh 2
```powershell
Get-AzExpressRoutePortsLocation -LocationName $loc
```

Mencantumkan bandwidth ExpressRoutePort yang tersedia di lokasi $loc.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

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

### -LocationName
Nama lokasi.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSExpressRoutePortsLocation

## NOTES

## RELATED LINKS
