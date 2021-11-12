---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: 047C5FBD-CB0D-47BF-AE03-4DF32B4FAD87
online version: ''
schema: 2.0.0
ms.openlocfilehash: c0a8a19e3f2f0e99beaceac7fcd5cbfdb28dbcf3
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132427516"
---
# Get-WAPackVM

## SYNOPSIS
Mendapatkan objek mesin virtual.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### Kosong (Default)
```
Get-WAPackVM [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### FromName
```
Get-WAPackVM [-Name <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### FromId
```
Get-WAPackVM [-ID <Guid>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Topik ini sudah tidak berlaku dan akan dihapus di masa mendatang.
Topik ini menguraikan cmdlet dalam versi 0.8.1 modul Microsoft Azure PowerShell.
Untuk mencari tahu versi modul yang Anda gunakan, dari konsol Azure PowerShell, ketik `(Get-Module -Name Azure).Version` .

Cmdlet **Get-WAPackvM** mendapatkan objek mesin virtual.

## EXAMPLES

### Contoh 1: Get a virtual machine by using a name
```
PS C:\> Get-WAPackVM -Name "ContosoV126"
```

Perintah ini mendapatkan mesin virtual bernama ContosoV126.

### Contoh 2: Dapatkan mesin virtual dengan menggunakan ID
```
PS C:\> Get-WAPackVM -Id 66242D17-189F-480D-87CF-8E1D749998C8
```

Perintah ini akan mendapatkan mesin virtual dengan ID yang ditentukan.

### Contoh 3: Get all virtual machines
```
PS C:\> Get-WAPackVM
```

Perintah ini memiliki semua mesin virtual.

## PARAMETERS

### -ID
Menentukan ID unik mesin virtual.

```yaml
Type: Guid
Parameter Sets: FromId
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nama
Menentukan nama mesin virtual.

```yaml
Type: String
Parameter Sets: FromName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[New-WAPackvm](./New-WAPackVM.md)

[Remove-WAPackvm](./Remove-WAPackVM.md)

[Restart-WAPackvm](./Restart-WAPackVM.md)

[Resume-WAPackvm](./Resume-WAPackVM.md)

[Set-WAPackvm](./Set-WAPackVM.md)

[Start-WAPackvm](./Start-WAPackVM.md)

[Stop-WAPackvm](./Stop-WAPackVM.md)

[Suspend-WAPackvm](./Suspend-WAPackVM.md)

[Get-WAPackvMOSDisk](./Get-WAPackVMOSDisk.md)


