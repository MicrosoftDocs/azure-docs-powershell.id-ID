---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Security.dll-Help.xml
Module Name: Az.Security
online version: https://docs.microsoft.com/powershell/module/az.security/Get-AzSecuritySolutionsReferenceData
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Security/Security/help/Get-AzSecuritySolutionsReferenceData.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Security/Security/help/Get-AzSecuritySolutionsReferenceData.md
ms.openlocfilehash: 676a944af40d26f6f3bf90e7c2b8a9fe327415c0
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145521163"
---
# Get-AzSecuritySolutionsReferenceData

## SYNOPSIS
Mendapatkan Data Referensi Solusi Keamanan

## SYNTAX

### SubscriptionScope (Default)
```
Get-AzSecuritySolutionsReferenceData [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan Data Referensi Solusi Keamanan

## EXAMPLES

### Contoh 1
```powershell
Get-AzSecuritySolutionsReferenceData
```

```output
Id                   : /subscriptions/67bc604b-54b2-4c78-a7ba-72504920a319/providers/Microsoft.Security/locations/centr
                       alus/securitySolutionsReferenceData/qualys.qualysAgent
Name                 : qualys.qualysAgent
SecurityFamily       : Va
alertVendorName      :
packageInfoUrl       :
productName          :
publisher            :
publisherDisplayName :
template             : qualys/qualysAgent

Id                   : /subscriptions/67bc604b-54b2-4c78-a7ba-72504920a319/providers/Microsoft.Security/locations/centr
                       alus/securitySolutionsReferenceData/microsoft.ApplicationGateway-ARM
Name                 : microsoft.ApplicationGateway-ARM
SecurityFamily       : SaasWaf
alertVendorName      :
packageInfoUrl       :
productName          :
publisher            :
publisherDisplayName :
template             : microsoft/ApplicationGateway-ARM
```

Mendapatkan semua Dapatkan Data Referensi Solusi Keamanan dalam langganan

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
