---
external help file: Az.StackHCI-help.xml
Module Name: Az.StackHCI
online version: https://docs.microsoft.com/powershell/module/az.stackhci/get-azstackhciremotesupportaccess
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StackHCI/help/Get-AzStackHCIRemoteSupportAccess.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StackHCI/help/Get-AzStackHCIRemoteSupportAccess.md
ms.openlocfilehash: 1eff9634c0e9045871519fc7215b6fff0729e1d2
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144193975"
---
# Get-AzStackHCIRemoteSupportAccess

## SYNOPSIS
Mendapatkan Akses Dukungan Jarak Jauh.

## SYNTAX

```
Get-AzStackHCIRemoteSupportAccess [-Cluster] [-IncludeExpired] [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan akses dukungan jarak jauh.

## EXAMPLES

### CONTOH 1
```powershell
Get-AzStackHCIRemoteSupportAccess -Cluster
```

### CONTOH 2
```powershell
Get-AzStackHCIRemoteSupportAccess -Cluster -IncludeExpired
```

## PARAMETERS

### -Cluster
Menunjukkan apakah akan menampilkan sesi dukungan jarak jauh di seluruh kluster.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncludeExpired
Menunjukkan apakah akan menyertakan entri kedaluwarsa sebelumnya.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS
