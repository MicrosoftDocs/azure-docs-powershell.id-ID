---
external help file: Az.Purview-help.xml
Module Name: Az.Purview
online version: https://docs.microsoft.com/powershell/module/az.purview/get-azpurviewsystemscanrulesetlatest
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/Get-AzPurviewSystemScanRulesetLatest.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/Get-AzPurviewSystemScanRulesetLatest.md
ms.openlocfilehash: c7c67870864e2f306dc10d48209f6e855a72b130
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145656346"
---
# Get-AzPurviewSystemScanRulesetLatest

## SYNOPSIS
Mendapatkan versi terbaru dari set aturan pemindaian sistem

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.purview/get-azpurviewsystemscanrulesetlatest) untuk informasi terbaru.

## SYNTAX

```
Get-AzPurviewSystemScanRulesetLatest -Endpoint <String> [-DataSourceType <DataSourceType>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan versi terbaru dari set aturan pemindaian sistem

## EXAMPLES

### Contoh 1: Dapatkan set aturan pemindaian sistem terbaru yang tersedia untuk sumber data
```powershell
PS C:\> Get-AzPurviewSystemScanRulesetLatest -Endpoint https://parv-brs-2.purview.azure.com/ -DataSourceType 'AzureStorage'

Id                : systemscanrulesets/AzureStorage
Kind              : AzureStorage
Name              : AzureStorage
ResourceGroupName :
Status            : Enabled
Type              : System
Version           : 4
```

Mendapatkan aturan pemindaian sistem terbaru yang tersedia untuk sumber data

## PARAMETERS

### -DataSourceType
.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Purviewdata.Support.DataSourceType
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Purviewdata.Models.Api20211001Preview.ISystemScanRuleset

## NOTES

ALIAS

## RELATED LINKS
