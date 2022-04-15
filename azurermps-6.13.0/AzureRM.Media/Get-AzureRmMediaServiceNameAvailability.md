---
external help file: Microsoft.Azure.Commands.Media.dll-Help.xml
Module Name: AzureRM.Media
ms.assetid: 23C6C9D3-A745-46C8-AB2C-B874223FBFFF
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.media/get-azurermmediaservicenameavailability
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Media/Commands.Media/help/Get-AzureRmMediaServiceNameAvailability.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Media/Commands.Media/help/Get-AzureRmMediaServiceNameAvailability.md
ms.openlocfilehash: 8de8b9f389f8d57d844c17d92dd492390fbf1884
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142139712"
---
# Get-AzureRmMediaServiceNameAvailability

## SYNOPSIS
Memeriksa apakah nama layanan media tersedia.
Nama layanan media unik secara global.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Get-AzureRmMediaServiceNameAvailability [-DefaultProfile <IAzureContextContainer>] [-AccountName] <String>
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmMediaServiceNameAvailability** memeriksa apakah nama layanan media tersedia.
Nama layanan media unik secara global.

## EXAMPLES

### Contoh 1: Periksa apakah nama Layanan Media tersedia
```
PS C:\>Get-AzureRmMediaServiceNameAvailability -AccountName "MediaService1"
```

Perintah ini memeriksa apakah nama MediaService1 tersedia.

## PARAMETERS

### -AccountName
Menentukan nama layanan media yang didapat cmdlet ini.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Name, ResourceName

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### Microsoft.Azure.Commands.Media.Models.PSCheckNameAvailabilityOutput

## CATATAN

## RELATED LINKS

[Get-AzureRmMediaService](./Get-AzureRmMediaService.md)

[Baru-AzureRmMediaService](./New-AzureRmMediaService.md)

[Hapus-AzureRmMediaService](./Remove-AzureRmMediaService.md)

[Set-AzureRmMediaService](./Set-AzureRmMediaService.md)


