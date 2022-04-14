---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Cdn.dll-Help.xml
Module Name: Az.Cdn
ms.assetid: 28DECA86-37A5-48BE-9727-0C1A3B867E9B
online version: https://docs.microsoft.com/powershell/module/az.cdn/get-azcdnprofile
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/Cdn/help/Get-AzCdnProfile.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/Cdn/help/Get-AzCdnProfile.md
ms.openlocfilehash: 361dcc9f2bc22a231b4fcfaa7caf575fcf523767
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142169695"
---
# Get-AzCdnProfile

## SYNOPSIS
Mendapatkan profil CDN.

## SYNTAX

```
Get-AzCdnProfile [-ProfileName <String>] [-ResourceGroupName <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
**Cmdlet Get-AzCdnProfile** mendapatkan profil Azure Content Delivery Network (CDN) dan informasi terkaitnya.

## EXAMPLES

### Contoh 1: Dapatkan semua profil CDN dalam grup sumber daya
```powershell
Get-AzCdnProfile -ResourceGroupName myresourcegroup
```

```Output
Sku               : Microsoft.Azure.Commands.Cdn.Models.Profile.PSSku
ResourceState     : Active
ResourceGroupName : myresourcegroup
Location          : WestUs
Tags              : {}
Id                : /subscriptions/11111111-1111-1111-1111-111111111111/resourcegroups/myresourcegroup/providers/Microsoft.Cdn
                    /profiles/mycdnprofile
Name              : mycdnprofile
Type              : Microsoft.Cdn/profiles
ProvisioningState : Succeeded
```

## PARAMETERS

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

### -ProfileName
Menentukan nama profil.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya tempat profil berada.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Cdn.Models.Profile.PSProfile

## CATATAN

## RELATED LINKS

[New-AzCdnProfile](./New-AzCdnProfile.md)

[Hapus-AzCdnProfile](./Remove-AzCdnProfile.md)

[Set-AzCdnProfile](./Set-AzCdnProfile.md)


