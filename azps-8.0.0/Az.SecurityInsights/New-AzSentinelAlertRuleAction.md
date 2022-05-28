---
external help file: Microsoft.Azure.PowerShell.Cmdlets.SecurityInsights.dll-Help.xml
Module Name: Az.SecurityInsights
online version: https://docs.microsoft.com/powershell/module/az.securityinsights/new-azsentinelalertruleaction
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SecurityInsights/SecurityInsights/help/New-AzSentinelAlertRuleAction.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/SecurityInsights/SecurityInsights/help/New-AzSentinelAlertRuleAction.md
ms.openlocfilehash: 3745fa5577796fb0041b5cddbd1d92eb9049db0e
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145519306"
---
# New-AzSentinelAlertRuleAction

## SYNOPSIS
Tambahkan Respons Otomatis ke Aturan Analitik.

## SYNTAX

```
New-AzSentinelAlertRuleAction -ResourceGroupName <String> -WorkspaceName <String> -AlertRuleId <String>
 [-ActionId <String>] -LogicAppResourceId <String> -TriggerUri <String>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzSentinelAlertRuleAction** membuat Respons Otomatis untuk Aturan Pemberitahuan di ruang kerja yang ditentukan.
Anda harus menyediakan Logic App ResourceId dan Trigger Uri yang dapat ditemukan menggunakan [modul Azure Logic Apps PowerShell](https://docs.microsoft.com/en-us/powershell/module/az.logicapp/get-azlogicapp?view=azps-5.6.0).
Anda dapat menggunakan parameter *Konfirmasi* dan variabel $ConfirmPreference Windows PowerShell untuk mengontrol apakah cmdlet meminta konfirmasi.

## EXAMPLES

### Contoh 1
```powershell
$LogicAppResourceId = Get-AzLogicApp -ResourceGroupName "MyResourceGroup" -Name "Reset-AADPassword"
$LogicAppTriggerUri = Get-AzLogicAppTriggerCallbackUrl -ResourceGroupName "MyResourceGroup" -Name "Reset-AADPassword" -TriggerName "When_a_response_to_an_Azure_Sentinel_alert_is_triggered"
$AlertRuleAction = New-AzSentinelAlertRuleAction -ResourceGroupName "MyResourceGroup" -WorkspaceName "MyWorkspaceName" -AlertRuleId "MyAlertRuleId" -LogicAppResourceId ($LogicAppResourceId.Id) -TriggerUri ($LogicAppTriggerUri.Value)
```

Contoh ini membuat AlertRuleAction untuk Aturan Pemberitahuan yang ditentukan menggunakan properti Aplikasi Logika, lalu menyimpannya dalam variabel $AlertRuleAction.<br/>
Kemudian kita menggunakan cmdlet New-AzSentinelAlertRuleAction untuk menambahkan Aplikasi Logika sebagai tindakan ke AlertRule spekifk.

### Contoh 2
```powershell
$SentinelConnection = @{
    ResourceGroupName = "myResourceGroupName"
    WorkspaceName = "mySentinelWorkspaceName"
}

$LogicAppConnection = @{
    ResourceGroupName = "myLogicAppResourceGroupName"
    Name = "Reset-AADPassword"
}

$LogicAppResourceId = Get-AzLogicApp @LogicAppConnection
$LogicAppTriggerUri = Get-AzLogicAppTriggerCallbackUrl @LogicAppConnection -TriggerName "When_a_response_to_an_Azure_Sentinel_alert_is_triggered"
$AnalyticsRule = Get-AzSentinelAlertRule @SentinelConnection | Where-Object {$PSItem.DisplayName -eq "Mimikatz Detected"}
$AlertRuleAction = New-AzSentinelAlertRuleAction @SentinelConnection -AlertRuleId $AnalyticsRule.Name -LogicAppResourceId ($LogicAppResourceId.Id) -TriggerUri ($LogicAppTriggerUri.Value)
```

Contoh ini menggunakan 2 objek koneksi untuk terhubung dengan Azure Sentinel dan untuk mendapatkan Aplikasi Logika tertentu. <br/>
Kemudian Aturan Analitik tertentu, berdasarkan nama tampilan, diambil dan digunakan dalam cmdlet **New-AzSentinelAlertRuleAction** akhir untuk menambahkan Aplikasi Logika ke Aturan Analitik.

## PARAMETERS

### -ActionId
Id Tindakan.

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

### -AlertRuleId
Id Aturan Pemberitahuan.

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

### -LogicAppResourceId
Id Sumber Daya Aplikasi Logika Tindakan.

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

### -ResourceGroupName
Nama grup sumber daya.

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

### -TriggerUri
Uri Pemicu Aplikasi Logika Tindakan.

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

### -WorkspaceName
Nama Ruang Kerja.

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
Menunjukkan yang akan terjadi jika cmdlet dijalankan. Cmdlet tidak dijalankan.

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

### Tidak ada
## OUTPUTS

### Microsoft.Azure.Commands.SecurityInsights.Models.Actions.PSSentinelActionResponse
## NOTES

## RELATED LINKS
