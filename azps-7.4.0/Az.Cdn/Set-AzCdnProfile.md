---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Cdn.dll-Help.xml
Module Name: Az.Cdn
ms.assetid: 863DD160-4443-4D50-804E-089255F3EA4E
online version: https://docs.microsoft.com/powershell/module/az.cdn/set-azcdnprofile
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/Cdn/help/Set-AzCdnProfile.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/Cdn/help/Set-AzCdnProfile.md
ms.openlocfilehash: 5d5aac28c7ed77fbf15665d7050c5998acf4310a
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144581574"
---
# Set-AzCdnProfile

## SYNOPSIS
Memperbarui profil CDN.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.cdn/set-azcdnprofile) untuk informasi terbaru.

## SYNTAX

```
Set-AzCdnProfile -CdnProfile <PSProfile> [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
**Cmdlet Set-AzCdnProfile** memperbarui profil Azure Content Delivery Network (CDN).

## EXAMPLES

### Contoh 1
```powershell
$profileObject = Get-AzCdnProfile -ResourceGroupName myresourcegroup -ProfileName mycdnprofile
$profileObject.Tags = @{"key"="value"}
Set-AzCdnProfile -CdnProfile $profileObject
```

```Output
Sku               : Microsoft.Azure.Commands.Cdn.Models.Profile.PSSku
ResourceState     : Active
ResourceGroupName : myresourcegroup
Location          : WestUs
Tags              : {key}
Id                : /subscriptions/11111111-1111-1111-1111-111111111111/resourcegroups/myresourcegroup/providers/Microsoft.Cdn
                    /profiles/mycdnprofile
Name              : mycdnprofile
Type              : Microsoft.Cdn/profiles
ProvisioningState : Succeeded
```

## PARAMETERS

### -CdnProfile
Menentukan profil yang diperbarui cmdlet ini.

```yaml
Type: Microsoft.Azure.Commands.Cdn.Models.Profile.PSProfile
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
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
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.Commands.Cdn.Models.Profile.PSProfile

## OUTPUTS

### Microsoft.Azure.Commands.Cdn.Models.Profile.PSProfile

## NOTES

## RELATED LINKS

[Get-AzCdnProfile](./Get-AzCdnProfile.md)

[New-AzCdnProfile](./New-AzCdnProfile.md)

[Remove-AzCdnProfile](./Remove-AzCdnProfile.md)


