---
external help file: ''
Module Name: Az.Datadog
online version: https://docs.microsoft.com/powershell/module/az.datadog/get-azdatadogmonitorlinkedresource
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Datadog/help/Get-AzDatadogMonitorLinkedResource.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Datadog/help/Get-AzDatadogMonitorLinkedResource.md
ms.openlocfilehash: d9f5efe215015242a5f6055a344cd3cefec301ca
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145746658"
---
# Get-AzDatadogMonitorLinkedResource

## SYNOPSIS
Cantumkan semua sumber daya Azure yang terkait dengan organisasi Datadog yang sama dengan sumber daya target.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.datadog/get-azdatadogmonitorlinkedresource) untuk informasi terbaru.

## SYNTAX

```
Get-AzDatadogMonitorLinkedResource -Name <String> -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Cantumkan semua sumber daya Azure yang terkait dengan organisasi Datadog yang sama dengan sumber daya target.

## EXAMPLES

### Contoh 1: Mencantumkan semua sumber daya Azure yang terkait dengan organisasi Datadog yang sama dengan sumber daya target
```powershell
Get-AzDatadogMonitorLinkedResource -ResourceGroupName azure-rg-Datadog -Name lucasDatadog
```

```output
Id
--
/SUBSCRIPTIONS/xxxxxxxxxxxxxx-xxxxxxx-xxxxxx/RESOURCEGROUPS/EUAP-ACR-01266F2538192A/PROVIDERS/MICROSOFT.Datadog/MONITORS/LIFTR-ACR-0126693370263
/SUBSCRIPTIONS/xxxxxxxxxxxxxx-xxxxxxx-xxxxxx/RESOURCEGROUPS/PROD-SUB-01278F01924690/PROVIDERS/MICROSOFT.Datadog/MONITORS/SUB01273EE24900C6832
/SUBSCRIPTIONS/xxxxxxxxxxxxxx-xxxxxxx-xxxxxx/RESOURCEGROUPS/CREATE-SSO-E4E2467832A/PROVIDERS/MICROSOFT.Datadog/MONITORS/LIFTR-CREATE-SSO-53326702
/SUBSCRIPTIONS/xxxxxxxxxxxxxx-xxxxxxx-xxxxxx/RESOURCEGROUPS/PROD-MUL-ACR-01277F790629/PROVIDERS/MICROSOFT.Datadog/MONITORS/LIFTR-ACR1-A3C8604150D
/SUBSCRIPTIONS/xxxxxxxxxxxxxx-xxxxxxx-xxxxxx/RESOURCEGROUPS/CREATE-68A6706056D95/PROVIDERS/MICROSOFT.Datadog/MONITORS/LIFTR-CREATE-2E312735B8
/SUBSCRIPTIONS/xxxxxxxxxxxxxx-xxxxxxx-xxxxxx/RESOURCEGROUPS/PROD-MUL-ACR-01279F943670/PROVIDERS/MICROSOFT.Datadog/MONITORS/LIFTR-ACR2-D46323262B4
/SUBSCRIPTIONS/xxxxxxxxxxxxxx-xxxxxxx-xxxxxx/RESOURCEGROUPS/CREATE-8288834488516/PROVIDERS/MICROSOFT.Datadog/MONITORS/LIFTR-CREATE-C7585255D1
/SUBSCRIPTIONS/xxxxxxxxxxxxxx-xxxxxxx-xxxxxx/RESOURCEGROUPS/CREATE-SSO-6E6618601FF/PROVIDERS/MICROSOFT.Datadog/MONITORS/LIFTR-CREATE-SSO-C5065109
/SUBSCRIPTIONS/xxxxxxxxxxxxxx-xxxxxxx-xxxxxx/RESOURCEGROUPS/PROD-MUL-ACR-012774705865/PROVIDERS/MICROSOFT.Datadog/MONITORS/LIFTR-ACR2-E2560749186
```

Perintah ini mencantumkan semua sumber daya Azure yang terkait dengan organisasi Datadog yang sama dengan sumber daya target.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases: AzureRMContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Memantau nama sumber daya

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
Nama ini tidak peka huruf besar/kecil.

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

### -SubscriptionId
ID langganan target.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
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

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Datadog.Models.Api20210301.ILinkedResource

## NOTES

ALIAS

## RELATED LINKS

