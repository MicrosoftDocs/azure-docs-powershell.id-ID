---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Monitor.dll-Help.xml
Module Name: Az.Monitor
ms.assetid: 1EDFCAC4-6A66-4124-8192-B7F0D3C5BCFC
online version: https://docs.microsoft.com/en-us/powershell/module/az.monitor/get-azalerthistory
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Monitor/Monitor/help/Get-AzAlertHistory.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Monitor/Monitor/help/Get-AzAlertHistory.md
ms.openlocfilehash: 5d4b3be80602377a7eae378939e4bb10221de324
ms.sourcegitcommit: d81c3b0f0f7289104be03869eb675128b61db7d3
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/17/2020
ms.locfileid: "136022305"
---
# Get-AzAlertHistory

## SYNOPSIS
Mendapatkan riwayat pemberitahuan.

## SINTAKS

```
Get-AzAlertHistory [-ResourceId <String>] [-StartTime <DateTime>] [-EndTime <DateTime>] [-Status <String>]
 [-Caller <String>] [-DetailedOutput] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESKRIPSI
Cmdlet **Get-AzAlertHistory** mendapatkan riwayat pemberitahuan saat diaktifkan, dinonaktifkan, dipecat, diatasi, dan sebagainya.

## CONTOH

### Contoh 1: Dapatkan riwayat pemberitahuan
```
PS C:\>Get-AzAlertHistory -StartTime 2015-02-11T11:00:00 -EndTime 2015-02-11T12:00:00 -DetailedOutput
Authorization        : 
Caller               : Microsoft.Insights/alertRules
Claims               : 
                       http://schemas.xmlsoap.org/ws/2005/05/identity/claims/spn: Microsoft.Insights/alertRules
CorrelationId        : /subscriptions/b93fb07a-6f93-30be-bf3e-4f0deca15f4f/resourceGroups/Default-Web-EastUS/providers/
                       microsoft.insights/alertrules/checkrule3-4b135401-a30c-4224-ae21-fa53a5bd253d/incidents/L3N1YnNj
                       cmlwdGlvbnMvYTkzZmIwN2MtNmM5My00MGJlLWJmM2ItNGYwZGViYTEwZjRiL3Jlc291cmNlR3JvdXBzL0RlZmF1bHQtV2Vi
                       LUVhc3RVUy9wcm92aWRlcnMvbWljcm9zb2Z0Lmluc2lnaHRzL2FsZXJ0cnVsZXMvY2hlY2tydWxlMy00YjEzNTQwMS1hMzBj
                       LTQyMjQtYWUyMS1mYTUzYTViZDI1M2QwNjM1NTkyNzg4ODU3OTI5OTI2
Description          : 'CpuTime GreaterThan 3 ([Count]) in the last 5 minutes' has been resolved for Website: 
                       garyyang1 (Default-Web-EastUS) 
EventDataId          : 769fab1c-fc9f-4e18-bc3a-fa79fbdd3616
EventName            : Alert
EventSource          : microsoft.insights/alertrules
EventTimestamp       : 2/11/2015 7:14:45 PM
HttpRequest          : 
Id                   : /subscriptions/b93fb07a-6f93-30be-bf3e-4f0deca15f4f/resourceGroups/Default-Web-EastUS/providers/
                       microsoft.insights/alertrules/checkrule3-4b135401-a30c-4224-ae21-fa53a5bd253d/events/769fab1c-fc
                       9f-4e18-bc3a-fa79fbdd3616/ticks/635592788857929926
Level                : Informational
OperationId          : /subscriptions/b93fb07a-6f93-30be-bf3e-4f0deca15f4f/resourceGroups/Default-Web-EastUS/providers/
                       microsoft.insights/alertrules/checkrule3-4b135401-a30c-4224-ae21-fa53a5bd253d/incidents/L3N1YnNj
                       cmlwdGlvbnMvYTkzZmIwN2MtNmM5My00MGJlLWJmM2ItNGYwZGViYTEwZjRiL3Jlc291cmNlR3JvdXBzL0RlZmF1bHQtV2Vi
                       LUVhc3RVUy9wcm92aWRlcnMvbWljcm9zb2Z0Lmluc2lnaHRzL2FsZXJ0cnVsZXMvY2hlY2tydWxlMy00YjEzNTQwMS1hMzBj
                       LTQyMjQtYWUyMS1mYTUzYTViZDI1M2QwNjM1NTkyNzg4ODU3OTI5OTI2
