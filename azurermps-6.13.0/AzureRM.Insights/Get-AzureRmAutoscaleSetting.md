---
external help file: Microsoft.Azure.Commands.Insights.dll-Help.xml
Module Name: AzureRM.Insights
ms.assetid: 989CE245-FD1D-4E1D-90A2-2D7DA3975D0B
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.insights/get-azurermautoscalesetting
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Insights/Commands.Insights/help/Get-AzureRmAutoscaleSetting.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Insights/Commands.Insights/help/Get-AzureRmAutoscaleSetting.md
ms.openlocfilehash: 6bf59522b09d9a8a5c301860ab175eef8f7537b8
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142063942"
---
# Get-AzureRmAutoscaleSetting

## SYNOPSIS
Mendapatkan pengaturan Skala Otomatis.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Get-AzureRmAutoscaleSetting -ResourceGroupName <String> [-Name <String>] [-DetailedOutput]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRmAutoscaleSetting** mendapatkan semua pengaturan Skala Otomatis yang terkait dengan grup sumber daya atau pengaturan Skala Otomatis tertentu.

## EXAMPLES

### Contoh 1: Dapatkan pengaturan Skala Otomatis
```
PS C:\>Get-AzureRmAutoscaleSetting -ResourceGroup "Default-Web-EastUS" -DetailedOutput
resourceId : /subscriptions/b93fb07a-6f93-30be-bf3e-4f0deca15f4f/resourceGroups/Default-Web-EastUS/providers/microsoft. 
             insights/autoscalesettings/DefaultServerFarm-Default-Web-EastUS
Location   : East US
Name       : DefaultServerFarm-Default-Web-EastUS
Properties : 
Enabled    : True
Profiles   : 
Capacity   : 
Default    : 1
Minimum    : 3
Maximum    : 1
FixedDate     : 
Name          : No scheduled times
Recurrence    : 
Rules         : 
MetricTrigger : 
MetricName         : CpuPercentage
MetricResourceId   : /subscriptions/a93fb07c-6c93-40be-bf3b-4f0deba10f4
             b/resourceGroups/Default-Web-EastUS/providers/microsoft.web/serverFarms/DefaultServerFarm
Operator           : GreaterThanOrEqual
Statistic          : Average
Threshold          : 14
TimeAggregation    : Average
TimeGrain          : 00:01:00
TimeWindow         : 00:45:00
ScaleAction        : 
Cooldown   : 00:05:00
Direction  : Increase
Type       : ChangeCount
Value      : 1
MetricTrigger  : 
MetricName         : CpuPercentage
MetricResourceId  : /subscriptions/a93fb07c-6c93-40be-bf3b-4f0deba10f4
             b/resourceGroups/Default-Web-EastUS/providers/microsoft.web/serverFarms/DefaultServerFarm
Operator           : LessThanOrEqual
Statistic          : Average
Threshold          : 4
TimeAggregation    : Average
TimeGrain          : 00:01:00
TimeWindow         : 00:45:00
ScaleAction  : 
Cooldown   : 02:00:00
Direction  : Decrease
Type       : ChangeCount
Value      : 1

MetricTrigger  : 
MetricName         : BytesReceived
MetricResourceId  : /subscriptions/a93fb07c-6c93-40be-bf3b-4f0deba10f4
             b/resourceGroups/Default-Web-EastUS/providers/microsoft.web/serverFarms/DefaultServerFarm
Operator           : LessThanOrEqual
Statistic          : Average
Threshold          : 50
TimeAggregation    : Average
TimeGrain          : 00:01:00
TimeWindow         : 00:10:00
ScaleAction    : 
Cooldown   : 00:10:00
Direction  : Decrease
Type       : ChangeCount
Value      : 1
MetricTrigger  : 
MetricName         : BytesReceived
MetricResourceId  : /subscriptions/a93fb07c-6c93-40be-bf3b-4f0deba10f4
             b/resourceGroups/Default-Web-EastUS/providers/microsoft.web/serverFarms/DefaultServerFarm
Operator           : GreaterThanOrEqual
Statistic          : Average
Threshold          : 100
                                                TimeAggregation    : Average
TimeGrain          : 00:01:00
TimeWindow         : 00:05:00
ScaleAction    : 
Cooldown   : 00:10:00
                                                Direction  : Increase
Type       : ChangeCount
Value      : 1
             TargetResourceId : /subscriptions/b93fb07a-6f93-30be-bf3e-4f0deca15f4f/resourceGroups/Default-Web-EastUS/
             providers/microsoft.web/serverFarms/DefaultServerFarm
Tags       : {[$type, Microsoft.WindowsAzure.Management.Common.Storage.CasePreservedDictionary, 
             Microsoft.WindowsAzure.Management.Common.Storage], [hidden-link:/subscriptions/a93fb07c-6c93-40be-bf3b-4f0
             deba10f4b/resourceGroups/Default-Web-EastUS/providers/microsoft.web/serverFarms/DefaultServerFarm, 
             Resource]}
```

