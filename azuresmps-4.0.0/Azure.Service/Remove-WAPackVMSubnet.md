---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: E7766E3D-D8C2-42F1-840A-8EA633E98500
online version: ''
schema: 2.0.0
ms.openlocfilehash: 28d484ffc91040c747559f4032ed547fbc406caf0057cb76c283e78d98154be4
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132415357"
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
Topik ini sudah tidak berlaku dan akan dihapus di masa mendatang.
Topik ini menguraikan cmdlet dalam versi 0.8.1 modul Microsoft Azure PowerShell ini.
Untuk mencari tahu versi modul yang Anda gunakan, dari konsol Azure PowerShell, ketikkan `(Get-Module -Name Azure).Version` .

Cmdlet **Remove-WAPackVMSubnet** menghapus objek subnet mesin virtual.

## EXAMPLES

### Contoh 1: Menghapus subnet mesin virtual
```
PS C:\> $VMSubnet = Get-WAPackVMSubnet -Name "ContosoVMSubnet01"
PS C:\> Remove-WAPackVMSubnet -VMSubnet $VMSubnet
```

Perintah pertama mendapatkan subnet mesin virtual bernama ContosoVMSubnet01 dengan menggunakan cmdlet **Get-WAPackVMSubnet,** lalu menyimpan objek tersebut di $VMSubnet variabel.

Perintah kedua menghapus subnet mesin virtual yang disimpan di $VMSubnet.
Perintah akan meminta konfirmasi Anda.

### Contoh 2: Hapus mesin virtual tanpa konfirmasi
```
PS C:\> $VMSubnet = Get-WAPackVMSubnet -Name "ContosoVMSubnet02"
PS C:\> Remove-WAPackVMSubnet -VMSubnet $VMSubnet -Force
```

Perintah pertama mendapatkan layanan awan bernama ContosoVMSubnet02 dengan menggunakan cmdlet **Get-WAPackVMSubnet,** lalu menyimpan objek tersebut dalam $VMSubnet variabel.

Perintah kedua menghapus subnet mesin virtual yang disimpan di $VMSubnet.
Perintah ini menyertakan parameter *Force.*
Perintah tidak akan meminta konfirmasi Anda.

## PARAMETERS

### -Force
Memaksa perintah untuk dijalankan tanpa meminta konfirmasi pengguna.

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

### -VMSubnet
Menentukan subnet mesin virtual.
Untuk mendapatkan subnet mesin virtual, gunakan cmdlet **Get-WAPackVMSubnet.**

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Get-WAPackvMSubnet](./Get-WAPackVMSubnet.md)

[New-WAPackvMSubnet](./New-WAPackVMSubnet.md)


