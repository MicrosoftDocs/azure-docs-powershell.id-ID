---
external help file: Microsoft.Azure.Commands.RecoveryServices.SiteRecovery.dll-Help.xml
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/RecoveryServices.SiteRecovery/Commands.RecoveryServices.SiteRecovery/help/Get-AzureRmRecoveryServicesAsrPolicy.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/RecoveryServices.SiteRecovery/Commands.RecoveryServices.SiteRecovery/help/Get-AzureRmRecoveryServicesAsrPolicy.md
ms.openlocfilehash: 7ac4db45f9eb0332217c5097802904cd2146aca5
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132425635"
---
# Get-AzureRmRecoveryServicesAsrPolicy

## SYNOPSIS
Mendapatkan kebijakan replikasi ASR.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### Default (Default)
```
Get-AzureRmRecoveryServicesAsrPolicy [<CommonParameters>]
```

### ByName
```
Get-AzureRmRecoveryServicesAsrPolicy -Name <String> [<CommonParameters>]
```

### ByFriendlyName
```
Get-AzureRmRecoveryServicesAsrPolicy -FriendlyName <String> [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmRecoveryServicesAsrPolicy** mendapatkan daftar kebijakan replikasi Pemulihan Situs Azure yang dikonfigurasi atau kebijakan replikasi tertentu menurut nama.

## EXAMPLES

### Contoh 1
```
PS C:\> $Policy = Get-AzureRmRecoveryServicesAsrPolicy -Name $PolicyName
```

Ret menjalankan kebijakan replikasi dengan nama yang ditentukan.

## PARAMETERS

### -FriendlyName
Menentukan nama yang mudah dikenal dari kebijakan replikasi ASR.

```yaml
Type: String
Parameter Sets: ByFriendlyName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Menentukan nama kebijakan replikasi ASR.

```yaml
Type: String
Parameter Sets: ByName
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

### Tidak ada

## OUTPUTS

### System.Collections.Generic.IEnumerable'1[[Microsoft.Azure.Commands.RecoveryServices.SiteRecovery.ASRPolicy, Microsoft.Azure.Commands.RecoveryServices.SiteRecovery, Version=4.0.0.0, Culture=neutral, PublicKeyToken=null]]

## CATATAN

## RELATED LINKS

[New-AzureRmRecoveryServicesAsrPolicy](./New-AzureRmRecoveryServicesAsrPolicy.md)

[Remove-AzureRmRecoveryServicesAsrPolicy](./Remove-AzureRmRecoveryServicesAsrPolicy.md)
