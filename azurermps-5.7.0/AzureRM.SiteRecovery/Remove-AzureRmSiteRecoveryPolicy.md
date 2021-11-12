---
external help file: Microsoft.Azure.Commands.SiteRecovery.dll-Help.xml
Module Name: AzureRM
ms.assetid: C4C624DB-BBE8-4F94-BDC6-C012482F7271
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.siterecovery/remove-azurermsiterecoverypolicy
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/SiteRecovery/Commands.SiteRecovery/help/Remove-AzureRmSiteRecoveryPolicy.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/SiteRecovery/Commands.SiteRecovery/help/Remove-AzureRmSiteRecoveryPolicy.md
ms.openlocfilehash: f09ca4bb6c033b954542d6c734b27bf5f2236d87
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132421350"
---
# Remove-AzureRmSiteRecoveryPolicy

## SYNOPSIS
Menghapus kebijakan replikasi Pemulihan Situs.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Remove-AzureRmSiteRecoveryPolicy -Policy <ASRPolicy> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzureRMSiteRecoveryPolicy** menghapus kebijakan replikasi Pemulihan Situs Azure.

## EXAMPLES

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

### -Kebijakan
Menentukan objek kebijakan Pemulihan Situs.

```yaml
Type: ASRPolicy
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### ASRPolicy
Parameter 'Policy' menerima nilai tipe 'ASRPolicy' dari saluran

## OUTPUTS

## CATATAN

## RELATED LINKS

[Get-AzureRmSiteRecoveryPolicy](./Get-AzureRmSiteRecoveryPolicy.md)

[New-AzureRmSiteRecoveryPolicy](./New-AzureRmSiteRecoveryPolicy.md)