Perintah ini mendapatkan pengaturan Skala Otomatis yang ditetapkan ke grup sumber daya Default-Web-EastUS.

### Contoh 2: Dapatkan pengaturan Skala Otomatis menurut nama
```
PS C:\>Get-AzureRmAutoscaleSetting -ResourceGroupName "Default-Web-EastUS" -Name "DefaultServerFarm-Default-Web-EastUS" -DetailedOutput
resourceId : /subscriptions/b93fb07a-6f93-30be-bf3e-4f0deca15f4f/resourceGroups/Default-Web-EastUS/providers/microsoft. 
             insights/autoscalesettings/DefaultServerFarm-Default-Web-EastUS
Location   : East US
Name       : DefaultServerFarm-Default-Web-EastUS
Properties : 
Enabled    : True
Profiles   : 
Capacity   : 
Default    : 1
Minimum    : 3
Maximum    : 1
FixedDate     : 
Name          : No scheduled times
Recurrence    : 
Rules         : 
MetricTrigger : 
MetricName         : CpuPercentage
MetricResourceId   : /subscriptions/a93fb07c-6c93-40be-bf3b-4f0deba10f4
             b/resourceGroups/Default-Web-EastUS/providers/microsoft.web/serverFarms/DefaultServerFarm
Operator           : GreaterThanOrEqual
Statistic          : Average
Threshold          : 14
TimeAggregation    : Average
TimeGrain          : 00:01:00
TimeWindow         : 00:45:00
ScaleAction    : 
Cooldown   : 00:05:00
Direction  : Increase
Type       : ChangeCount
Value      : 1
MetricTrigger  : 
MetricName         : CpuPercentage
MetricResourceId  : /subscriptions/a93fb07c-6c93-40be-bf3b-4f0deba10f4
             b/resourceGroups/Default-Web-EastUS/providers/microsoft.web/serverFarms/DefaultServerFarm
Operator           : LessThanOrEqual
Statistic          : Average
Threshold          : 4
TimeAggregation    : Average
TimeGrain          : 00:01:00
TimeWindow         : 00:45:00
ScaleAction    : 
Cooldown   : 02:00:00
Direction  : Decrease
Type       : ChangeCount
Value      : 1
MetricTrigger  : 
MetricName         : BytesReceived
MetricResourceId  : /subscriptions/a93fb07c-6c93-40be-bf3b-4f0deba10f4
             b/resourceGroups/Default-Web-EastUS/providers/microsoft.web/serverFarms/DefaultServerFarm
Operator           : LessThanOrEqual
Statistic          : Average
Threshold          : 50
TimeAggregation    : Average
TimeGrain          : 00:01:00
TimeWindow         : 00:10:00
ScaleAction    : 
Cooldown   : 00:10:00
Direction  : Decrease
Type       : ChangeCount
Value      : 1
MetricTrigger  : 
MetricName         : BytesReceived
MetricResourceId  : /subscriptions/a93fb07c-6c93-40be-bf3b-4f0deba10f4
             b/resourceGroups/Default-Web-EastUS/providers/microsoft.web/serverFarms/DefaultServerFarm
Operator           : GreaterThanOrEqual
Statistic          : Average
Threshold          : 100
TimeAggregation    : Average
TimeGrain          : 00:01:00
TimeWindow         : 00:05:00
ScaleAction    : 
Cooldown   : 00:10:00
Direction  : Increase
Type       : ChangeCount
Value      : 1
TargetResourceId : /subscriptions/b93fb07a-6f93-30be-bf3e-4f0deca15f4f/resourceGroups/Default-Web-EastUS/
             providers/microsoft.web/serverFarms/DefaultServerFarm
Tags       : {[$type, Microsoft.WindowsAzure.Management.Common.Storage.CasePreservedDictionary, 
             Microsoft.WindowsAzure.Management.Common.Storage], [hidden-link:/subscriptions/a93fb07c-6c93-40be-bf3b-4f0
             deba10f4b/resourceGroups/Default-Web-EastUS/providers/microsoft.web/serverFarms/DefaultServerFarm, 
             Resource]}
```

Perintah ini mendapatkan pengaturan Skala Otomatis bernama DefaultServerFarm-Default-Web-EastUS.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DetailedOutput
Menunjukkan bahwa operasi ini menampilkan detail lengkap dalam output.

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

### -Nama
Menentukan nama pengaturan yang akan didapatkan.

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

### -ResourceGroupName
Menentukan nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ResourceGroup

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.Management.Automation.SwitchParameter

## OUTPUTS

### Microsoft.Azure.Commands. Insights. OutputClasses.PSAutoscaleSetting

## CATATAN

## RELATED LINKS

[Add-AzureRmAutoscaleSetting](./Add-AzureRmAutoscaleSetting.md)

[Hapus-AzureRmAutoscaleSetting](./Remove-AzureRmAutoscaleSetting.md)


