---
external help file: Az.Purview-help.xml
Module Name: Az.Purview
online version: https://docs.microsoft.com/powershell/module/az.purview/get-azpurviewscanruleset
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/Get-AzPurviewScanRuleset.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Purview/Purview/help/Get-AzPurviewScanRuleset.md
ms.openlocfilehash: 6cc7f9bc2dccdf33a2f61276d580abc8bb169a20
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145656490"
---
# Get-AzPurviewScanRuleset

## SYNOPSIS
Mendapatkan set aturan pemindaian

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.purview/get-azpurviewscanruleset) untuk informasi terbaru.

## SYNTAX

### Daftar (Default)
```
Get-AzPurviewScanRuleset -Endpoint <String> [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Dapatkan
```
Get-AzPurviewScanRuleset -Endpoint <String> -Name <String> [-DefaultProfile <PSObject>] [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan set aturan pemindaian

## EXAMPLES

### Contoh 1: Mendapatkan semua scanruleset kustom
```powershell
PS C:\> Get-AzPurviewScanRuleset -Endpoint https://parv-brs-2.purview.azure.com/

CreatedAt                            : 1/25/2022 2:01:38 AM
Description                          : asdasd
ExcludedSystemClassification         : {MICROSOFT.GOVERNMENT.CYPRUS.TAX.IDENTIFICATION.NUMBER, MICROSOFT.GOVERNMENT.CHILE.CDI_NUMBER, MICROSOFT.GOVERNMENT.MALTA.DRIVERS.LICENSE.NUMBER,
                                       MICROSOFT.GOVERNMENT.TURKEY.TURKISH_NATIONAL_IDENTIFICATION_NUMBER…}
Id                                   : scanrulesets/DummySRSFOrDemo
IncludedCustomClassificationRuleName : {}
Kind                                 : AzureStorage
LastModifiedAt                       : 1/27/2022 4:37:15 AM
Name                                 : DummySRSFOrDemo
ScanningRuleCustomFileExtension      :
ScanningRuleFileExtension            : {CSV, JSON, PSV, SSV…}
Status                               : Enabled
Type                                 : Custom
Version                              : 4

CreatedAt                            : 2/17/2022 2:30:15 PM
Description                          : test desc
ExcludedSystemClassification         : {MICROSOFT.FINANCIAL.CREDIT_CARD_NUMBER, MICROSOFT.SECURITY.COMMON_PASSWORDS, MICROSOFT.MISCELLANEOUS.IPADDRESS}
Id                                   : scanrulesets/TestRule
IncludedCustomClassificationRuleName : {ClassificationRule5, ClassificationRule2}
Kind                                 : AzureStorage
LastModifiedAt                       : 2/17/2022 2:32:02 PM
Name                                 : TestRule
ScanningRuleCustomFileExtension      :
ScanningRuleFileExtension            : {CSV, JSON, PSV, SSV…}
Status                               : Enabled
Type                                 : Custom
Version                              : 2
```

Mendapatkan semua scanruleset kustom

### Contoh 2: Dapatkan scanruleset kustom berdasarkan nama
```powershell
PS C:\> Get-AzPurviewScanRuleset -Endpoint https://parv-brs-2.purview.azure.com/ -Name TestRule

CreatedAt                            : 2/17/2022 2:30:15 PM
Description                          : test desc
ExcludedSystemClassification         : {MICROSOFT.FINANCIAL.CREDIT_CARD_NUMBER, MICROSOFT.SECURITY.COMMON_PASSWORDS, MICROSOFT.MISCELLANEOUS.IPADDRESS}
Id                                   : scanrulesets/TestRule
IncludedCustomClassificationRuleName : {ClassificationRule5, ClassificationRule2}
Kind                                 : AzureStorage
LastModifiedAt                       : 2/17/2022 2:32:02 PM
Name                                 : TestRule
ScanningRuleCustomFileExtension      :
ScanningRuleFileExtension            : {CSV, JSON, PSV, SSV…}
Status                               : Enabled
Type                                 : Custom
Version                              : 2
```

Dapatkan scanruleset kustom berdasarkan nama

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
Aliases: ScanRulesetName

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

### Microsoft.Azure.PowerShell.Cmdlets.Purviewdata.Models.Api20211001Preview.IScanRuleset

## NOTES

ALIAS

## RELATED LINKS
