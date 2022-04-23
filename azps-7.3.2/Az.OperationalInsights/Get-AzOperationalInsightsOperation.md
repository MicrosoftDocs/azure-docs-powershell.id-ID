---
external help file: Microsoft.Azure.PowerShell.Cmdlets.OperationalInsights.dll-Help.xml
Module Name: Az.OperationalInsights
online version: https://docs.microsoft.com/powershell/module/az.operationalinsights/get-azoperationalinsightsoperation
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/OperationalInsights/OperationalInsights/help/Get-AzOperationalInsightsOperation.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/OperationalInsights/OperationalInsights/help/Get-AzOperationalInsightsOperation.md
ms.openlocfilehash: 8ec1b07fcd0e0de02bad5783d1cd2ce9b1a78c43
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143329553"
---
# Get-AzOperationalInsightsOperation

## SYNOPSIS
Mencantumkan semua operasi OperationalInsights Rest API yang tersedia.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.operationalinsights/get-azoperationalinsightsoperation) untuk informasi terbaru.

## SYNTAX

```
Get-AzOperationalInsightsOperation [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Mencantumkan semua operasi OperationalInsights Rest API yang tersedia.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Get-AzOperationalInsightsOperation
```

Nama : microsoft.operationalinsights/workspaces/features/{resource_name0}/read Provider : MicrosoftOperationalInsights Resource : {resource_name0} Operation : Deskripsi : 

Nama : microsoft.operationalinsights/workspaces/features/{resource_name0}/read Provider : MicrosoftOperationalInsights Resource : {resource_name1} Operation : Deskripsi : 

Perintah ini mendapatkan semua operasi OperationalInsights Rest API yang tersedia oleh penyewa.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### Microsoft.Azure.Commands.OperationalInsights.Models.PSOperation

## NOTES

## RELATED LINKS