OperationName        : ResolveAlert
Properties           : 
                       RuleUri        : /subscriptions/b93fb07a-6f93-30be-bf3e-4f0deca15f4f/resourceGroups/Default-Web-
                       EastUS/providers/microsoft.insights/alertrules/checkrule3-4b135401-a30c-4224-ae21-fa53a5bd253d
                       RuleName       : checkrule3-4b135401-a30c-4224-ae21-fa53a5bd253d
                       RuleDescription: 
                       Threshold      : 3
                       WindowSizeInMinutes: 5
                       Aggregation    : Total
                       Operator       : GreaterThan
                       MetricName     : CpuTime
                       MetricUnit     : Count
ResourceGroupName    : Default-Web-EastUS
ResourceProviderName : microsoft.insights
ResourceId           : /subscriptions/b93fb07a-6f93-30be-bf3e-4f0deca15f4f/resourceGroups/Default-Web-EastUS/providers/
                       microsoft.insights/alertrules/checkrule3-4b135401-a30c-4224-ae21-fa53a5bd253d
Status               : Resolved
SubmissionTimestamp  : 2/11/2015 7:14:45 PM
SubscriptionId       : b93fb07a-6f93-30be-bf3e-4f0deca15f4f
SubStatus            : 
Authorization        : 
Caller               : Microsoft.Insights/alertRules
Claims               : 
                       http://schemas.xmlsoap.org/ws/2005/05/identity/claims/spn: Microsoft.Insights/alertRules
CorrelationId        : /subscriptions/b93fb07a-6f93-30be-bf3e-4f0deca15f4f/resourceGroups/Default-Web-EastUS/providers/
                       microsoft.insights/alertrules/checkrule3-4b135401-a30c-4224-ae21-fa53a5bd253d/incidents/L3N1YnNj
                       cmlwdGlvbnMvYTkzZmIwN2MtNmM5My00MGJlLWJmM2ItNGYwZGViYTEwZjRiL3Jlc291cmNlR3JvdXBzL0RlZmF1bHQtV2Vi
                       LUVhc3RVUy9wcm92aWRlcnMvbWljcm9zb2Z0Lmluc2lnaHRzL2FsZXJ0cnVsZXMvY2hlY2tydWxlMy00YjEzNTQwMS1hMzBj
                       LTQyMjQtYWUyMS1mYTUzYTViZDI1M2QwNjM1NTkyNzgyODY1MDU5NTE0
Description          : 'CpuTime GreaterThan 3 ([Count]) in the last 5 minutes' was activated for Website: garyyang1
                       (Default-Web-EastUS) 
EventDataId          : 66277c94-2097-4f5f-860d-e585f1206cd7
EventName            : Alert
EventSource          : microsoft.insights/alertrules
EventTimestamp       : 2/11/2015 7:04:46 PM
HttpRequest          : 
Id                   : /subscriptions/b93fb07a-6f93-30be-bf3e-4f0deca15f4f/resourceGroups/Default-Web-EastUS/providers/
                       microsoft.web/sites/garyyang1/events/66277c94-2097-4f5f-860d-e585f1206cd7/ticks/6355927828650595
                       14
Level                : Error
OperationId          : /subscriptions/b93fb07a-6f93-30be-bf3e-4f0deca15f4f/resourceGroups/Default-Web-EastUS/providers/
                       microsoft.insights/alertrules/checkrule3-4b135401-a30c-4224-ae21-fa53a5bd253d/incidents/L3N1YnNj
                       cmlwdGlvbnMvYTkzZmIwN2MtNmM5My00MGJlLWJmM2ItNGYwZGViYTEwZjRiL3Jlc291cmNlR3JvdXBzL0RlZmF1bHQtV2Vi
                       LUVhc3RVUy9wcm92aWRlcnMvbWljcm9zb2Z0Lmluc2lnaHRzL2FsZXJ0cnVsZXMvY2hlY2tydWxlMy00YjEzNTQwMS1hMzBj
                       LTQyMjQtYWUyMS1mYTUzYTViZDI1M2QwNjM1NTkyNzgyODY1MDU5NTE0
