---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Security.dll-Help.xml
Module Name: Az.Security
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Security/Security/help/Set-AzAlertsSuppressionRule.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Security/Security/help/Set-AzAlertsSuppressionRule.md
ms.openlocfilehash: 474d0bbd2e35bb757c2709c76da17c01d9f88bb7
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145540076"
---
# Set-AzAlertsSuppressionRule

## SYNOPSIS
Membuat atau memperbarui aturan supresi pemberitahuan.

## SYNTAX

### RuleNameWithParameters (Default)
```
Set-AzAlertsSuppressionRule -Name <String> -AlertType <String> [-ExpirationDateUtc <DateTime>] -Reason <String>
 -State <PSRuleState> [-Comment <String>] [-SuppressionAlertsScope <PSSuppressionAlertsScope>]
 [-AllOf <PSIScopeElement[]>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### InputObject
```
Set-AzAlertsSuppressionRule -InputObject <PSAlertsSuppressionRule> [-Name <String>] [-AlertType <String>]
 [-ExpirationDateUtc <DateTime>] [-Reason <String>] [-State <PSRuleState>] [-Comment <String>]
 [-SuppressionAlertsScope <PSSuppressionAlertsScope>] [-AllOf <PSIScopeElement[]>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Membuat atau memperbarui aturan supresi pemberitahuan.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Set-AzAlertsSuppressionRule -Name "Example" -State Enabled -Comment "Example of a comment" -AlertType "AzureDNS_CurrencyMining" -Reason "Other" -AllOf @([Microsoft.Azure.Commands.Security.Models.AlertsSuppressionRules.PSScopeElementContains]::new("entities.account.name", "example")) -ExpirationDateUtc 2024-10-17T15:02:24.7511441Z
```

Contoh di atas membuat aturan supresi baru dengan nama "Contoh" untuk menekan pemberitahuan jenis (Aktivitas penambangan mata uang digital)[https://docs.microsoft.com/en-us/azure/defender-for-cloud/alerts-reference] yang berisi "contoh" sebagai bagian dari nama akun mereka.

## PARAMETERS

### -AlertType
Jenis pemberitahuan untuk ditekan.

```yaml
Type: System.String
Parameter Sets: RuleNameWithParameters
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: System.String
Parameter Sets: InputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllOf
Cakupan aturan supresi menggunakan entitas tertentu.

```yaml
Type: Microsoft.Azure.Commands.Security.Models.AlertsSuppressionRules.PSIScopeElement[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Komentar
Komentar.

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

### -ExpirationDateUtc
Atur data kedaluwarsa untuk aturan, yang diharapkan dalam format UTC.

```yaml
Type: System.Nullable`1[System.DateTime]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Objek Input.

```yaml
Type: Microsoft.Azure.Commands.Security.Models.AlertsSuppressionRules.PSAlertsSuppressionRule
Parameter Sets: InputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Nama aturan supresi pemberitahuan, harus unik per langganan.

```yaml
Type: System.String
Parameter Sets: RuleNameWithParameters
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: System.String
Parameter Sets: InputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Alasan
Alasan untuk membuat aturan supresi.

```yaml
Type: System.String
Parameter Sets: RuleNameWithParameters
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: System.String
Parameter Sets: InputObject
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -State
Status aturan, Diaktifkan/Dinonaktifkan

```yaml
Type: Microsoft.Azure.Commands.Security.Models.AlertsSuppressionRules.PSRuleState
Parameter Sets: RuleNameWithParameters
Aliases:
Accepted values: Enabled, Disabled, Expired

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: Microsoft.Azure.Commands.Security.Models.AlertsSuppressionRules.PSRuleState
Parameter Sets: InputObject
Aliases:
Accepted values: Enabled, Disabled, Expired

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SuppressionAlertsScope
Cakupan aturan supresi menggunakan entitas tertentu.

```yaml
Type: Microsoft.Azure.Commands.Security.Models.AlertsSuppressionRules.PSSuppressionAlertsScope
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
Cmdlet tidak dijalankan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.Commands.Security.Models.AlertsSuppressionRules.PSAlertsSuppressionRule

## OUTPUTS

### Microsoft.Azure.Commands.Security.Models.AlertsSuppressionRules.PSAlertsSuppressionRule

## NOTES

## RELATED LINKS
