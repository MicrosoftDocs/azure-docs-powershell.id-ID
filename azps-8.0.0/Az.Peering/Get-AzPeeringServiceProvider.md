---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Peering.dll-Help.xml
Module Name: Az.Peering
online version: https://docs.microsoft.com/powershell/module/az.peering/get-azpeeringserviceprovider
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Peering/Peering/help/Get-AzPeeringServiceProvider.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Peering/Peering/help/Get-AzPeeringServiceProvider.md
ms.openlocfilehash: f5b988bf99a038ac4933d0d9c7028403b315f78b
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145507150"
---
# Get-AzPeeringServiceProvider

## SYNOPSIS
Mendapatkan daftar penyedia layanan peering yang bermitra dengan Microsoft.

## SYNTAX

```
Get-AzPeeringServiceProvider [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Mencantumkan penyedia layanan peering

## EXAMPLES

### Contoh 1
```powershell
Get-AzPeeringServiceProvider
```

```output
ServiceProviderName Name      Id Type
------------------- ----      -- ----
TestPeer1           TestPeer1    Microsoft.Peering/peeringServiceProviders
```

Mendapatkan penyedia layanan peering yang tersedia

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Peering.Models.PSPeeringServiceProvider

## NOTES

## RELATED LINKS