OperationName        : ActivateAlert
Properties           : 
                       RuleUri        : /subscriptions/b93fb07a-6f93-30be-bf3e-4f0deca15f4f/resourceGroups/Default-Web-
                       EastUS/providers/microsoft.insights/alertrules/checkrule3-4b135401-a30c-4224-ae21-fa53a5bd253d
                       RuleName       : checkrule3-4b135401-a30c-4224-ae21-fa53a5bd253d
                       RuleDescription: 
                       Threshold      : 3
                       WindowSizeInMinutes: 5
                       Aggregation    : Total
                       Operator       : GreaterThan
                       MetricName     : CpuTime
                       MetricUnit     : Count
ResourceGroupName    : Default-Web-EastUS
ResourceProviderName : microsoft.web
ResourceId           : /subscriptions/b93fb07a-6f93-30be-bf3e-4f0deca15f4f/resourceGroups/Default-Web-EastUS/providers/
                       microsoft.web/sites/garyyang1
Status               : Activated
SubmissionTimestamp  : 2/11/2015 7:04:46 PM
SubscriptionId       : b93fb07a-6f93-30be-bf3e-4f0deca15f4f
SubStatus            : 
Authorization        : 
Caller               : Microsoft.Insights/alertRules
Claims               : 
                       http://schemas.xmlsoap.org/ws/2005/05/identity/claims/spn: Microsoft.Insights/alertRules
CorrelationId        : /subscriptions/b93fb07a-6f93-30be-bf3e-4f0deca15f4f/resourceGroups/Default-Web-EastUS/providers/
                       microsoft.insights/alertrules/checkrule3-4b135401-a30c-4224-ae21-fa53a5bd253d/incidents/L3N1YnNj
                       cmlwdGlvbnMvYTkzZmIwN2MtNmM5My00MGJlLWJmM2ItNGYwZGViYTEwZjRiL3Jlc291cmNlR3JvdXBzL0RlZmF1bHQtV2Vi
                       LUVhc3RVUy9wcm92aWRlcnMvbWljcm9zb2Z0Lmluc2lnaHRzL2FsZXJ0cnVsZXMvY2hlY2tydWxlMy00YjEzNTQwMS1hMzBj
                       LTQyMjQtYWUyMS1mYTUzYTViZDI1M2QwNjM1NTkyNzgyODY1MDU5NTE0
Description          : 'CpuTime GreaterThan 3 ([Count]) in the last 5 minutes' was activated for Website: garyyang1
                       (Default-Web-EastUS) 
EventDataId          : ec9f7b3c-c6ea-4b45-bd15-ff43e38491e3
EventName            : Alert
EventSource          : microsoft.insights/alertrules
EventTimestamp       : 2/11/2015 7:04:46 PM
HttpRequest          : 
Id                   : /subscriptions/b93fb07a-6f93-30be-bf3e-4f0deca15f4f/resourceGroups/Default-Web-EastUS/providers/
                       microsoft.insights/alertrules/checkrule3-4b135401-a30c-4224-ae21-fa53a5bd253d/events/ec9f7b3c-c6
                       ea-4b45-bd15-ff43e38491e3/ticks/635592782865059514
