---
external help file: Az.StackHCI-help.xml
Module Name: Az.StackHCI
online version: https://docs.microsoft.com/powershell/module/az.stackhci/get-azstackhciremotesupportsessionhistory
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StackHCI/help/Get-AzStackHCIRemoteSupportSessionHistory.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/StackHCI/help/Get-AzStackHCIRemoteSupportSessionHistory.md
ms.openlocfilehash: 92741a0ee07d229226066f72610240ebe47a6a6e
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140290921"
---
# Get-AzStackHCIRemoteSupportSessionHistory

## SYNOPSIS
Mendapatkan detail riwayat sesi dukungan jarak jauh.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.stackhci/get-azstackhciremotesupportsessionhistory) untuk informasi terkini.

## SYNTAX

```
Get-AzStackHCIRemoteSupportSessionHistory [[-SessionId] <String>] [-IncludeSessionTranscript]
 [[-FromDate] <DateTime>] [<CommonParameters>]
```

## DESCRIPTION
Riwayat sesi mewakili semua akses jarak jauh yang dibuat oleh Dukungan Microsoft untuk Diagnostik atauRepair Diagnostik berdasarkan Tingkat Akses yang diberikan.

## EXAMPLES

### CONTOH 1
```poweshell
PS C:\> Get-AzStackHCIRemoteSupportSessionHistory -SessionId 467e3234-13f4-42f2-9422-81db248930fa -IncludeSessionTranscript $true
```

## PARAMETERS

### -FromDate
Menunjukkan tanggal dari tempat memulai sesi daftar dari sampai sekarang.

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
Id Sesi untuk mendapatkan detail untuk sesi tertentu. Jika dihilangkan, mencantumkan semua sesi dimulai dari tanggal 'FromDate'.

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

## CATATAN

## RELATED LINKS
