---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Security.dll-Help.xml
Module Name: Az.Security
online version: https://docs.microsoft.com/powershell/module/az.security/Get-AzSecuritySolutionsReferenceData
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Security/Security/help/Get-AzSecuritySolution.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Security/Security/help/Get-AzSecuritySolution.md
ms.openlocfilehash: db59b6e386dce4bbd38e3badcaab7575fa7b262a
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145520179"
---
# Get-AzSecuritySolution

## SYNOPSIS
Dapatkan Solusi Keamanan

## SYNTAX

### SubscriptionScope (Default)
```
Get-AzSecuritySolution [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Dapatkan Solusi Keamanan

## EXAMPLES

### Contoh 1
```powershell
Get-AzSecuritySolution
```

```output
Id                : /subscriptions/67bc604b-54b2-4c78-a7ba-72504920a319/resourceGroups/QualysLICTest/providers/Microsoft.Security/locations/centralus/securitySolutions/QualysTest
Name              : QualysLICTest
provisioningState : Succeeded
template          : qualys.qualysAgent
SecurityFamily    : Va
protectionStatus  : Good

Id                : /subscriptions/67bc604b-54b2-4c78-a7ba-72504920a319/resourceGroups/OfriWafTest/providers/MicrosoftSecurity/locations/centralus/securitySolutions/WafTest
Name              : WafTest
provisioningState : Succeeded
template          : Microsoft.ApplicationGateway-ARM
SecurityFamily    : SaasWaf
protectionStatus  : Good
```

Mendapatkan semua Dapatkan Solusi Keamanan dalam langganan

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

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Security.Models.ExternalSecuritySolutions.PSSecurityExternalSecuritySolution

## NOTES

## RELATED LINKS