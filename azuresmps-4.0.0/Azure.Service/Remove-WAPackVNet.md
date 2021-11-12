---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: 42042533-9F84-4189-8C9F-01FD62F89DC3
online version: ''
schema: 2.0.0
ms.openlocfilehash: 47d6799da05a6d1fd54ff4e54c999c8549b4b5da065a63c14ed5858e087a6660
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132415356"
---
# Remove-WAPackVNet

## SYNOPSIS
Menghapus objek jaringan virtual.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Remove-WAPackVNet -VNet <VMNetwork> [-PassThru] [-Force] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Topik ini sudah tidak berlaku dan akan dihapus di masa mendatang.
Topik ini menguraikan cmdlet dalam versi 0.8.1 modul Microsoft Azure PowerShell standar.
Untuk mencari tahu versi modul yang Anda gunakan, dari konsol Azure PowerShell, ketikkan `(Get-Module -Name Azure).Version` .

Cmdlet **Remove-WAPackVNet** menghapus objek jaringan virtual.

## EXAMPLES

### Contoh 1: Menghapus jaringan yang divirtualisasi
```
PS C:\> $VNet = Get-WAPackVNet -Name "ContosoVNet01"
PS C:\> Remove-WAPackVM -VNet $VNet
```

Perintah pertama mendapatkan jaringan yang divirtualisasikan bernama ContosoVNet01 dengan menggunakan cmdlet **Get-WAPackVNet,** lalu menyimpan objek tersebut di $VNet variabel.
Perintah kedua menghapus jaringan yang divirtualisasikan yang disimpan di $VNet.
Perintah akan meminta konfirmasi Anda.

### Contoh 2: Menghapus jaringan yang divirtualisasi tanpa konfirmasi
```
PS C:\> $VNet = Get-WAPackVNet -Name "ContosoVNet02"
PS C:\> Remove-WAPackVNet -VNet $VNet -Force
```

Perintah pertama mendapatkan layanan awan bernama ContosoVNet02 dengan menggunakan cmdlet **Get-WAPackVNet,** lalu menyimpan objek tersebut di $VNet variabel.
Perintah kedua menghapus jaringan yang divirtualisasikan yang disimpan di $VNet.
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

### -VNet
Menentukan jaringan yang divirtualisasikan.
Untuk mendapatkan jaringan yang divirtualisasi, gunakan cmdlet **Get-WAPackVNet.**

```yaml
Type: VMNetwork
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

[Get-WAPackvNet](./Get-WAPackVNet.md)

[New-WAPackvNet](./New-WAPackVNet.md)


