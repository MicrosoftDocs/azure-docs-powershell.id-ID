---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Media.dll-Help.xml
Module Name: Az.Media
ms.assetid: 9843D191-CBC4-481A-BD36-D7B2D7917BD9
online version: https://docs.microsoft.com/powershell/module/az.media/get-azmediaservice
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Media/Media/help/Get-AzMediaService.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Media/Media/help/Get-AzMediaService.md
ms.openlocfilehash: 01db151a1b6960ab9ea206e5b3d76f390e7bdd52
ms.sourcegitcommit: 321c644cf2161807a71e1af318fc5c5311d22e25
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/25/2022
ms.locfileid: "145792000"
---
# Get-AzMediaService

## SYNOPSIS
Mendapatkan informasi tentang layanan media.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.media/get-azmediaservice) untuk informasi terbaru.

## SYNTAX

### ResourceGroupParameterSet
```
Get-AzMediaService [-ResourceGroupName] <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### AccountNameParameterSet
```
Get-AzMediaService [-ResourceGroupName] <String> [-AccountName] <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzMediaService** mendapatkan informasi tentang layanan media.

## EXAMPLES

### Contoh 1: Mendapatkan semua layanan media dalam grup sumber daya
```powershell
Get-AzMediaService -ResourceGroupName "ResourceGroup001"
```

Perintah ini mendapatkan properti untuk semua layanan media dalam grup sumber daya bernama ResourceGroup001.

### Contoh 2: Mendapatkan properti layanan media
```powershell
Get-AzMediaService -ResourceGroupName "ResourceGroup002" -AccountName "MediaService1"
```

Perintah ini mendapatkan properti layanan media bernama MediaService1 yang termasuk dalam grup sumber daya bernama ResourceGroup002.

## PARAMETERS

### -AccountName
Menentukan nama layanan media yang didapat cmdlet ini.

```yaml
Type: System.String
Parameter Sets: AccountNameParameterSet
Aliases: Name, ResourceName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -ResourceGroupName
Menentukan nama grup sumber daya yang berisi layanan media.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Media.Models.PSMediaService

## NOTES

## RELATED LINKS

[New-AzMediaService](./New-AzMediaService.md)

[Remove-AzMediaService](./Remove-AzMediaService.md)

[Set-AzMediaService](./Set-AzMediaService.md)


