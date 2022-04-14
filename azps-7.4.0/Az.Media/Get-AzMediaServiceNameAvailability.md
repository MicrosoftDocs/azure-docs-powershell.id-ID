---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Media.dll-Help.xml
Module Name: Az.Media
ms.assetid: 23C6C9D3-A745-46C8-AB2C-B874223FBFFF
online version: https://docs.microsoft.com/powershell/module/az.media/get-azmediaservicenameavailability
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Media/Media/help/Get-AzMediaServiceNameAvailability.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Media/Media/help/Get-AzMediaServiceNameAvailability.md
ms.openlocfilehash: 1689340fbfba9af6a8ce86aa887c814173c771e7
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142177484"
---
# Get-AzMediaServiceNameAvailability

## SYNOPSIS
Memeriksa apakah nama layanan media tersedia.
Nama layanan media unik secara global.

## SYNTAX

```
Get-AzMediaServiceNameAvailability [-DefaultProfile <IAzureContextContainer>] [-AccountName] <String>
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzMediaServiceNameAvailability** memeriksa apakah nama layanan media tersedia.
Nama layanan media unik secara global.

## EXAMPLES

### Contoh 1: Periksa apakah nama Layanan Media tersedia
```powershell
Get-AzMediaServiceNameAvailability -AccountName "MediaService1"
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
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### Microsoft.Azure.Commands.Media.Models.PSCheckNameAvailabilityOutput

## CATATAN

## RELATED LINKS

[Get-AzMediaService](./Get-AzMediaService.md)

[New-AzMediaService](./New-AzMediaService.md)

[Hapus-AzMediaService](./Remove-AzMediaService.md)

[Set-AzMediaService](./Set-AzMediaService.md)


