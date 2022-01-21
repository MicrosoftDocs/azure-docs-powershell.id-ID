---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ResourceManager.dll-Help.xml
Module Name: Az.Resources
online version: https://docs.microsoft.com/powershell/module/az.resources/get-azproviderpreviewfeature
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzProviderPreviewFeature.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Get-AzProviderPreviewFeature.md
ms.openlocfilehash: 6a7a191635b05c8feb7f68bf1b69f15d4dd36b2c
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136540076"
---
# Get-AzProviderPreviewFeature

## SYNOPSIS
Dapatkan pendaftaran fitur di akun Anda.

## SYNTAX

```
Get-AzProviderPreviewFeature [-Name <String>] -ProviderNamespace <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzProviderPreviewFeature** mendapatkan pendaftaran fitur di akun Anda.

## EXAMPLES

### Contoh 1
```powershell
PS C:\>Get-AzProviderPreviewFeature -FeatureName AllowApplicationSecurityGroups -ProviderNamespace Microsoft.Network
```

Hal ini akan mendapatkan fitur AllowApplicationSecurityGroups untuk Microsoft.Network dalam akun Anda.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

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

### -Nama
Nama fitur.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: FeatureName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ProviderNamespace
Ruang nama penyedia sumber daya.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Management.ResourceManager.Models.PSSubscriptionFeatureRegistration

## CATATAN

## RELATED LINKS

[Register-AzProviderPreviewFeature](./Register-AzProviderPreviewFeature.md)

[Unregister-AzProviderPreviewFeature](./Unregister-AzProviderPreviewFeature.md)
