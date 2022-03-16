---
external help file: Microsoft.Azure.PowerShell.Cmdlets.OperationalInsights.dll-Help.xml
Module Name: Az.OperationalInsights
online version: https://docs.microsoft.com/powershell/module/az.operationalinsights/get-azoperationalinsightsoperation
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/OperationalInsights/OperationalInsights/help/Get-AzOperationalInsightsOperation.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/OperationalInsights/OperationalInsights/help/Get-AzOperationalInsightsOperation.md
ms.openlocfilehash: 8ec1b07fcd0e0de02bad5783d1cd2ce9b1a78c43
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "139952727"
---
# Get-AzOperationalInsightsOperation

## SYNOPSIS
Mencantumkan semua operasi API Rest OperationalInsights yang tersedia.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.operationalinsights/get-azoperationalinsightsoperation) untuk informasi terkini.

## SYNTAX

```
Get-AzOperationalInsightsOperation [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Mencantumkan semua operasi API Rest OperationalInsights yang tersedia.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Get-AzOperationalInsightsOperation
```

Nama : microsoft.operationalinsights/workspaces/features/{resource_name0}/read Provider : MicrosoftOperationalInsights Resource : {resource_name0} Operation : Deskripsi : 

Nama: microsoft.operationalinsights/workspaces/features/{resource_name0}/read Provider : MicrosoftOperationalInsights Resource : {resource_name1} Operation : Deskripsi : 

Perintah ini memperoleh semua operasi API Rest OperationalInsights yang tersedia menurut penyewa.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.OperationalInsights.Models.PSOperation

## CATATAN

## RELATED LINKS
