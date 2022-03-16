---
external help file: Microsoft.Azure.PowerShell.Cmdlets.AlertsManagement.dll-Help.xml
Module Name: Az.AlertsManagement
online version: https://docs.microsoft.com/powershell/module/az.alertsmanagement/get-azactionrule
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/AlertsManagement/AlertsManagement/help/Get-AzAlertProcessingRule.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/AlertsManagement/AlertsManagement/help/Get-AzAlertProcessingRule.md
ms.openlocfilehash: dbbe99a77a4257572a904a6818d3e3b740755359
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140004885"
---
# Get-AzAlertProcessingRule

## SYNOPSIS
Dapatkan Informasi Aturan Pemrosesan Pemberitahuan

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
**Cmdlet Get-AzAlertProcessingRule** mengonfigurasi aturan pemrosesan pemberitahuan.

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

Konfigurasikan semua aturan pemrosesan pemberitahuan yang dikonfigurasi dalam uji-rg grup sumber daya.

### Contoh 3
```powershell
PS C:\> Get-AzAlertProcessingRule -ResourceGroupName "test-rg" -Name "Test-AlertProcessing-Rule" | Format-List
```

Dapatkan aturan pemrosesan pemberitahuan dengan nama Test-AlertProcessing-Rule dalam grup sumber daya test-rg.

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


### -Nama
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
Nama Grup Sumber Daya di mana aturan pemrosesan pemberitahuan berada.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.AlertsManagement.OutputModels.PSAlertProcessingRule

## CATATAN

## RELATED LINKS
