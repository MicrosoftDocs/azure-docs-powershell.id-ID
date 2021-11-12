---
external help file: Microsoft.Azure.Commands.Cdn.dll-Help.xml
Module Name: AzureRM.Cdn
ms.assetid: F93D9D7C-AC2A-4D83-87EC-4A54CD45272B
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.cdn/get-azurermcdnendpoint
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Cdn/Commands.Cdn/help/Get-AzureRmCdnEndpoint.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Cdn/Commands.Cdn/help/Get-AzureRmCdnEndpoint.md
ms.openlocfilehash: e8b8268467c8867896cbd91f324897eeb644a6949673b9295c261dcce85e624d
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132416526"
---
# Get-AzureRmCdnEndpoint

## SYNOPSIS
Mendapatkan titik CDN akhir.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### ByFieldsParameterSet (Default)
```
Get-AzureRmCdnEndpoint [-EndpointName <String>] -ProfileName <String> -ResourceGroupName <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByObjectParameterSet
```
Get-AzureRmCdnEndpoint [-EndpointName <String>] -CdnProfile <PSProfile>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRMCdnEndpoint** mendapatkan titik akhir Azure Content Delivery Network (CDN) dan data konfigurasi yang terkait.

## EXAMPLES

## PARAMETERS

### -CdnProfile
Menentukan objek CDN profil tempat titik akhir tersebut berada.

```yaml
Type: Microsoft.Azure.Commands.Cdn.Models.Profile.PSProfile
Parameter Sets: ByObjectParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EndpointName
Menentukan nama titik akhir.
Nama titik akhir bukan nama host titik akhir.

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

### -ProfileName
Menentukan nama profil tempat titik akhir tersebut berada.

```yaml
Type: System.String
Parameter Sets: ByFieldsParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya tempat titik akhir tersebut berada.

```yaml
Type: System.String
Parameter Sets: ByFieldsParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Microsoft.Azure.Commands.Cdn.Models.Profile.PSProfile
Parameter: CdnProfile (ByValue)

## OUTPUTS

### Microsoft.Azure.Commands.Cdn.Models.Endpoint.PSEndpoint

## CATATAN

## RELATED LINKS

[New-AzureRmCdnEndpoint](./New-AzureRmCdnEndpoint.md)

[Remove-AzureRmCdnEndpoint](./Remove-AzureRmCdnEndpoint.md)

[Set-AzureRmCdnEndpoint](./Set-AzureRmCdnEndpoint.md)

[Start-AzureRmCdnEndpoint](./Start-AzureRmCdnEndpoint.md)

[Stop-AzureRmCdnEndpoint](./Stop-AzureRmCdnEndpoint.md)


