---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: 4414EA89-8573-416E-A611-DA2135E350BD
online version: ''
schema: 2.0.0
ms.openlocfilehash: 6200b5c1c2d5b9f94f811ff82c2fa347ff4f3288
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142788292"
---
# Get-WAPackStaticIPAddressPool

## SYNOPSIS
Mendapatkan objek kumpulan alamat IP statis.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### FromVMSubnetObject (Default)
```
Get-WAPackStaticIPAddressPool -VMSubnet <VMSubnet> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### FromName
```
Get-WAPackStaticIPAddressPool -VMSubnet <VMSubnet> -Name <String> [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
Topik ini ditolak dan akan dihapus di masa mendatang.
Topik ini menjelaskan cmdlet dalam versi 0.8.1 modul Microsoft Azure PowerShell.
Untuk mengetahui versi modul yang Anda gunakan, dari konsol Azure PowerShell, ketik `(Get-Module -Name Azure).Version`.

**Cmdlet Get-WAPackStaticIPAddressPool** mendapatkan objek pool alamat IP statis.

## EXAMPLES

### Contoh 1: Dapatkan kumpulan alamat IP statis dari VMSubnet tertentu
```
PS C:\> $Subnet = Get-WAPackVMSubet -Name "ContosoVMSubnet01"
PS C:\> Get-WAPackStaticIPAddressPool -VMSubnet $Subnet -Name "ContosoStaticIPAddressPool01"
```

Perintah ini mendapatkan kumpulan alamat IP statis bernama ContosoStaticIPAddressPool01 dari VMSubnet tertentu.

### Contoh 2: Dapatkan semua kumpulan alamat IP statis dari VMSubnet tertentu
```
PS C:\> $Subnet = Get-WAPackVMSubet -Name "ContosoVMSubnet01"
PS C:\> Get-WAPackStaticIPAddressPool -VMSubnet $Subnet
```

Perintah ini mendapatkan semua kumpulan IP statis dari VMSubet tertentu.

## PARAMETERS

### -Nama
Menentukan nama kumpulan alamat IP statis.

```yaml
Type: String
Parameter Sets: FromName
Aliases:

Required: True
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
Menentukan objek **VMSubnet** yang terkait dengan kumpulan alamat IP statis.

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

## NOTES

## RELATED LINKS

[New-WAPackStaticIPAddressPool](./New-WAPackStaticIPAddressPool.md)

[Remove-WAPackStaticIPAddressPool](./Remove-WAPackStaticIPAddressPool.md)