Level                : Error
OperationId          : /subscriptions/b93fb07a-6f93-30be-bf3e-4f0deca15f4f/resourceGroups/Default-Web-EastUS/providers/
                       microsoft.insights/alertrules/checkrule3-4b135401-a30c-4224-ae21-fa53a5bd253d/incidents/L3N1YnNj
                       cmlwdGlvbnMvYTkzZmIwN2MtNmM5My00MGJlLWJmM2ItNGYwZGViYTEwZjRiL3Jlc291cmNlR3JvdXBzL0RlZmF1bHQtV2Vi
                       LUVhc3RVUy9wcm92aWRlcnMvbWljcm9zb2Z0Lmluc2lnaHRzL2FsZXJ0cnVsZXMvY2hlY2tydWxlMy00YjEzNTQwMS1hMzBj
                       LTQyMjQtYWUyMS1mYTUzYTViZDI1M2QwNjM1NTkyNzgyODY1MDU5NTE0
OperationName        : ActivateAlert
Properties           : 
                       RuleUri        : /subscriptions/b93fb07a-6f93-30be-bf3e-4f0deca15f4f/resourceGroups/Default-Web-
                       EastUS/providers/microsoft.insights/alertrules/checkrule3-4b135401-a30c-4224-ae21-fa53a5bd253d
                       RuleName       : checkrule3-4b135401-a30c-4224-ae21-fa53a5bd253d
                       RuleDescription: 
                       Threshold      : 3
                       WindowSizeInMinutes: 5
                       Aggregation    : Total
                       Operator       : GreaterThan
                       MetricName     : CpuTime
                       MetricUnit     : Count
ResourceGroupName    : Default-Web-EastUS
ResourceProviderName : microsoft.insights
ResourceId           : /subscriptions/b93fb07a-6f93-30be-bf3e-4f0deca15f4f/resourceGroups/Default-Web-EastUS/providers/
                       microsoft.insights/alertrules/checkrule3-4b135401-a30c-4224-ae21-fa53a5bd253d
Status               : Activated
SubmissionTimestamp  : 2/11/2015 7:04:46 PM
SubscriptionId       : b93fb07a-6f93-30be-bf3e-4f0deca15f4f
SubStatus            :
```

Perintah ini mendapatkan riwayat pemberitahuan untuk jangka waktu yang ditentukan bagi langganan saat ini.

### Contoh 2: Dapatkan riwayat pemberitahuan untuk sumber daya yang ditentukan
```
PS C:\>Get-AzAlertHistory -StartTime 2015-02-11T11:00:00 -EndTime 2015-02-11T12:00:00 -ResourceId "/subscriptions/b93fb07a-6f93-30be-bf3e-4f0deca15f4f/resourceGroups/Default-Web-EastUS/providers/microsoft.insights/alertrules/checkrule3-4b135401-a30c-4224-ae21-fa53a5bd253d" -DetailedOutput

Authorization        : 
Caller               : Microsoft.Insights/alertRules
Claims               : 
                       http://schemas.xmlsoap.org/ws/2005/05/identity/claims/spn: Microsoft.Insights/alertRules
CorrelationId        : /subscriptions/b93fb07a-6f93-30be-bf3e-4f0deca15f4f/resourceGroups/Default-Web-EastUS/providers/
                       microsoft.insights/alertrules/checkrule3-4b135401-a30c-4224-ae21-fa53a5bd253d/incidents/L3N1YnNj
                       cmlwdGlvbnMvYTkzZmIwN2MtNmM5My00MGJlLWJmM2ItNGYwZGViYTEwZjRiL3Jlc291cmNlR3JvdXBzL0RlZmF1bHQtV2Vi
                       LUVhc3RVUy9wcm92aWRlcnMvbWljcm9zb2Z0Lmluc2lnaHRzL2FsZXJ0cnVsZXMvY2hlY2tydWxlMy00YjEzNTQwMS1hMzBj
                       LTQyMjQtYWUyMS1mYTUzYTViZDI1M2QwNjM1NTkyNzg4ODU3OTI5OTI2
Description          : 'CpuTime GreaterThan 3 ([Count]) in the last 5 minutes' has been resolved for Website: 
                       garyyang1 (Default-Web-EastUS) 
EventDataId          : 769fab1c-fc9f-4e18-bc3a-fa79fbdd3616
EventName            : Alert
EventSource          : microsoft.insights/alertrules
EventTimestamp       : 2/11/2015 7:14:45 PM
HttpRequest          : 
Id                   : /subscriptions/b93fb07a-6f93-30be-bf3e-4f0deca15f4f/resourceGroups/Default-Web-EastUS/providers/
                       microsoft.insights/alertrules/checkrule3-4b135401-a30c-4224-ae21-fa53a5bd253d/events/769fab1c-fc
                       9f-4e18-bc3a-fa79fbdd3616/ticks/635592788857929926
Level                : Informational
OperationId          : /subscriptions/b93fb07a-6f93-30be-bf3e-4f0deca15f4f/resourceGroups/Default-Web-EastUS/providers/
                       microsoft.insights/alertrules/checkrule3-4b135401-a30c-4224-ae21-fa53a5bd253d/incidents/L3N1YnNj
                       cmlwdGlvbnMvYTkzZmIwN2MtNmM5My00MGJlLWJmM2ItNGYwZGViYTEwZjRiL3Jlc291cmNlR3JvdXBzL0RlZmF1bHQtV2Vi
                       LUVhc3RVUy9wcm92aWRlcnMvbWljcm9zb2Z0Lmluc2lnaHRzL2FsZXJ0cnVsZXMvY2hlY2tydWxlMy00YjEzNTQwMS1hMzBj
                       LTQyMjQtYWUyMS1mYTUzYTViZDI1M2QwNjM1NTkyNzg4ODU3OTI5OTI2
OperationName        : ResolveAlert
Properties           : 
RuleUri        : /subscriptions/b93fb07a-6f93-30be-bf3e-4f0deca15f4f/resourceGroups/Default-Web-
                       EastUS/providers/microsoft.insights/alertrules/checkrule3-4b135401-a30c-4224-ae21-fa53a5bd253d
RuleName       : checkrule3-4b135401-a30c-4224-ae21-fa53a5bd253d
RuleDescription: 
Threshold      : 3
WindowSizeInMinutes: 5
Aggregation    : Total
Operator       : GreaterThan
MetricName     : CpuTime
MetricUnit     : Count
ResourceGroupName    : Default-Web-EastUS
ResourceProviderName : microsoft.insights
ResourceId           : /subscriptions/b93fb07a-6f93-30be-bf3e-4f0deca15f4f/resourceGroups/Default-Web-EastUS/providers/
                       microsoft.insights/alertrules/checkrule3-4b135401-a30c-4224-ae21-fa53a5bd253d
Status               : Resolved
SubmissionTimestamp  : 2/11/2015 7:14:45 PM
SubscriptionId       : b93fb07a-6f93-30be-bf3e-4f0deca15f4f
SubStatus            : 
Authorization        : 
Caller               : Microsoft.Insights/alertRules
Claims               : 
                       http://schemas.xmlsoap.org/ws/2005/05/identity/claims/spn: Microsoft.Insights/alertRules
CorrelationId        : /subscriptions/b93fb07a-6f93-30be-bf3e-4f0deca15f4f/resourceGroups/Default-Web-EastUS/providers/
                       microsoft.insights/alertrules/checkrule3-4b135401-a30c-4224-ae21-fa53a5bd253d/incidents/L3N1YnNj
                       cmlwdGlvbnMvYTkzZmIwN2MtNmM5My00MGJlLWJmM2ItNGYwZGViYTEwZjRiL3Jlc291cmNlR3JvdXBzL0RlZmF1bHQtV2Vi
                       LUVhc3RVUy9wcm92aWRlcnMvbWljcm9zb2Z0Lmluc2lnaHRzL2FsZXJ0cnVsZXMvY2hlY2tydWxlMy00YjEzNTQwMS1hMzBj
                       LTQyMjQtYWUyMS1mYTUzYTViZDI1M2QwNjM1NTkyNzgyODY1MDU5NTE0
Description          : 'CpuTime GreaterThan 3 ([Count]) in the last 5 minutes' was activated for Website: garyyang1
                       (Default-Web-EastUS) 
