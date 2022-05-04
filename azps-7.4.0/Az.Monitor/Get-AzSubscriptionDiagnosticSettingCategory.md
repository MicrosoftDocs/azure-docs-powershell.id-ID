---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Monitor.dll-Help.xml
Module Name: Az.Monitor
online version: https://docs.microsoft.com/powershell/module/az.monitor/get-azsubscriptiondiagnosticsettingcategory
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Monitor/Monitor/help/Get-AzSubscriptionDiagnosticSettingCategory.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Monitor/Monitor/help/Get-AzSubscriptionDiagnosticSettingCategory.md
ms.openlocfilehash: c4a9e024d02a6988a30b23c2659f7536848cccd3
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144673792"
---
# Get-AzSubscriptionDiagnosticSettingCategory

## SYNOPSIS
Mendapatkan kategori pengaturan diagnostik untuk langganan.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.monitor/get-azsubscriptiondiagnosticsettingcategory) untuk informasi terbaru.

## SYNTAX

```
Get-AzSubscriptionDiagnosticSettingCategory [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan kategori pengaturan diagnostik untuk langganan.

## EXAMPLES

### Contoh 1
```powershell
Get-AzSubscriptionDiagnosticSettingCategory
```

```output
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

Mendapatkan kategori pengaturan diagnostik.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands. Insights. OutputClasses.PSSubscriptionDiagnosticSettingCategory

## NOTES

## RELATED LINKS
