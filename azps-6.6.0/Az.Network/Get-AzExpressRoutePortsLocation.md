---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/get-azexpressrouteportslocation
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzExpressRoutePortsLocation.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzExpressRoutePortsLocation.md
ms.openlocfilehash: 662f0661a8e1348d6f9614ed812adc032f9fbae2
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "139935925"
---
# Get-AzExpressRoutePortsLocation

## SYNOPSIS
Dapatkan lokasi sumber daya ExpressRoutePort yang tersedia.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.network/get-azexpressrouteportslocation) untuk informasi terkini.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSExpressRoutePortsLocation

## CATATAN

## RELATED LINKS
