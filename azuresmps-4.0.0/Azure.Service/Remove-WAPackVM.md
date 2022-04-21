---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: D04D79CE-F183-4A8D-B925-F640D89377BD
online version: ''
schema: 2.0.0
ms.openlocfilehash: f0c0c587cb51add04bd4c60764f836eea7f2ac8b
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142787491"
---
# Remove-WAPackVM

## SYNOPSIS
Menghapus objek mesin virtual.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Remove-WAPackVM -VM <VirtualMachine> [-PassThru] [-Force] [-Profile <AzureSMProfile>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Topik ini ditolak dan akan dihapus di masa mendatang.
Topik ini menjelaskan cmdlet dalam versi 0.8.1 modul Microsoft Azure PowerShell.
Untuk mengetahui versi modul yang Anda gunakan, dari konsol Azure PowerShell, ketik `(Get-Module -Name Azure).Version`.

Cmdlet **Remove-WAPackVM** menghapus objek mesin virtual.

## EXAMPLES

### Contoh 1: Hapus mesin virtual
```
PS C:\> $VirtualMachine = Get-WAPackVM -Name "ContosoV126"
PS C:\> Remove-WAPackVM -VM $VirtualMachine
```

Perintah pertama mendapatkan mesin virtual bernama ContosoV126 dengan menggunakan cmdlet **Get-WAPackVM** , lalu menyimpan objek tersebut dalam variabel $VirtualMachine.

Perintah kedua menghapus mesin virtual yang disimpan di $VirtualMachine.
Perintah meminta konfirmasi kepada Anda.

### Contoh 2: Hapus mesin virtual tanpa konfirmasi
```
PS C:\> $VirtualMachine = Get-WAPackVM -Name "ContosoV126"
PS C:\> Remove-WAPackVM -VM $VirtualMachine -Force
```

Perintah pertama mendapatkan mesin virtual bernama ContosoV126 dengan menggunakan cmdlet **Get-WAPackVM** , lalu menyimpan objek tersebut dalam variabel $VirtualMachine.

Perintah kedua menghapus mesin virtual yang disimpan di $VirtualMachine.
Perintah ini menyertakan parameter *Paksa* .
Perintah tidak meminta konfirmasi kepada Anda.

## PARAMETERS

### -Paksa
Menunjukkan bahwa cmdlet menghapus mesin virtual tanpa meminta konfirmasi kepada Anda.

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

### -PassThru
Menunjukkan bahwa cmdlet mengembalikan nilai Boolean.
Jika operasi berhasil, cmdlet mengembalikan nilai $True.
Jika tidak, mengembalikan nilai $False.
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

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak dijalankan.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
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

[Mulai ulang-WAPackVM](./Restart-WAPackVM.md)

[Resume-WAPackVM](./Resume-WAPackVM.md)

[Set-WAPackVM](./Set-WAPackVM.md)

[Start-WAPackVM](./Start-WAPackVM.md)

[Stop-WAPackVM](./Stop-WAPackVM.md)

[Suspensi-WAPackVM](./Suspend-WAPackVM.md)


