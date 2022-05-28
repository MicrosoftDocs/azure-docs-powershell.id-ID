---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Security.dll-Help.xml
Module Name: Az.Security
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Security/Security/help/New-AzSecurityAutomationSourceObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Security/Security/help/New-AzSecurityAutomationSourceObject.md
ms.openlocfilehash: 7f4584ab0ed1e36772b79302db1f9fdcd5e1b90e
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145635488"
---
# New-AzSecurityAutomationSourceObject

## SYNOPSIS
Membuat objek sumber otomatisasi keamanan

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.security/new-azsecurityautomationsourceobject) untuk informasi terbaru.

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
