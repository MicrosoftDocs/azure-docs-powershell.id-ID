---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Security.dll-Help.xml
Module Name: Az.Security
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Security/Security/help/New-AzAlertsSuppressionRuleScope.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Security/Security/help/New-AzAlertsSuppressionRuleScope.md
ms.openlocfilehash: 1a851ac7edc29201db8d91e3c1ae34e8b22ec91c
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145561997"
---
# New-AzAlertsSuppressionRuleScope

## SYNOPSIS
Cmdlet pembantu untuk membuat PSIScopeElement.

## SYNTAX

```
New-AzAlertsSuppressionRuleScope -Field <String> [-ContainsSubstring <String>] [-AnyOf <String[]>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet pembantu untuk membuat PSIScopeElement.
Dapat digunakan dalam Set-AzAlertsSuppressionRule sebagai bagian dari parameter -AllOf.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> $scope1 = New-AzAlertsSuppressionRuleScope -Field "entities.account.name" -Contains "Example"
```

Membuat PSScopeElementContains.

### Contoh 2
```powershell
PS C:\> $scope2 = New-AzAlertsSuppressionRuleScope -Field "entities.file.name" -In "FileName1","FileName2","FileName3"
```

Membuat PSScopeElementIn.

## PARAMETERS

### -AnyOf
Sembunyikan hanya ketika bidang sama dengan salah satu nilai tersebut.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ContainsSubstring
Sembunyikan hanya ketika bidang berisi nilai spesifik ini.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -Bidang
Bidang entitas untuk dilingkup oleh.

```yaml
Type: System.String
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

### Microsoft.Azure.Commands.Security.Models.AlertsSuppressionRules.PSIScopeElement

## NOTES

## RELATED LINKS
