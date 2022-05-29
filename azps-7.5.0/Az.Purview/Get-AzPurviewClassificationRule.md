---
external help file: Az.Purview-help.xml
Module Name: Az.Purview
online version: https://docs.microsoft.com/powershell/module/az.purview/get-azpurviewclassificationrule
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/Get-AzPurviewClassificationRule.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/Get-AzPurviewClassificationRule.md
ms.openlocfilehash: 2001f3f2383819c4642377f2d7bfbc6305bd75a5
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145656616"
---
# Get-AzPurviewClassificationRule

## SYNOPSIS
Mendapatkan aturan klasifikasi

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.purview/get-azpurviewclassificationrule) untuk informasi terbaru.

## SYNTAX

### Daftar (Default)
```
Get-AzPurviewClassificationRule -Endpoint <String> [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Dapatkan
```
Get-AzPurviewClassificationRule -Endpoint <String> -Name <String> [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan aturan klasifikasi

## EXAMPLES

### Contoh 1: Mendapatkan aturan klasifikasi kustom berdasarkan nama
```powershell
PS C:\> Get-AzPurviewClassificationRule -Endpoint https://parv-brs-2.purview.azure.com/ -Name ClassificationRule1

ClassificationAction   : Keep
ClassificationName     : ClassificationName1
ColumnPattern          : {{
                           "kind": "Regex",
                           "pattern": "column1"
                         }}
CreatedAt              : 1/27/2022 4:36:25 AM
DataPattern            : {{
                           "kind": "Regex",
                           "pattern": "^\\d{5}$"
                         }}
Description            : This is a description
Id                     : classificationrules/ClassificationRule1
Kind                   : Custom
LastModifiedAt         : 1/27/2022 4:36:25 AM
MinimumPercentageMatch : 60
Name                   : ClassificationRule1
RuleStatus             : Enabled
Version                : 1
```

Mendapatkan aturan klasifikasi bernama Klasifikasi1

### Contoh 2: Mendapatkan semua aturan klasifikasi kustom
```powershell
PS C:\> Get-AzPurviewClassificationRule -Endpoint https://parv-brs-2.purview.azure.com/

ClassificationAction   : Keep
ClassificationName     : ClassificationName1
ColumnPattern          : {{
                           "kind": "Regex",
                           "pattern": "column1"
                         }}
CreatedAt              : 1/27/2022 4:36:25 AM
DataPattern            : {{
                           "kind": "Regex",
                           "pattern": "^\\d{5}$"
                         }}
Description            : This is a description
Id                     : classificationrules/ClassificationRule1
Kind                   : Custom
LastModifiedAt         : 1/27/2022 4:36:25 AM
MinimumPercentageMatch : 60
Name                   : ClassificationRule1
RuleStatus             : Enabled
Version                : 1

ClassificationAction   : Keep
ClassificationName     : ClassificationName2
ColumnPattern          : {{
                           "kind": "Regex",
                           "pattern": "column2"
                         }}
CreatedAt              : 1/27/2022 4:37:09 AM
DataPattern            : {{
                           "kind": "Regex",
                           "pattern": "^\\d{6}$"
                         }}
Description            : This is description
Id                     : classificationrules/ClassificationRule2
Kind                   : Custom
LastModifiedAt         : 1/27/2022 4:37:09 AM
MinimumPercentageMatch : 60
Name                   : ClassificationRule2
RuleStatus             : Enabled
Version                : 1
```

Mendapatkan semua aturan klasifikasi kustom

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

### -Titik akhir
Titik akhir pemindaian akun purview Anda.
Contoh: https://{accountName}.purview.azure.com

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

### -Name
.

```yaml
Type: System.String
Parameter Sets: Get
Aliases: ClassificationRuleName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Purviewdata.Models.Api20211001Preview.IClassificationRule

## NOTES

ALIAS

## RELATED LINKS