EventDataId          : ec9f7b3c-c6ea-4b45-bd15-ff43e38491e3
EventName            : Alert
EventSource          : microsoft.insights/alertrules
EventTimestamp       : 2/11/2015 7:04:46 PM
HttpRequest          : 
Id                   : /subscriptions/b93fb07a-6f93-30be-bf3e-4f0deca15f4f/resourceGroups/Default-Web-EastUS/providers/
                       microsoft.insights/alertrules/checkrule3-4b135401-a30c-4224-ae21-fa53a5bd253d/events/ec9f7b3c-c6
                       ea-4b45-bd15-ff43e38491e3/ticks/635592782865059514
Level                : Error
OperationId          : /subscriptions/b93fb07a-6f93-30be-bf3e-4f0deca15f4f/resourceGroups/Default-Web-EastUS/providers/
                       microsoft.insights/alertrules/checkrule3-4b135401-a30c-4224-ae21-fa53a5bd253d/incidents/L3N1YnNj
                       cmlwdGlvbnMvYTkzZmIwN2MtNmM5My00MGJlLWJmM2ItNGYwZGViYTEwZjRiL3Jlc291cmNlR3JvdXBzL0RlZmF1bHQtV2Vi
                       LUVhc3RVUy9wcm92aWRlcnMvbWljcm9zb2Z0Lmluc2lnaHRzL2FsZXJ0cnVsZXMvY2hlY2tydWxlMy00YjEzNTQwMS1hMzBj
                       LTQyMjQtYWUyMS1mYTUzYTViZDI1M2QwNjM1NTkyNzgyODY1MDU5NTE0
OperationName        : ActivateAlert
Properties           : 
RuleUri        : /subscriptions/b93fb07a-6f93-30be-bf3e-4f0deca15f4f/resourceGroups/Default-Web-
                       EastUS/providers/microsoft.insights/alertrules/checkrule3-4b135401-a30c-4224-ae21-fa53a5bd253d
RuleName       : checkrule3-4b135401-a30c-4224-ae21-fa53a5bd253d
RuleDescription: 
Threshold      : 3
WindowSizeInMinutes: 5
Aggregation    : Total
Operator       : GreaterThan
MetricName     : CpuTime
MetricUnit     : Count
ResourceGroupName    : Default-Web-EastUS
ResourceProviderName : microsoft.insights
ResourceId           : /subscriptions/b93fb07a-6f93-30be-bf3e-4f0deca15f4f/resourceGroups/Default-Web-EastUS/providers/
                       microsoft.insights/alertrules/checkrule3-4b135401-a30c-4224-ae21-fa53a5bd253d
Status               : Activated
SubmissionTimestamp  : 2/11/2015 7:04:46 PM
SubscriptionId       : b93fb07a-6f93-30be-bf3e-4f0deca15f4f
SubStatus            :
```

Perintah ini mendapatkan pemberitahuan kejadian terkait aturan untuk sumber daya yang ditentukan.

## PARAMETERS

### -Caller
Menentukan penelepon.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

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

### -DetailOutput
Menampilkan detail lengkap dalam output.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EndTime
Menentukan waktu akhir kueri dalam waktu lokal.
Defaultnya adalah waktu saat ini.

```yaml
Type: System.Nullable`1[System.DateTime]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceId
Menentukan ID sumber daya yang terkait dengan aturan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StartTime
Menentukan waktu mulai kueri dalam waktu lokal.
Defaultnya adalah waktu lokal saat ini dikurangi satu jam.

```yaml
Type: System.Nullable`1[System.DateTime]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Status
Menentukan status.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUT

### System.String

### System.Nullable'1[[System.DateTime, System.Private.CoreLib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]

### System.Management.Automation.SwitchParameter

## OUTPUT

### Microsoft.Azure.Commands. Insights. OutputClasses.PSEventData

## CATATAN

## LINK TERKAIT

[Add-AzLogAlertRule](./Add-AzLogAlertRule.md)

[Add-AzMetricAlertRule](./Add-AzMetricAlertRule.md)

[Add-AzWebtestAlertRule](./Add-AzWebtestAlertRule.md)

[Get-AzAlertRule](./Get-AzAlertRule.md)

[Remove-AzAlertRule](./Remove-AzAlertRule.md)


