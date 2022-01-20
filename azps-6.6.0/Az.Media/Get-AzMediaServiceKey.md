---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Media.dll-Help.xml
Module Name: Az.Media
ms.assetid: 2099938F-5325-416C-AE10-6813546A1055
online version: https://docs.microsoft.com/powershell/module/az.media/get-azmediaservicekey
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Media/Media/help/Get-AzMediaServiceKey.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Media/Media/help/Get-AzMediaServiceKey.md
ms.openlocfilehash: 1e92ffa4015256f4af26189b4192bca289596541
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136367623"
---
# Get-AzMediaServiceKey

## SYNOPSIS
Mendapatkan informasi penting untuk mengakses titik akhir REST yang terkait dengan layanan media.

## SYNTAX

```
Get-AzMediaServiceKey [-ResourceGroupName] <String> [-AccountName] <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzMediaServiceKey** mendapatkan informasi kunci untuk mengakses titik akhir Representational State Transfer (REST) yang terkait dengan layanan media Azure.

## EXAMPLES

### Contoh 1: Dapatkan informasi penting untuk mengakses layanan media
```
PS C:\>Get-AzMediaServiceKey -ResourceGroupName "ResourceGroup001" -AccountName "MediaService001"
```

Perintah ini mendapatkan informasi utama untuk mengakses layanan media bernama MediaService001 yang dimiliki oleh grup sumber daya bernama ResourceGroup001.

## PARAMETERS

### -Nama Akun
Menentukan nama layanan media yang mendapatkan kunci layanan media dari cmdlet ini.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Name, ResourceName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Media.Models.PSServiceKeys

## CATATAN

## RELATED LINKS

[Set-AzMediaServiceKey](./Set-AzMediaServiceKey.md)


