---
external help file: ''
Module Name: Az.Logz
online version: https://docs.microsoft.com/powershell/module/az.logz/get-azlogzmonitoredresource
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Logz/help/Get-AzLogzMonitoredResource.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Logz/help/Get-AzLogzMonitoredResource.md
ms.openlocfilehash: 8d4b6b6035a443f52fc1c21e4993132c7d91e67c
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138258604"
---
# Get-AzLogzMonitoredResource

## SYNOPSIS
List the resources currently being monitored by the Logz monitor resource.

## SYNTAX

### Daftar (Default)
```
Get-AzLogzMonitoredResource -MonitorName <String> -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### ListBySubAccount
```
Get-AzLogzMonitoredResource -MonitorName <String> -ResourceGroupName <String> -SubAccountName <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
List the resources currently being monitored by the Logz monitor resource.

## EXAMPLES

### Contoh 1:  List the resources currently being monitored by the Logz monitor resource
```powershell
PS C:\> Get-AzLogzMonitoredResource -ResourceGroupName LPTrials -MonitorName lpatlogz

ReasonForLogsStatus            ReasonForMetricsStatus SendingLog SendingMetric
-------------------            ---------------------- ---------- -------------
CapturedByRules                                       True
CapturedByRules                                       True
CapturedByRules                                       True
CapturedByRules                                       True
CapturedByRules                                       True
```

Perintah ini mencantumkan sumber daya yang saat ini sedang dipantau oleh sumber daya monitor Logz.

### Contoh 2:  List the resources currently being monitored by the Logz sub account
```powershell
PS C:\> Get-AzLogzMonitoredResource -ResourceGroupName LPTrials -MonitorName lpatlogz -SubAccountName lpslogzsubaccount

ReasonForLogsStatus ReasonForMetricsStatus SendingLog SendingMetric
------------------- ---------------------- ---------- -------------
Other                                      False
```

Perintah ini mencantumkan sumber daya yang saat ini sedang dipantau oleh sub akun Logz

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

### -MonitorName
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

### -SubAccountName
Memantau nama sumber daya

```yaml
Type: System.String
Parameter Sets: ListBySubAccount
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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Logz.Models.Api20201001Preview.IMonitoredResource

## CATATAN

ALIAS

## RELATED LINKS

