---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: 80820C11-92BB-4E75-8722-496CF21C779E
online version: ''
schema: 2.0.0
ms.openlocfilehash: 039e4186be648fd3faeafe729a1a42fffb29f261
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142915967"
---
# Restart-WAPackVM

## SYNOPSIS
Memulai ulang mesin virtual.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Restart-WAPackVM -VM <VirtualMachine> [-PassThru] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Topik ini ditolak dan akan dihapus di masa mendatang.
Topik ini menjelaskan cmdlet dalam versi 0.8.1 modul Microsoft Azure PowerShell.
Untuk mengetahui versi modul yang Anda gunakan, dari konsol Azure PowerShell, ketik `(Get-Module -Name Azure).Version`.

Cmdlet **Restart-WAPackVM** memulai ulang mesin virtual.

## EXAMPLES

### Contoh 1: Memulai ulang mesin virtual
```
PS C:\> $VirtualMachine = Get-WAPackVM -Name "ContosoV126"
PS C:\> Restart-WAPackVM -VM $VirtualMachine
```

Perintah pertama mendapatkan mesin virtual bernama ContosoV126 dengan menggunakan cmdlet **Get-WAPackVM** , lalu menyimpan objek tersebut dalam variabel $VirtualMachine.

Perintah kedua memulai ulang mesin virtual yang disimpan di $VirtualMachine.

## PARAMETERS

### -PassThru
Mengembalikan objek yang mewakili item tempat Anda bekerja.
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

### -VM
Menentukan mesin virtual.
Untuk mendapatkan mesin virtual, gunakan cmdlet **Get-WAPackVM** .

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-WAPackVM](./Get-WAPackVM.md)

[WAPackVM Baru](./New-WAPackVM.md)

[Hapus-WAPackVM](./Remove-WAPackVM.md)

[Resume-WAPackVM](./Resume-WAPackVM.md)

[Set-WAPackVM](./Set-WAPackVM.md)

[Start-WAPackVM](./Start-WAPackVM.md)

[Stop-WAPackVM](./Stop-WAPackVM.md)

[Suspensi-WAPackVM](./Suspend-WAPackVM.md)


