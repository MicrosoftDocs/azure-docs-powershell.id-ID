---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: 047C5FBD-CB0D-47BF-AE03-4DF32B4FAD87
online version: ''
schema: 2.0.0
ms.openlocfilehash: c0a8a19e3f2f0e99beaceac7fcd5cbfdb28dbcf3
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142094658"
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
Topik ini ditolak dan akan dihapus di masa mendatang.
Topik ini menjelaskan cmdlet dalam versi 0.8.1 modul Microsoft Azure PowerShell.
Untuk mengetahui versi modul yang Anda gunakan, dari konsol Azure PowerShell, ketik `(Get-Module -Name Azure).Version`.

Cmdlet **Get-WAPackVM** mendapatkan objek mesin virtual.

## EXAMPLES

### Contoh 1: Dapatkan mesin virtual dengan menggunakan nama
```
PS C:\> Get-WAPackVM -Name "ContosoV126"
```

Perintah ini mendapatkan mesin virtual bernama ContosoV126.

### Contoh 2: Dapatkan mesin virtual dengan menggunakan ID
```
PS C:\> Get-WAPackVM -Id 66242D17-189F-480D-87CF-8E1D749998C8
```

Perintah ini mendapatkan mesin virtual yang memiliki ID yang ditentukan.

### Contoh 3: Dapatkan semua mesin virtual
```
PS C:\> Get-WAPackVM
```

Perintah ini mendapatkan semua mesin virtual.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[WAPackVM Baru](./New-WAPackVM.md)

[Hapus-WAPackVM](./Remove-WAPackVM.md)

[Mulai ulang-WAPackVM](./Restart-WAPackVM.md)

[Resume-WAPackVM](./Resume-WAPackVM.md)

[Set-WAPackVM](./Set-WAPackVM.md)

[Start-WAPackVM](./Start-WAPackVM.md)

[Stop-WAPackVM](./Stop-WAPackVM.md)

[Suspensi-WAPackVM](./Suspend-WAPackVM.md)

[Get-WAPackVMOSDisk](./Get-WAPackVMOSDisk.md)


