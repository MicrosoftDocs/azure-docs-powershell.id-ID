---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Security.dll-Help.xml
Module Name: Az.Security
online version: https://docs.microsoft.com/powershell/module/az.security/Get-AzSecuritySecureScoreControlDefinition
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Security/Security/help/Get-AzSecuritySecureScoreControlDefinition.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Security/Security/help/Get-AzSecuritySecureScoreControlDefinition.md
ms.openlocfilehash: 7916739a25fe6ede1cd63721eeddf547d4f4585a
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142174804"
---
# Get-AzSecuritySecureScoreControlDefinition

## SYNOPSIS
Mendapatkan definisi kontrol skor aman keamanan pada langganan

## SYNTAX

### SubscriptionScope (Default)
```
Get-AzSecuritySecureScoreControlDefinition [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### SubscriptionLevelResource
```
Get-AzSecuritySecureScoreControlDefinition -Name <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Komplet Get-AzSecuritySecureScoreControlDefinition mendapatkan definisi kontrol skor aman keamanan pada langganan.

## EXAMPLES

### Contoh 1
```powershell
Get-AzSecuritySecureScoreControlDefinition
```

```output
Id                    : /providers/Microsoft.Security/secureScoreControlDefinitions/a9909064-42b4-4d34-8143-275477afe18b
Name                  : a9909064-42b4-4d34-8143-275477afe18b
Type                  : Microsoft.Security/secureScoreControlDefinitions
DisplayName           : Protect your applications with Azure advanced networking solutions
Description           : 
MaxScore              : 2
Source                : BuiltIn
AssessmentDefinitions : {/providers/Microsoft.Security/assessmentMetadata/e3de1cc0-f4dd-3b34-e496-8b5381ba2d70, /providers/Microsoft.Security/assessmentMetadata/08e628db-e2ed-4793-bc91-d13e6
                        84401c3, /providers/Microsoft.Security/assessmentMetadata/0642d770-b189-42ef-a2ce-9dcc3ec6c169, /providers/Microsoft.Security/assessmentMetadata/405c9ae6-49f9-46c4-88
                        73-a86690f27818...}
```

Mendapatkan semua definisi kontrol skor aman keamanan dalam langganan

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Security.Models.Assessments.PSSecuritySecureScoreControlDefinition

## CATATAN

## RELATED LINKS
