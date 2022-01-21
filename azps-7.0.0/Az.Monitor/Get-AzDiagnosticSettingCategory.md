---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Monitor.dll-Help.xml
Module Name: Az.Monitor
online version: https://docs.microsoft.com/powershell/module/az.monitor/get-azdiagnosticsettingcategory
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Monitor/Monitor/help/Get-AzDiagnosticSettingCategory.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Monitor/Monitor/help/Get-AzDiagnosticSettingCategory.md
ms.openlocfilehash: f4fa2ee668621841c81651e90ebb28ef837d79a9
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136574938"
---
# Get-AzDiagnosticSettingCategory

## SYNOPSIS
Dapatkan atau list kategori pengaturan diagnostik yang didukung untuk sumber daya Azure.

## SYNTAX

```
Get-AzDiagnosticSettingCategory -TargetResourceId <String> [-Name <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Dapatkan atau list kategori pengaturan diagnostik yang didukung untuk sumber daya Azure.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Get-AzDiagnosticSettingCategory -TargetResourceId /subscriptions/XXXXXXXXXXXX/resourceGroups/XXXXXXXX/providers/Microsoft.Network/virtualNetworks/XXXXXXXX
Id           : /subscriptions/XXXXXXXXXXXX/resourceGroups/XXXXXXXX/providers/Microsoft.Network/virtualNetworks/XXXXXXXX/providers/Microsoft.Insights/diagnosticSettingsCategories/VMProtectionAlerts
Name         : VMProtectionAlerts
Type         : Microsoft.Insights/diagnosticSettingsCategories
CategoryType : Logs

Id           : /subscriptions/XXXXXXXXXXXX/resourceGroups/XXXXXXXX/providers/Microsoft.Network/virtualNetworks/XXXXXXXX/providers/Microsoft.Insights/diagnosticSettingsCategories/AllMetrics
Name         : AllMetrics
Type         : Microsoft.Insights/diagnosticSettingsCategories
CategoryType : Metrics
```

Dapatkan kategori pengaturan diagnostik yang didukung untuk jaringan virtual.

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
Nama kategori pengaturan diagnostik

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

### -TargetResourceId
Id sumber daya target

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands. Insights. OutputClasses.PSDiagnosticSettingCategory

## CATATAN

## RELATED LINKS
