---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Monitor.dll-Help.xml
Module Name: Az.Monitor
online version: https://docs.microsoft.com/powershell/module/az.monitor/remove-azdatacollectionrule
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Monitor/Monitor/help/Remove-AzDataCollectionRule.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Monitor/Monitor/help/Remove-AzDataCollectionRule.md
ms.openlocfilehash: 84b1c4b7457f7a6c0800055fb7446ee0bbd15d00
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145527871"
---
# Remove-AzDataCollectionRule

## SYNOPSIS
Menghapus aturan pengumpulan data.

## SYNTAX

### ByName (Default)
```
Remove-AzDataCollectionRule
   -ResourceGroupName <string> 
   -RuleName <string> 
   [-PassThru]
   [-DefaultProfile <IAzureContextContainer>]
   [-WhatIf]
   [-Confirm]
   [<CommonParameters>]
```

### ByInputObject
```
Remove-AzDataCollectionRule
   -InputObject <PSDataCollectionRuleResource>
   [-PassThru]
   [-DefaultProfile <IAzureContextContainer>]
   [-WhatIf]
   [-Confirm]
   [<CommonParameters>]
```

### ByResourceId
```
Remove-AzDataCollectionRule
   -RuleId <string>
   [-PassThru]
   [-DefaultProfile <IAzureContextContainer>]
   [-WhatIf]
   [-Confirm]
   [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzDataCollectionRule** menghapus aturan pengumpulan data.

Aturan Pengumpulan Data (DCR) menentukan data yang masuk ke Azure Monitor dan menentukan lokasi data tersebut harus dikirim atau disimpan. Berikut adalah [artikel gambaran umum DCR](https://docs.microsoft.com/azure/azure-monitor/platform/data-collection-rule-overview) lengkap.

## EXAMPLES

### Contoh 1: Menghapus aturan pengumpulan data dengan parameter nama dan grup sumber daya
```powershell
Remove-AzDataCollectionRule -ResourceGroupName "testgroup" -RuleName "testDcr"             
```

### Contoh 2: Menghapus aturan pengumpulan data dengan nama dan grup sumber daya mengembalikan bool
```powershell
Remove-AzDataCollectionRule -ResourceGroupName "testgroup" -RuleName "testDcr" -PassThru
```

```output
True
```

### Contoh 3: Menghapus aturan pengumpulan data dari InputObject
```powershell
Get-AzDataCollectionRule -ResourceGroupName "testdcr" -RuleName "dcrFromPipe95" | Remove-AzDataCollectionRule
```

### Contoh 4: Menghapus aturan pengumpulan data dari id sumber daya
```powershell
Remove-AzDataCollectionRule -RuleId "/subscriptions/{subId}/resourceGroups/testdcr/providers/Microsoft.Insights/dataCollectionRules/{dcrName}"
```

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

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

### -ResourceGroupName
Nama grup sumber daya

```yaml
Type: System.String
Parameter Sets: ByResourceGroup
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: System.String
Parameter Sets: ByName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RuleName
Nama sumber daya.

```yaml
Type: System.String
Parameter Sets: ByName
Aliases: Name

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RuleId
Pengidentifikasi sumber daya.

```yaml
Type: System.String
Parameter Sets: ByResourceId
Aliases: ResourceId

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Menunjukkan yang akan terjadi jika cmdlet dijalankan. Cmdlet tidak dijalankan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands. Insights. OutputClasses.PSDataCollectionRuleResource

## NOTES

## RELATED LINKS

[Set-AzDataCollectionRule](./Set-AzDataCollectionRule.md)
 [Get-AzDataCollectionRule](./Get-AzDataCollectionRule.md)
 [New-AzDataCollectionRule](./New-AzDataCollectionRule.md)
 [Update-AzDataCollectionRule](./Update-AzDataCollectionRule.md)