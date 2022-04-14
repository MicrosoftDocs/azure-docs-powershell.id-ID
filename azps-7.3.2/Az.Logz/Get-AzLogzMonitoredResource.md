---
external help file: ''
Module Name: Az.Logz
online version: https://docs.microsoft.com/powershell/module/az.logz/get-azlogzmonitoredresource
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Logz/help/Get-AzLogzMonitoredResource.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Logz/help/Get-AzLogzMonitoredResource.md
ms.openlocfilehash: 06350833b40490c6f1c616e4473cb58eaee1fb8e
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142067935"
---
# Get-AzLogzMonitoredResource

## SYNOPSIS
Cantumkan sumber daya yang saat ini sedang dipantau oleh sumber daya monitor Logz.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.logz/get-azlogzmonitoredresource) untuk informasi terbaru.

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
Cantumkan sumber daya yang saat ini sedang dipantau oleh sumber daya monitor Logz.

## EXAMPLES

### Contoh 1: Cantumkan sumber daya yang sedang dipantau oleh sumber daya monitor Logz
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

### Contoh 2: Daftar sumber daya yang sedang dipantau oleh sub akun Logz
```powershell
PS C:\> Get-AzLogzMonitoredResource -ResourceGroupName LPTrials -MonitorName lpatlogz -SubAccountName lpslogzsubaccount

ReasonForLogsStatus ReasonForMetricsStatus SendingLog SendingMetric
------------------- ---------------------- ---------- -------------
Other                                      False
```

Perintah ini mencantumkan sumber daya yang sedang dipantau oleh sub akun Logz

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
Pantau nama sumber daya

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
Nama ini tidak peka huruf besar kecil.

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
Pantau nama sumber daya

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Logz.Models.Api20201001Preview.IMonitoredResource

## CATATAN

ALIAS

## RELATED LINKS

