---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Security.dll-Help.xml
Module Name: Az.Security
online version: https://docs.microsoft.com/powershell/module/az.security/Get-AzSecuritySecureScore
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Security/Security/help/Get-AzSecuritySecureScore.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Security/Security/help/Get-AzSecuritySecureScore.md
ms.openlocfilehash: 82f530b72e185bda7c99c16f9a2c4dcc0c02a385
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143274581"
---
# Get-AzSecuritySecureScore

## SYNOPSIS
Mendapatkan skor keamanan yang aman dan hasilnya pada langganan

## SYNTAX

### SubscriptionScope (Default)
```
Get-AzSecuritySecureScore [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### SubscriptionLevelResource
```
Get-AzSecuritySecureScore -Name <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Komplet Get-AzSecuritySecureScore mendapatkan skor keamanan yang aman dan hasilnya pada langganan.

## EXAMPLES

### Contoh 1
```powershell
Get-AzSecuritySecureScore
```

```output
Id : /subscriptions/0b1f6471-1bf0-4dda-aec3-cb9272f09590/providers/Microsoft.Security/secureScores/ascScore
Name : ascScore
Type : Microsoft.Security/secureScores
DisplayName : ASC score
CurrentScore : 18.38
MaxScore : 56
Percentage : 0.3282
Weight : 1161
```

Mendapatkan semua skor keamanan aman dalam langganan

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama sumber daya.

```yaml
Type: String
Parameter Sets: SubscriptionLevelResource
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Security.Models.Assessments.PSSecuritySecureScore

## NOTES

## RELATED LINKS
