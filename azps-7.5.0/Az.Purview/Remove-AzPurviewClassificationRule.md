---
external help file: Az.Purview-help.xml
Module Name: Az.Purview
online version: https://docs.microsoft.com/powershell/module/az.purview/remove-azpurviewclassificationrule
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/Remove-AzPurviewClassificationRule.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/Remove-AzPurviewClassificationRule.md
ms.openlocfilehash: 966f6a29306a7fd0bfc3d61f0667f313fe690014
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144111560"
---
# Remove-AzPurviewClassificationRule

## SYNOPSIS
Menghapus aturan klasifikasi

## SYNTAX

```
Remove-AzPurviewClassificationRule -Endpoint <String> -Name <String> [-DefaultProfile <PSObject>] [-PassThru]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Menghapus aturan klasifikasi

## EXAMPLES

### Contoh 1: Menghapus aturan klasifikasi kustom menurut nama
```powershell
PS C:\> Remove-AzPurviewClassificationRule -Endpoint https://parv-brs-2.purview.azure.com -ClassificationRuleName 'RuleDUmmy'

ClassificationAction   : Keep
ClassificationName     : MICROSOFT.GOVERNMENT.AUSTRALIA.DRIVERS_LICENSE_NUMBER
ColumnPattern          : {{
                           "kind": "Regex",
                           "pattern": "Column1"
                         }, {
                           "kind": "Regex",
                           "pattern": "Column2"
                         }}
CreatedAt              : 2/3/2022 11:28:58 AM
DataPattern            : {}
Description            : Description
Id                     : classificationrules/RuleDUmmy
Kind                   : Custom
LastModifiedAt         : 2/3/2022 11:28:58 AM
MinimumPercentageMatch :
Name                   : RuleDUmmy
RuleStatus             : Enabled
Version                : 1
```

Menghapus aturan klasifikasi kustom bernama 'ClassificationRule4'

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
Parameter Sets: (All)
Aliases: ClassificationRuleName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Mengembalikan true ketika perintah berhasil

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
Cmdlet tidak dijalankan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
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
