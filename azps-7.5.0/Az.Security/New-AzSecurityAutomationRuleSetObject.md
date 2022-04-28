---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Security.dll-Help.xml
Module Name: Az.Security
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Security/Security/help/New-AzSecurityAutomationRuleSetObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Security/Security/help/New-AzSecurityAutomationRuleSetObject.md
ms.openlocfilehash: 778a744a11556bf5b05be8370d272326e255fa99
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144213371"
---
# New-AzSecurityAutomationRuleSetObject

## SYNOPSIS
Membuat objek seperangkat aturan otomatisasi keamanan

## SYNTAX

```
New-AzSecurityAutomationRuleSetObject -Rules <PSSecurityAutomationTriggeringRule[]>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Membuat objek seperangkat aturan otomatisasi keamanan

## EXAMPLES

### Contoh 1
```powershell
PS C:\> New-AzSecurityAutomationRuleSetObject -Rule $rule
```

Membuat objek seperangkat aturan otomatisasi keamanan

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

### -Aturan
Aturan yang dievaluasi setelah penyadapan peristiwa.
Aturan dikonfigurasi dengan membandingkan nilai tertentu dari model peristiwa dengan nilai yang diharapkan.
Perbandingan ini dilakukan dengan menggunakan salah satu set operator yang didukung

```yaml
Type: PSSecurityAutomationTriggeringRule[]
Parameter Sets: (All)
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

### Microsoft.Azure.Commands.Security.Models.Automations.PSSecurityAutomationRuleSet

## NOTES

## RELATED LINKS
