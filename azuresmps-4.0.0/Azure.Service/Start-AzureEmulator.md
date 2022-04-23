---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: A1815E7F-720E-4526-A779-106C181B840D
online version: ''
schema: 2.0.0
ms.openlocfilehash: 6ea07264ac9b09d90e6445f2062ea69292507328
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143102843"
---
# Start-AzureEmulator

## SYNOPSIS
Memulai emulator komputasi dan penyimpanan.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Start-AzureEmulator [-Launch] [-Mode <ComputeEmulatorMode>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Topik ini menjelaskan cmdlet dalam versi 0.8.10 modul Microsoft Azure PowerShell.
Untuk mendapatkan versi modul yang Anda gunakan, di konsol Azure PowerShell, ketik .`(Get-Module -Name Azure).Version`

Cmdlet **Start-AzureEmulator** memulai emulator komputasi dan penyimpanan dan menghosting layanan saat ini di emulator komputasi.

## EXAMPLES

### Contoh 1: Mulai emulator dan luncurkan browser
```
PS C:\> Start-AzureEmulator -L
```

Contoh ini menjalankan layanan di emulator Azure dan meluncurkan jendela browser baru pada layanan yang ditiru.

## PARAMETERS

### -Luncurkan
Membuka jendela browser baru di layanan setelah menghostingnya di emulator.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: ln

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Mode
Menentukan mode emulator.
Nilai yang valid adalah: Full dan Express.
Nilai defaultnya adalah Express.

```yaml
Type: ComputeEmulatorMode
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profil
Menentukan profil Azure tempat cmdlet ini dibaca.
Jika Anda tidak menentukan profil, cmdlet ini akan dibaca dari profil default lokal.

```yaml
Type: AzureSMProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[New-AzureServiceProject](./New-AzureServiceProject.md)

[Publish-AzureServiceProject](./Publish-AzureServiceProject.md)

[Stop-AzureEmulator](./Stop-AzureEmulator.md)


