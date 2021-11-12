---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/en-us/powershell/module/az.network/get-azapplicationgatewayavailablewafruleset
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Network/Network/help/Get-AzApplicationGatewayAvailableWafRuleSet.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Network/Network/help/Get-AzApplicationGatewayAvailableWafRuleSet.md
ms.openlocfilehash: 7cb3f6d015f95ba6a72066714647eb7a0551398b
ms.sourcegitcommit: b4a38bcb0501a9016a4998efd377aa75d3ef9ce8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/27/2020
ms.locfileid: "132408913"
---
# Get-AzApplicationGatewayAvailableWafRuleSet

## SYNOPSIS
Mendapatkan semua kumpulan aturan firewall aplikasi web yang tersedia.

## SINTAKS

```
Get-AzApplicationGatewayAvailableWafRuleSet [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESKRIPSI
Cmdlet **Get-AzApplicationGatewayAvailableWafRuleSet** mendapatkan semua kumpulan aturan firewall aplikasi web yang tersedia.

## CONTOH

### Contoh 1
```
PS C:\>$availableRuleSets = Get-AzApplicationGatewayAvailableWafRuleSet
```

Perintah ini mengembalikan semua kumpulan aturan firewall aplikasi web yang tersedia.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUT

### Tidak ada

## OUTPUT

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayAvailableWafRuleSetsResult

## CATATAN
**List-AzApplicationGatewayAvailableWafRuleSets** merupakan alias untuk cmdlet **Get-AzApplicationGatewayAvailableWafRuleSet.**

## LINK TERKAIT
