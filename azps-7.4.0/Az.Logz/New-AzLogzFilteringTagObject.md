---
external help file: ''
Module Name: Az.Logz
online version: https://docs.microsoft.com/powershell/module/az.Logz/new-AzLogzFilteringTagObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Logz/help/New-AzLogzFilteringTagObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Logz/help/New-AzLogzFilteringTagObject.md
ms.openlocfilehash: 3a7489a58793343d6e1efca12ad5edc23812dbe8
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141996618"
---
# New-AzLogzFilteringTagObject

## SYNOPSIS
Membuat objek dalam memori untuk FilteringTag

## SYNTAX

```
New-AzLogzFilteringTagObject [-Action <TagAction>] [-Name <String>] [-Value <String>] [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk FilteringTag

## EXAMPLES

### Contoh 1: Membuat objek dalam memori untuk FilteringTag masuk ke parameter LogRuleFilteringTag saat membuat aturan tage untuk sumber daya monitor
```powershell
$filter = New-AzLogzFilteringTagObject -Action 'Include' -Name 'Env' -Value "Prod"
New-AzLogzMonitorTagRule -ResourceGroupName logz-rg-test -MonitorName pwsh-logz04 -LogRuleFilteringTag $filter
```

```output
Name    ProvisioningState ResourceGroupName
----    ----------------- -----------------
default Succeeded         logz-rg-test
```

Perintah ini membuat objek dalam memori untuk filteringTag masuk ke parameter LogRuleFilteringTag saat membuat aturan tage untuk sumber daya monitor.

## PARAMETERS

### -Tindakan
Tindakan valid untuk tag pemfilteran.
Pengecualian lebih diprioritaskan daripada penyertaan.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Logz.Support.TagAction
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama (juga dikenal sebagai kunci) tag.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Value
Nilai tag.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Logz.Models.Api20201001Preview.FilteringTag

## CATATAN

ALIAS

## RELATED LINKS

