---
external help file: Microsoft.Azure.Commands.Cdn.dll-Help.xml
Module Name: AzureRM.Cdn
ms.assetid: 6477ADC3-0831-493D-8904-F1D787145DD3
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.cdn/start-azurermcdnendpoint
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Cdn/Commands.Cdn/help/Start-AzureRmCdnEndpoint.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Cdn/Commands.Cdn/help/Start-AzureRmCdnEndpoint.md
ms.openlocfilehash: cfa0eb8506230fe14b9ddf48bcd7562acf45a590
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132420845"
---
# Start-AzureRmCdnEndpoint

## SYNOPSIS
Memulai titik CDN akhir.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### ByFieldsParameterSet (Default)
```
Start-AzureRmCdnEndpoint -EndpointName <String> -ProfileName <String> -ResourceGroupName <String> [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByObjectParameterSet
```
Start-AzureRmCdnEndpoint -CdnEndpoint <PSEndpoint> [-PassThru] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Start-AzureRmCdnEndpoint** memulai titik akhir Azure Content Delivery Network (CDN).

## EXAMPLES

## PARAMETERS

### -CdnEndpoint
Menentukan titik akhir yang dimulai cmdlet ini.

```yaml
Type: PSEndpoint
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
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EndpointName
Menentukan nama titik akhir yang dimulai cmdlet ini.

```yaml
Type: String
Parameter Sets: ByFieldsParameterSet
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Mengembalikan objek yang mewakili item yang Anda kerjakan.
Secara default, cmdlet ini tidak menghasilkan output apa pun.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ProfileName
Menentukan nama profil tempat titik akhir tersebut berada.

```yaml
Type: String
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
Type: String
Parameter Sets: ByFieldsParameterSet
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak berjalan.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### PSEndpoint
Parameter 'CdnEndpoint' menerima nilai tipe 'PSEndpoint' dari saluran

## OUTPUTS

### System.Boolean

## CATATAN

## RELATED LINKS

[Get-AzureRmCdnEndpoint](./Get-AzureRmCdnEndpoint.md)

[New-AzureRmCdnEndpoint](./New-AzureRmCdnEndpoint.md)

[Remove-AzureRmCdnEndpoint](./Remove-AzureRmCdnEndpoint.md)

[Set-AzureRmCdnEndpoint](./Set-AzureRmCdnEndpoint.md)

[Stop-AzureRmCdnEndpoint](./Stop-AzureRmCdnEndpoint.md)


