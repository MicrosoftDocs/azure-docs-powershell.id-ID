---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Cdn.dll-Help.xml
Module Name: Az.Cdn
online version: https://docs.microsoft.com/powershell/module/az.cdn/get-azcdnsubscriptionresourceusage
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/Cdn/help/Get-AzCdnSubscriptionResourceUsage.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/Cdn/help/Get-AzCdnSubscriptionResourceUsage.md
ms.openlocfilehash: 99ea51cec7dc1f2caf0e983f5220b78f095d470b
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144225914"
---
# Get-AzCdnSubscriptionResourceUsage

## SYNOPSIS
Mendapatkan penggunaan sumber daya untuk langganan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.Cdn.Models.PSResourceUsage

## NOTES

## RELATED LINKS
