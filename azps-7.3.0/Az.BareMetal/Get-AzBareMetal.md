---
external help file: ''
Module Name: Az.BareMetal
online version: https://docs.microsoft.com/powershell/module/az.baremetal/get-azbaremetal
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/BareMetal/help/Get-AzBareMetal.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/BareMetal/help/Get-AzBareMetal.md
ms.openlocfilehash: 24fd87cceb5d2527707d7ea9a65d4a8d69296e3f
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140181995"
---
# Get-AzBareMetal

## SYNOPSIS
Mendapatkan instans Azure BareMetal untuk langganan, grup sumber daya, dan nama instans yang ditentukan.

## SYNTAX

### Daftar (Default)
```
Get-AzBareMetal [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Dapatkan
```
Get-AzBareMetal -Name <String> -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Daftar1
```
Get-AzBareMetal -ResourceGroupName <String> [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan instans Azure BareMetal untuk langganan, grup sumber daya, dan nama instans yang ditentukan.

## EXAMPLES

### Contoh 1: Daftar
```powershell
PS C:\> Get-AzBareMetal

Location       Name         ResourceGroupName
--------       ----         -----------------
westus2        rhel79ora01  MWH03A-T210
westus2        rhel79ora02  MWH03A-T210
southcentralus oelnvmetest  SAT09A-T230
centraluseuap  orcllabdsm01 DSM05A-T030
```

Mendapatkan instans Azure BareMetal.

### Contoh 2: Dapatkan
```powershell
PS C:\> Get-AzBareMetal -Name oelnvmetest -ResourceGroupName SAT09A-T230

Location       Name         ResourceGroupName
--------       ----         -----------------
southcentralus oelnvmetest  SAT09A-T230
```

Mendapatkan instans Azure BareMetal untuk langganan, grup sumber daya, dan nama instans yang ditentukan.

### Contoh 3: Daftar1
```powershell
PS C:\> Get-AzBareMetal -ResourceGroupName MWH03A-T210

Location Name        ResourceGroupName
-------- ----        -----------------
westus2  rhel79ora01 MWH03A-T210
westus2  rhel79ora02 MWH03A-T210
```

Mendapatkan contoh Azure BareMetal untuk grup sumber daya.

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
Nama Azure BareMetal pada instans Azure.

```yaml
Type: System.String
Parameter Sets: Get
Aliases: AzureBareMetalInstanceName

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
Parameter Sets: Get, List1
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

### Microsoft.Azure.PowerShell.Cmdlets.BareMetal.Models.Api20210809.IAzureBareMetalInstance

## CATATAN

ALIAS

## RELATED LINKS

