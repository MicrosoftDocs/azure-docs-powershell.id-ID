---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/get-azexpressrouteportslocation
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzExpressRoutePortsLocation.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzExpressRoutePortsLocation.md
ms.openlocfilehash: 64f9cbdc53e7c0a4de74748ba2b124798f1a48eb
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136559689"
---
# Get-AzExpressRoutePortsLocation

## SYNOPSIS
Dapatkan lokasi sumber daya ExpressRoutePort yang tersedia.

## SYNTAX

```
Get-AzExpressRoutePortsLocation [-LocationName <String>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzExpressRoutePortsLocation** digunakan untuk mengambil lokasi tempat sumber daya ExpressRoutePort tersedia. Jika lokasi tertentu sebagai input, cmdlet akan menampilkan detail lokasi tersebut seperti daftar bandwidth yang tersedia di lokasi tersebut.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Get-AzExpressRoutePortsLocation
```

Mencantumkan lokasi tempat sumber daya ExpressRoutePort tersedia.

### Contoh 2
```powershell
PS C:\> Get-AzExpressRoutePortsLocation -LocationName $loc
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSExpressRoutePortsLocation

## CATATAN

## RELATED LINKS
