---
external help file: ''
Module Name: Az.Logz
online version: https://docs.microsoft.com/powershell/module/az.Logz/new-AzLogzFilteringTagObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Logz/help/New-AzLogzFilteringTagObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Logz/help/New-AzLogzFilteringTagObject.md
ms.openlocfilehash: 3a7489a58793343d6e1efca12ad5edc23812dbe8
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144213503"
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

### Contoh 1: Buat objek dalam memori untuk FilteringTag yang diteruskan ke parameter LogRuleFilteringTag saat membuat aturan tage untuk sumber daya monitor
```powershell
$filter = New-AzLogzFilteringTagObject -Action 'Include' -Name 'Env' -Value "Prod"
New-AzLogzMonitorTagRule -ResourceGroupName logz-rg-test -MonitorName pwsh-logz04 -LogRuleFilteringTag $filter
```

```output
Name    ProvisioningState ResourceGroupName
----    ----------------- -----------------
default Succeeded         logz-rg-test
```

Perintah ini membuat objek dalam memori untuk FilteringTag yang diteruskan ke parameter LogRuleFilteringTag saat membuat aturan tage untuk sumber daya monitor.

## PARAMETERS

### -Tindakan
Tindakan yang valid untuk tag pemfilteran.
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

### -Name
Nama (juga dikenal sebagai kunci) dari tag.

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

### -Nilai
Nilai dari tag.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Logz.Models.Api20201001Preview.FilteringTag

## NOTES

ALIAS

## RELATED LINKS

