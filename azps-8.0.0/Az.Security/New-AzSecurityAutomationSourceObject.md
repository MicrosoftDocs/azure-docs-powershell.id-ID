---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Security.dll-Help.xml
Module Name: Az.Security
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Security/Security/help/New-AzSecurityAutomationSourceObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Security/Security/help/New-AzSecurityAutomationSourceObject.md
ms.openlocfilehash: f15a3b4a7bc7a3df7c594f9f3b5b0e9878ab1ed3
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145500857"
---
# New-AzSecurityAutomationSourceObject

## SYNOPSIS
Membuat objek sumber otomatisasi keamanan

## SYNTAX

### SecurityAutomationSource (Default)
```
New-AzSecurityAutomationSourceObject [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### SecurityAutomationActionLogicApp
```
New-AzSecurityAutomationSourceObject -EventSource <String> -RuleSets <PSSecurityAutomationRuleSet[]>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Membuat objek sumber otomatisasi keamanan

## EXAMPLES

### Contoh 1
```powershell
PS C:\> New-AzSecurityAutomationSourceObject -EventSource 'Assessments' -RuleSet $ruleSet
```

Membuat objek sumber otomatisasi keamanan

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

### -EventSource
ID Sumber Daya Azure Logic App yang dipicu.
Ini juga dapat berada di langganan lain, mengingat Anda memiliki izin untuk memicu Aplikasi Logika

```yaml
Type: String
Parameter Sets: SecurityAutomationActionLogicApp
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RuleSets
Titik akhir URI pemicu Aplikasi Logika (tidak akan disertakan dalam respons apa pun)

```yaml
Type: PSSecurityAutomationRuleSet[]
Parameter Sets: SecurityAutomationActionLogicApp
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

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.Security.Models.Automations.PSSecurityAutomationSource

## NOTES

## RELATED LINKS
