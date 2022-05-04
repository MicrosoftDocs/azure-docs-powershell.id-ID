---
external help file: Az.StackHCI-help.xml
Module Name: Az.StackHCI
online version: https://docs.microsoft.com/powershell/module/az.stackhci/get-azstackhciremotesupportaccess
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StackHCI/help/Get-AzStackHCIRemoteSupportAccess.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StackHCI/help/Get-AzStackHCIRemoteSupportAccess.md
ms.openlocfilehash: 322e919b9bb7e29db8a79aef208307b51992d039
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144666718"
---
# Get-AzStackHCIRemoteSupportAccess

## SYNOPSIS
Mendapatkan Akses Dukungan Jarak Jauh.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.stackhci/get-azstackhciremotesupportaccess) untuk informasi terbaru.

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
