---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Security.dll-Help.xml
Module Name: Az.Security
online version: https://docs.microsoft.com/powershell/module/az.security/Get-AzSecuritySecureScore
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Security/Security/help/Get-AzSecuritySecureScore.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Security/Security/help/Get-AzSecuritySecureScore.md
ms.openlocfilehash: 207d4c0839372f420e499b34413002869fb6cf57
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144734068"
---
# Get-AzSecuritySecureScore

## SYNOPSIS
Mendapatkan skor aman keamanan dan hasilnya pada langganan

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.security/get-azsecuritysecurescore) untuk informasi terbaru.

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
Komplet Get-AzSecuritySecureScore mendapatkan skor aman keamanan dan hasilnya pada langganan.

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

Mendapatkan semua skor aman keamanan dalam langganan

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

### -Name
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Security.Models.Assessments.PSSecuritySecureScore

## NOTES

## RELATED LINKS
