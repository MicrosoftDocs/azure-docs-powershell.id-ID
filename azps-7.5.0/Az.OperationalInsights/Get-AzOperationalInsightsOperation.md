---
external help file: Microsoft.Azure.PowerShell.Cmdlets.OperationalInsights.dll-Help.xml
Module Name: Az.OperationalInsights
online version: https://docs.microsoft.com/powershell/module/az.operationalinsights/get-azoperationalinsightsoperation
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/OperationalInsights/OperationalInsights/help/Get-AzOperationalInsightsOperation.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/OperationalInsights/OperationalInsights/help/Get-AzOperationalInsightsOperation.md
ms.openlocfilehash: 296539e75329e598ee463c773c25f72981661524
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145662088"
---
# Get-AzOperationalInsightsOperation

## SYNOPSIS
Mencantumkan semua operasi Rest API OperationalInsights yang tersedia.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.operationalinsights/get-azoperationalinsightsoperation) untuk informasi terbaru.

## SYNTAX

```
Get-AzOperationalInsightsOperation [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Mencantumkan semua operasi Rest API OperationalInsights yang tersedia.

## EXAMPLES

### Contoh 1
```powershell
Get-AzOperationalInsightsOperation
```

```output
Name        : microsoft.operationalinsights/workspaces/features/{resource_name0}/read
Provider    : MicrosoftOperationalInsights
Resource    : {resource_name0}
Operation   : 
Description : 

Name        : microsoft.operationalinsights/workspaces/features/{resource_name0}/read
Provider    : MicrosoftOperationalInsights
Resource    : {resource_name1}
Operation   : 
Description : 
```
Perintah ini mendapatkan semua operasi Rest API OperationalInsights yang tersedia oleh penyewa.

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

### Microsoft.Azure.Commands.OperationalInsights.Models.PSOperation

## NOTES

## RELATED LINKS
