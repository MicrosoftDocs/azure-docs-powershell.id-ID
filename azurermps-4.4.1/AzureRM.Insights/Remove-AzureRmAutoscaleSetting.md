---
external help file: Microsoft.Azure.Commands.Insights.dll-Help.xml
Module Name: AzureRM.Insights
ms.assetid: 6140E973-D7AB-4A28-A4FA-818E08129372
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Insights/Commands.Insights/help/Remove-AzureRmAutoscaleSetting.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Insights/Commands.Insights/help/Remove-AzureRmAutoscaleSetting.md
ms.openlocfilehash: cd853184e06403f3c0d516ee1b0790c724adacb4
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132421037"
---
# Remove-AzureRmAutoscaleSetting

## SYNOPSIS
Menghapus pengaturan Skala Otomatis.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Remove-AzureRmAutoscaleSetting -ResourceGroup <String> -Name <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzureRmAutoscaleSetting** menghapus pengaturan Skala Otomatis.
Anda harus menentukan nama pengaturan dan nama grup sumber daya yang ditetapkan untuk pengaturan tersebut.

## EXAMPLES

## PARAMETERS

### -Nama
Menentukan nama pengaturan Skala Otomatis untuk dihapus.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroup
Menentukan nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

### Microsoft.Azure.AzureOperationResponse

## CATATAN

## RELATED LINKS

[Add-AzureRmAutoscaleSetting](./Add-AzureRmAutoscaleSetting.md)

[Get-AzureRmAutoscaleSetting](./Get-AzureRmAutoscaleSetting.md)


