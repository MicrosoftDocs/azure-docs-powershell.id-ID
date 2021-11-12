---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: ABF5B4EB-0908-4103-B0BF-69A68A21D69C
online version: ''
schema: 2.0.0
ms.openlocfilehash: df767cfc29d1bf59486e292fc46341383ecab309
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132423181"
---
# Suspend-WAPackVM

## SYNOPSIS
Menangguhkan mesin virtual.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Suspend-WAPackVM -VM <VirtualMachine> [-PassThru] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Topik ini sudah tidak berlaku dan akan dihapus di masa mendatang.
Topik ini menguraikan cmdlet dalam versi 0.8.1 modul Microsoft Azure PowerShell.
Untuk mencari tahu versi modul yang Anda gunakan, dari konsol Azure PowerShell, ketik `(Get-Module -Name Azure).Version` .

Cmdlet **Suspend-WAPackVM** menangguhkan komputer virtual.

## EXAMPLES

### Contoh 1: Menangguhkan mesin virtual
```
PS C:\> $VirtualMachine = Get-WAPackVM -Name "ContosoV126"
PS C:\> Suspend-WAPackVM -VM $VirtualMachine
```

Perintah pertama mendapatkan mesin virtual bernama ContosoV126 dengan menggunakan cmdlet **Get-WAPackVM,** lalu menyimpan objek tersebut di $VirtualMachine variabel.

Perintah kedua menangguhkan mesin virtual yang disimpan di $VirtualMachine.

## PARAMETERS

### -PassThru
Mengembalikan objek yang mewakili item yang Anda kerjakan.
Secara default, cmdlet ini tidak menghasilkan output apa pun.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profil
Menentukan profil Azure yang akan dibaca cmdlet ini.
Jika Anda tidak menentukan profil, cmdlet ini akan membaca dari profil default lokal.

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

### -VM
Menentukan mesin virtual.
Untuk mendapatkan mesin virtual, gunakan cmdlet **Get-WAPackVM.**

```yaml
Type: VirtualMachine
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Get-WAPackvm](./Get-WAPackVM.md)

[New-WAPackvm](./New-WAPackVM.md)

[Remove-WAPackvm](./Remove-WAPackVM.md)

[Restart-WAPackvm](./Restart-WAPackVM.md)

[Resume-WAPackvm](./Resume-WAPackVM.md)

[Set-WAPackvm](./Set-WAPackVM.md)

[Start-WAPackvm](./Start-WAPackVM.md)

[Stop-WAPackvm](./Stop-WAPackVM.md)


