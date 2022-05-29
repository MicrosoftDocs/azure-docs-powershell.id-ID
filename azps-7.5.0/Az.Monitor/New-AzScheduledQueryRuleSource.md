---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Monitor.dll-Help.xml
Module Name: Az.Monitor
online version: https://docs.microsoft.com/powershell/module/az.monitor/new-azscheduledqueryrulesource
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Monitor/Monitor/help/New-AzScheduledQueryRuleSource.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Monitor/Monitor/help/New-AzScheduledQueryRuleSource.md
ms.openlocfilehash: 0b38fa1bfc947020563e44365baa1ce63dd8be11
ms.sourcegitcommit: 321c644cf2161807a71e1af318fc5c5311d22e25
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/25/2022
ms.locfileid: "145810944"
---
# New-AzScheduledQueryRuleSource

## SYNOPSIS
Membuat objek jenis Sumber

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.monitor/new-azscheduledqueryrulesource) untuk informasi terbaru.

## SYNTAX

```
New-AzScheduledQueryRuleSource -Query <String> [-AuthorizedResource <String[]>] -DataSourceId <String>
 [-QueryType <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Membuat objek berjenis Sumber.
Objek ini akan diteruskan ke perintah yang membuat Aturan Pemberitahuan Log

## EXAMPLES

### Contoh 1
```powershell
$source = New-AzScheduledQueryRuleSource -Query "Heartbeat | summarize AggregatedValue = count() by bin(TimeGenerated, 5m)" `
                  -DataSourceId "/subscriptions/b67f7fec-69fc-4974-9099-a26bd6ffeda3/resourceGroups/MyResourceGroup/providers/Microsoft.OperationalInsights/workspaces/MyWorkspace"  `
                  -QueryType "ResultCount"
```

### Contoh 2

Membuat objek berjenis Sumber. (dibuat otomatis)

```powershell <!-- Aladdin Generated Example --> 
New-AzScheduledQueryRuleSource -DataSourceId <String> -Query 'Heartbeat | summarize AggregatedValue = count() by bin(TimeGenerated, 5m)'
```

## PARAMETERS

### -AuthorizedResource
Daftar sumber daya yang diotorisasi untuk pemberitahuan ini

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

### -DataSourceId
Sumber data tempat pemberitahuan ini dibuat

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

### -Kueri
Kueri pemberitahuan

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

### -QueryType
Jenis Kueri - nilai yang saat ini didukung : ResultCount

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands. Insights. OutputClasses.PSScheduledQueryRuleSource

## NOTES

## RELATED LINKS
