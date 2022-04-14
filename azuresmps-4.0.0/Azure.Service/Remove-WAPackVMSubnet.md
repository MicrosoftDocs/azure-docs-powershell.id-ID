---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: E7766E3D-D8C2-42F1-840A-8EA633E98500
online version: ''
schema: 2.0.0
ms.openlocfilehash: 42f5ff8bfe5c95572489c358686f61763c5106fc
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142093535"
---
# Remove-WAPackVMSubnet

## SYNOPSIS
Menghapus objek subnet mesin virtual.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Remove-WAPackVMSubnet -VMSubnet <VMSubnet> [-PassThru] [-Force] [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
Topik ini ditolak dan akan dihapus di masa mendatang.
Topik ini menjelaskan cmdlet dalam versi 0.8.1 modul Microsoft Azure PowerShell.
Untuk mengetahui versi modul yang Anda gunakan, dari konsol Azure PowerShell, ketik `(Get-Module -Name Azure).Version`.

Cmdlet **Remove-WAPackVMSubnet** menghapus objek subnet mesin virtual.

## EXAMPLES

### Contoh 1: Menghapus subnet mesin virtual
```
PS C:\> $VMSubnet = Get-WAPackVMSubnet -Name "ContosoVMSubnet01"
PS C:\> Remove-WAPackVMSubnet -VMSubnet $VMSubnet
```

Perintah pertama mendapatkan subnet mesin virtual bernama ContosoVMSubnet01 dengan menggunakan cmdlet **Get-WAPackVMSubnet** , lalu menyimpan objek tersebut dalam variabel $VMSubnet.

Perintah kedua menghapus subnet mesin virtual yang disimpan di $VMSubnet.
Perintah meminta konfirmasi kepada Anda.

### Contoh 2: Hapus mesin virtual tanpa konfirmasi
```
PS C:\> $VMSubnet = Get-WAPackVMSubnet -Name "ContosoVMSubnet02"
PS C:\> Remove-WAPackVMSubnet -VMSubnet $VMSubnet -Force
```

Perintah pertama mendapatkan layanan cloud bernama ContosoVMSubnet02 dengan menggunakan cmdlet **Get-WAPackVMSubnet** , lalu menyimpan objek tersebut dalam variabel $VMSubnet.

Perintah kedua menghapus subnet mesin virtual yang disimpan di $VMSubnet.
Perintah ini menyertakan parameter *Paksa* .
Perintah tidak meminta konfirmasi kepada Anda.

## PARAMETERS

### -Paksa
Memaksa perintah untuk berjalan tanpa meminta konfirmasi pengguna.

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

### -VMSubnet
Menentukan subnet mesin virtual.
Untuk mendapatkan subnet mesin virtual, gunakan cmdlet **Get-WAPackVMSubnet** .

```yaml
Type: VMSubnet
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

## CATATAN

## RELATED LINKS

[Get-WAPackVMSubnet](./Get-WAPackVMSubnet.md)

[New-WAPackVMSubnet](./New-WAPackVMSubnet.md)


