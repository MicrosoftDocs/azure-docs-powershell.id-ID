---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: 0E358CEF-69E4-4639-918C-CE593E97B189
online version: ''
schema: 2.0.0
ms.openlocfilehash: 21e7df1cf64f97e59a3032709609c44bfb1869ed
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132422926"
---
# Get-WAPackVMSubnet

## SYNOPSIS
Mendapatkan objek subnet mesin virtual.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### FromVMNetworkObject (Default)
```
Get-WAPackVMSubnet -VNet <VMNetwork> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### FromName
```
Get-WAPackVMSubnet -VNet <VMNetwork> -Name <String> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### FromId
```
Get-WAPackVMSubnet -VNet <VMNetwork> -ID <Guid> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Topik ini sudah tidak berlaku dan akan dihapus di masa mendatang.
Topik ini menguraikan cmdlet dalam versi 0.8.1 modul Microsoft Azure PowerShell ini.
Untuk mencari tahu versi modul yang Anda gunakan, dari konsol Azure PowerShell, ketikkan `(Get-Module -Name Azure).Version` .

Cmdlet **Get-WAPackVMSubnet** mendapatkan objek subnet mesin virtual.

## EXAMPLES

### Contoh 1: Mendapatkan subnet mesin virtual menggunakan nama
```
PS C:\> $VNet = Get-WAPackVNet -Name "ContosoVNet01"
PS C:\> Get-WAPackVMTemplate -VNet $VNet -Name "ContosoSubnet01"
```

Perintah ini mendapatkan subnet mesin virtual bernama ContosoSubnet01.

### Contoh 2: Mendapatkan subnet mesin virtual menggunakan ID
```
PS C:\> $VNet = Get-WAPackVNet -Name "ContosoVNet01"
PS C:\> Get-WAPackVMSubnet -VNet $VNet -Id 66242D17-189F-480D-87CF-8E1D749998C8
```

Perintah ini mendapatkan subnet mesin virtual yang memiliki ID yang ditentukan.

### Contoh 3: Mendapatkan semua subnet mesin virtual dari jaringan virtualisasi tertentu
```
PS C:\> $VNet = Get-WAPackVNet -Name "ContosoVNet01"
PS C:\> Get-WAPackVMSubnet -VNet $VNet
```

Perintah ini mendapatkan semua subnet mesin virtual dari jaringan virtualisasi tertentu.

## PARAMETERS

### -ID
Menentukan ID unik subnet mesin virtual.

```yaml
Type: Guid
Parameter Sets: FromId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Menentukan nama subnet mesin virtual.

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
Menentukan VNet terkait dengan subnet mesin virtual.

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

[New-WAPackvMSubnet](./New-WAPackVMSubnet.md)

[Remove-WAPackvMSubnet](./Remove-WAPackVMSubnet.md)


