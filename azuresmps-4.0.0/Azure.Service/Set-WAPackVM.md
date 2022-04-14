---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: 08A7556E-C07F-4B3B-B9D6-B241C72860FA
online version: ''
schema: 2.0.0
ms.openlocfilehash: 695cbf0935e95070d9f8ec050da356db6772bb31
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141772173"
---
# Set-WAPackVM

## SYNOPSIS
Mengubah properti ukuran mesin virtual.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Set-WAPackVM -VM <VirtualMachine> -VMSizeProfile <HardwareProfile> [-PassThru] [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
Topik ini ditolak dan akan dihapus di masa mendatang.
Topik ini menjelaskan cmdlet dalam versi 0.8.1 modul Microsoft Azure PowerShell.
Untuk mengetahui versi modul yang Anda gunakan, dari konsol Azure PowerShell, ketik `(Get-Module -Name Azure).Version`.

Cmdlet **Set-WAPackVM** mengubah properti ukuran mesin virtual.

## EXAMPLES

### Contoh 1: Tentukan ukuran untuk mesin virtual
```
PS C:\> $VirtualMachine = Get-WAPackVM -Name "ContosoV126"
PS C:\> $SizeProfile = Get-WAPackVMSizeProfile -Name "MediumSizeVM"
PS C:\> Set-WAPackVM -VM $VirtualMachine -VMSizeProfile $SizeProfile
```

Perintah pertama mendapatkan mesin virtual bernama ContosoV126 dengan menggunakan cmdlet **Get-WAPackVM** , lalu menyimpan objek tersebut dalam variabel $VirtualMachine.

Perintah kedua mendapatkan profil ukuran bernama MediumSizeVM menggunakan cmdlet **Get-WAPackVMSizeProfile** , lalu menyimpan objek tersebut dalam variabel $SizeProfile.

Perintah akhir menetapkan profil ukuran yang disimpan di $SizeProfile ke mesin virtual yang disimpan di $VirtualMachine.

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

### -VMSizeProfile
Menentukan profil ukuran untuk mesin virtual sebagai objek **HardwareProfile** .
Untuk mendapatkan profil ukuran, gunakan cmdlet **Get-WAPackVMSizeProfile** .

```yaml
Type: HardwareProfile
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Get-WAPackVM](./Get-WAPackVM.md)

[WAPackVM Baru](./New-WAPackVM.md)

[Hapus-WAPackVM](./Remove-WAPackVM.md)

[Mulai ulang-WAPackVM](./Restart-WAPackVM.md)

[Resume-WAPackVM](./Resume-WAPackVM.md)

[Start-WAPackVM](./Start-WAPackVM.md)

[Stop-WAPackVM](./Stop-WAPackVM.md)

[Suspensi-WAPackVM](./Suspend-WAPackVM.md)

[Get-WAPackVMSizeProfile](./Get-WAPackVMSizeProfile.md)


