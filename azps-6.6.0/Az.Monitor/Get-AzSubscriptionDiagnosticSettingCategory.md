---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Monitor.dll-Help.xml
Module Name: Az.Monitor
online version: https://docs.microsoft.com/powershell/module/az.monitor/get-azsubscriptiondiagnosticsettingcategory
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Monitor/Monitor/help/Get-AzSubscriptionDiagnosticSettingCategory.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Monitor/Monitor/help/Get-AzSubscriptionDiagnosticSettingCategory.md
ms.openlocfilehash: e05a8eefc6a769ee97b60deb1801e18fe6dfc7db
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136361085"
---
# Get-AzSubscriptionDiagnosticSettingCategory

## SYNOPSIS
Dapatkan kategori pengaturan diagnostik untuk langganan.

## SYNTAX

```
Get-AzSubscriptionDiagnosticSettingCategory [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Dapatkan kategori pengaturan diagnostik untuk langganan.

## EXAMPLES

### Contoh 1
```powershell
PS D:\> Get-AzSubscriptionDiagnosticSettingCategory

Name            CategoryType
----            ------------
Administrative          Logs
Security                Logs
ServiceHealth           Logs
Alert                   Logs
Recommendation          Logs
Policy                  Logs
Autoscale               Logs
ResourceHealth          Logs
```

Dapatkan kategori pengaturan diagnostik.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands. Insights. OutputClasses.PSSubscriptionDiagnosticSettingCategory

## CATATAN

## RELATED LINKS
