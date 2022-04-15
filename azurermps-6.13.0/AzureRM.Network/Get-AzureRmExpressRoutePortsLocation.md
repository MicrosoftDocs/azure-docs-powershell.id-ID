---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
Module Name: AzureRM.Network
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.network/get-azurermexpressrouteportslocation
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/Get-AzureRmExpressRoutePortsLocation.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Network/Commands.Network/help/Get-AzureRmExpressRoutePortsLocation.md
ms.openlocfilehash: 5d077991e42da0709019df1dccdd83f03659ca49
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142138963"
---
# Get-AzureRmExpressRoutePortsLocation

## SYNOPSIS
Mendapatkan lokasi di mana sumber daya ExpressRoutePort tersedia.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Get-AzureRmExpressRoutePortsLocation [-LocationName <String>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmExpressRoutePortsLocation** digunakan untuk mengambil lokasi di mana sumber daya ExpressRoutePort tersedia. Dengan lokasi tertentu sebagai input, cmdlet menampilkan detail lokasi tersebut, yaitu daftar bandwidth yang tersedia di lokasi tersebut.


## EXAMPLES

### Contoh 1
```powershell
PS C:\> Get-AzureRmExpressRoutePortsLocation
```

Mencantumkan lokasi sumber daya ExpressRoutePort yang tersedia.

### Contoh 2
```powershell
PS C:\> Get-AzureRmExpressRoutePortsLocation -LocationName $loc
```

Mencantumkan bandwidth ExpressRoutePort yang tersedia di $loc lokasi.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LocationName
Nama lokasi.

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSExpressRoutePortsLocation

## CATATAN

## RELATED LINKS
