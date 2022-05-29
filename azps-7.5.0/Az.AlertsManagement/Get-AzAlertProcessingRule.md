---
external help file: Microsoft.Azure.PowerShell.Cmdlets.AlertsManagement.dll-Help.xml
Module Name: Az.AlertsManagement
online version: https://docs.microsoft.com/powershell/module/az.alertsmanagement/get-azactionrule
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/AlertsManagement/AlertsManagement/help/Get-AzAlertProcessingRule.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/AlertsManagement/AlertsManagement/help/Get-AzAlertProcessingRule.md
ms.openlocfilehash: e76cc78b3239f95b09f5113b83b6a3850d87a061
ms.sourcegitcommit: 321c644cf2161807a71e1af318fc5c5311d22e25
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/25/2022
ms.locfileid: "145782532"
---
# Get-AzAlertProcessingRule

## SYNOPSIS
Mendapatkan Informasi Aturan AlertProcessing

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.alertsmanagement/get-azalertprocessingrule) untuk informasi terbaru.

## SYNTAX

### ListAlertProcessingRules (Default)
```
Get-AzAlertProcessingRule [-Name <String>] [-ResourceGroupName <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ResourceId
```
Get-AzActionRule -ResourceId <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ListAlertProcessingRulesByResourceGroupName
```
Get-AzAlertProcessingRule -ResourceGroupName <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### AlertProcessingRuleByName
```
Get-AzAlertProcessingRule -Name <String> -ResourceGroupName <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzAlertProcessingRule** mendapatkan aturan pemrosesan pemberitahuan yang dikonfigurasi.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Get-AzAlertProcessingRule
```

Mencantumkan semua aturan pemrosesan pemberitahuan yang dikonfigurasi dalam langganan.

### Contoh 2
```powershell
PS C:\> Get-AzAlertProcessingRule -ResourceGroupName "test-rg"
```

Cantumkan semua aturan pemrosesan pemberitahuan yang dikonfigurasi dalam grup sumber daya test-rg.

### Contoh: 3
```powershell
PS C:\> Get-AzAlertProcessingRule -ResourceGroupName "test-rg" -Name "Test-AlertProcessing-Rule" | Format-List
```

Dapatkan aturan pemrosesan pemberitahuan dengan nama Test-AlertProcessing-Rule di grup sumber daya test-rg.

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
Nama aturan pemrosesan pemberitahuan.

```yaml
Type: System.String
Parameter Sets: ListAlertProcessingRules
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: System.String
Parameter Sets: AlertProcessingRuleByName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama Grup Sumber Daya tempat aturan pemrosesan pemberitahuan berada.

```yaml
Type: System.String
Parameter Sets: ListAlertProcessingRules, ListAlertProcessingRulesByResourceGroupName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: System.String
Parameter Sets: AlertProcessingRuleByName
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

### Microsoft.Azure.Commands.AlertsManagement.OutputModels.PSAlertProcessingRule

## NOTES

## RELATED LINKS
