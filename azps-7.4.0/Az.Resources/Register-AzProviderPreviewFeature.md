---
external help file: Microsoft.Azure.PowerShell.Cmdlets.ResourceManager.dll-Help.xml
Module Name: Az.Resources
online version: https://docs.microsoft.com/powershell/module/az.resources/register-azproviderpreviewfeature
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Register-AzProviderPreviewFeature.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Resources/Resources/help/Register-AzProviderPreviewFeature.md
ms.openlocfilehash: 1aefb745bd7f39af4b349792d3125add9688e850
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144608198"
---
# Register-AzProviderPreviewFeature

## SYNOPSIS
Membuat pendaftaran fitur di akun Anda.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.resources/register-azproviderpreviewfeature) untuk informasi terbaru.

## SYNTAX

```
Register-AzProviderPreviewFeature -Name <String> -ProviderNamespace <String>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Register-AzProviderPreviewFeature** membuat pendaftaran fitur di akun Anda.

## EXAMPLES

### Contoh 1: Membuat pendaftaran fitur
```powershell
Register-AzProviderPreviewFeature -FeatureName AllowApplicationSecurityGroups -ProviderNamespace Microsoft.Network
```

Ini menambahkan fitur AllowApplicationSecurityGroups untuk Microsoft.Network ke akun Anda.

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

### -Name
Nama fitur.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: FeatureName

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ProviderNamespace
Namespace layanan penyedia sumber daya.

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

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
Cmdlet tidak dijalankan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Management.ResourceManager.Models.SubscriptionFeatureRegistration

## NOTES

## RELATED LINKS

[Get-AzProviderPreviewFeature](./Get-AzProviderPreviewFeature.md)

[Batalkan pendaftaran-AzProviderPreviewFeature](./Unregister-AzProviderPreviewFeature.md)
