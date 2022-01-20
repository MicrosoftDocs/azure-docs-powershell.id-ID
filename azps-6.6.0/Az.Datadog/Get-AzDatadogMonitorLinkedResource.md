---
external help file: ''
Module Name: Az.Datadog
online version: https://docs.microsoft.com/powershell/module/az.datadog/get-azdatadogmonitorlinkedresource
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Datadog/help/Get-AzDatadogMonitorLinkedResource.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Datadog/help/Get-AzDatadogMonitorLinkedResource.md
ms.openlocfilehash: 9775b4222d0b3d97b98d82ebac9850eb1e02e21c
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136365834"
---
# Get-AzDatadogMonitorLinkedResource

## SYNOPSIS
Daftar semua sumber daya Azure yang terkait ke organisasi Datadog yang sama sebagai sumber daya target.

## SYNTAX

```
Get-AzDatadogMonitorLinkedResource -Name <String> -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Daftar semua sumber daya Azure yang terkait ke organisasi Datadog yang sama sebagai sumber daya target.

## EXAMPLES

### Contoh 1: Daftar semua sumber daya Azure yang terkait ke organisasi Datadog yang sama sebagai sumber daya target
```powershell
PS C:\> Get-AzDatadogMonitorLinkedResource -ResourceGroupName azure-rg-Datadog -Name lucasDatadog

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

Perintah ini mencantumkan semua sumber daya Azure yang terkait ke organisasi Datadog yang sama sebagai sumber daya target.

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

### -Nama
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
Namanya peka huruf besar/huruf.

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

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Datadog.Models.Api20210301.ILinkedResource

## CATATAN

ALIAS

## RELATED LINKS

