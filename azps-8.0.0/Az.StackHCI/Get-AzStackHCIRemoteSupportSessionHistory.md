---
external help file: Az.StackHCI-help.xml
Module Name: Az.StackHCI
online version: https://docs.microsoft.com/powershell/module/az.stackhci/get-azstackhciremotesupportsessionhistory
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StackHCI/help/Get-AzStackHCIRemoteSupportSessionHistory.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StackHCI/help/Get-AzStackHCIRemoteSupportSessionHistory.md
ms.openlocfilehash: 7e28c0bbd5a7b7e46a27c191d8b5f2fb1f913705
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145499110"
---
# Get-AzStackHCIRemoteSupportSessionHistory

## SYNOPSIS
Mendapatkan Detail Riwayat Sesi Dukungan Jarak Jauh.

## SYNTAX

```
Get-AzStackHCIRemoteSupportSessionHistory [[-SessionId] <String>] [-IncludeSessionTranscript]
 [[-FromDate] <DateTime>] [<CommonParameters>]
```

## DESCRIPTION
Riwayat sesi mewakili semua akses jarak jauh yang dibuat oleh Dukungan Microsoft untuk Diagnostik atau DiagnostikRepair berdasarkan Tingkat Akses yang diberikan.

## EXAMPLES

### CONTOH 1
```powershell
Get-AzStackHCIRemoteSupportSessionHistory -SessionId 467e3234-13f4-42f2-9422-81db248930fa -IncludeSessionTranscript $true
```

## PARAMETERS

### -FromDate
Menunjukkan tanggal dari mana mulai mencantumkan sesi hingga sekarang.

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncludeSessionTranscript
Menunjukkan apakah akan menyertakan transkrip sesi lengkap. Transkrip menyediakan detail tentang semua operasi yang dilakukan selama sesi.

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

### -SessionId
Id Sesi untuk mendapatkan detail untuk sesi tertentu. Jika dihilangkan, maka mencantumkan semua sesi mulai dari tanggal 'FromDate'.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: [System.String]::Empty
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS
