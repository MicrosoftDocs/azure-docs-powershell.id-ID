---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Cdn.dll-Help.xml
Module Name: Az.Cdn
online version: https://docs.microsoft.com/powershell/module/az.cdn/get-azcdnsubscriptionresourceusage
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/Cdn/help/Get-AzCdnSubscriptionResourceUsage.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/Cdn/help/Get-AzCdnSubscriptionResourceUsage.md
ms.openlocfilehash: 1e353154b73686c426470f367257a1496fe1b6b5
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143368451"
---
# Get-AzCdnSubscriptionResourceUsage

## SYNOPSIS
Mendapatkan penggunaan sumber daya untuk langganan.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.cdn/get-azcdnsubscriptionresourceusage) untuk informasi terbaru.

## SYNTAX

```
Get-AzCdnSubscriptionResourceUsage [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
**Cmdlet Get-AzCdnSubscriptionResourceUsage** mendapatkan penggunaan sumber daya untuk langganan.

## EXAMPLES

### Contoh 1
```powershell
Get-AzCdnSubscriptionResourceUsage
```

```Output
ResourceType Unit  CurrentValue Limit
------------ ----  ------------ -----
profile      count            0    25
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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### Microsoft.Azure.Commands.Cdn.Models.PSResourceUsage

## NOTES

## RELATED LINKS
