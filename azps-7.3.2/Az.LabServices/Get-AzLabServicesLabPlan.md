---
external help file: ''
Module Name: Az.LabServices
online version: https://docs.microsoft.com/powershell/module/az.labservices/get-azlabserviceslabplan
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/LabServices/help/Get-AzLabServicesLabPlan.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/LabServices/help/Get-AzLabServicesLabPlan.md
ms.openlocfilehash: 8df6c3a7144c5a7130e6a99d641a82534a506b3f
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140402231"
---
# Get-AzLabServicesLabPlan

## SYNOPSIS
Mengambil properti Rencana Lab.

## SYNTAX

### Daftar (Default)
```
Get-AzLabServicesLabPlan [-SubscriptionId <String[]>] [-Filter <String>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### Dapatkan
```
Get-AzLabServicesLabPlan -Name <String> -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Daftar1
```
Get-AzLabServicesLabPlan -ResourceGroupName <String> [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### ListByLabPlanName
```
Get-AzLabServicesLabPlan -Name <String> [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### ResourceId
```
Get-AzLabServicesLabPlan -ResourceId <String> [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Mengambil properti Rencana Lab.

## EXAMPLES

### Contoh 1: Get all lab plans in subscription.
```powershell
PS C:\> Get-AzLabServicesLabPlan

Location      Name                          Type
--------      ----                          ----
westus2       plan1                         Microsoft.LabServices/labPlans
westus2       plan2                         Microsoft.LabServices/labPlans
westus2       plan3                         Microsoft.LabServices/labPlans

```

Mengembalikan semua rencana lab dalam sebuah langganan.

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

### -Filter
Filter yang akan diterapkan ke operasi.

```yaml
Type: System.String
Parameter Sets: List
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama rencana lab yang mengidentifikasinya secara unik di dalam grup sumber daya.
Digunakan dalam URI sumber daya dan dalam UI.

```yaml
Type: System.String
Parameter Sets: Get, ListByLabPlanName
Aliases: LabPlanName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### -ResourceGroupName
Nama grup sumber daya.
Namanya peka huruf besar/huruf.

```yaml
Type: System.String
Parameter Sets: Get, List1
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId


```yaml
Type: System.String
Parameter Sets: ResourceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### System.String

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.LabServices.Models.Api20211001Preview.ILabPlan

## CATATAN

ALIAS

## RELATED LINKS

