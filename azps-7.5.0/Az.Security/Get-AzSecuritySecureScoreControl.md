---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Security.dll-Help.xml
Module Name: Az.Security
online version: https://docs.microsoft.com/powershell/module/az.security/Get-AzSecuritySecureScoreControl
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Security/Security/help/Get-AzSecuritySecureScoreControl.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Security/Security/help/Get-AzSecuritySecureScoreControl.md
ms.openlocfilehash: ea36ceba1591e726b46e98d3c3382f0db7c4b1f1
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145636298"
---
# Get-AzSecuritySecureScoreControl

## SYNOPSIS
Mendapatkan kontrol skor aman keamanan dan hasilnya pada langganan

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.security/get-azsecuritysecurescorecontrol) untuk informasi terbaru.

## SYNTAX

### SubscriptionScope (Default)
```
Get-AzSecuritySecureScoreControl [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### SubscriptionLevelResource
```
Get-AzSecuritySecureScoreControl -Name <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Komplet Get-AzSecuritySecureScoreControl mendapatkan kontrol skor aman keamanan dan hasilnya pada langganan.

## EXAMPLES

### Contoh 1
```powershell
Get-AzSecuritySecureScoreControl
```

```output
Id : /subscriptions/0b1f6471-1bf0-4dda-aec3-cb9272f09590/providers/Microsoft.Security/secureSco
res/ascScore/secureScoreControls/8fd574ec-43cf-426e-a439-a67cbaf2d564
Name : 8fd574ec-43cf-426e-a439-a67cbaf2d564
Type : Microsoft.Security/secureScores/secureScoreControls
DisplayName : Enable encryption at rest
CurrentScore : 0
MaxScore : 4
Percentage : 0
Weight : 6
HealthyResourceCount : 0
UnhealthyResourceCount : 6
NotApplicableResourceCount : 0
```

Mendapatkan semua skor aman keamanan dalam langganan

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

### -Name
Nama skor aman.

```yaml
Type: System.String
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

### Microsoft.Azure.Commands.Security.Models.Assessments.PSSecuritySecureScoreControl

## NOTES

## RELATED LINKS
