---
external help file: Az.StackHCI-help.xml
Module Name: Az.StackHCI
online version: https://docs.microsoft.com/powershell/module/az.stackhci/get-azstackhciremotesupportsessionhistory
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StackHCI/help/Get-AzStackHCIRemoteSupportSessionHistory.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StackHCI/help/Get-AzStackHCIRemoteSupportSessionHistory.md
ms.openlocfilehash: 92741a0ee07d229226066f72610240ebe47a6a6e
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143131589"
---
# Get-AzStackHCIRemoteSupportSessionHistory

## SYNOPSIS
Mendapatkan Detail Riwayat Sesi Dukungan Jarak Jauh.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.stackhci/get-azstackhciremotesupportsessionhistory) untuk informasi terbaru.

## SYNTAX

```
Get-AzStackHCIRemoteSupportSessionHistory [[-SessionId] <String>] [-IncludeSessionTranscript]
 [[-FromDate] <DateTime>] [<CommonParameters>]
```

## DESCRIPTION
Riwayat sesi mewakili semua akses jarak jauh yang dibuat oleh Dukungan Microsoft baik untuk Diagnostik atau DiagnostikRepair berdasarkan Tingkat Akses yang diberikan.

## EXAMPLES

### CONTOH 1
```poweshell
PS C:\> Get-AzStackHCIRemoteSupportSessionHistory -SessionId 467e3234-13f4-42f2-9422-81db248930fa -IncludeSessionTranscript $true
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
Session Id untuk mendapatkan detail sesi tertentu. Jika dihilangkan, maka daftar semua sesi dimulai dari tanggal 'FromDate'.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS
