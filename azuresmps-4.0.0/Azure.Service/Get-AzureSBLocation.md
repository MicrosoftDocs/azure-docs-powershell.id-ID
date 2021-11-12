---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: 03E0442D-248E-41DB-98F5-DB3132CD0DCC
online version: ''
schema: 2.0.0
ms.openlocfilehash: 7d3042df6340f2a0ee53d91e7748c79c7571a8ec
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132428105"
---
# Get-AzureSBLocation

## SYNOPSIS
Mendapat lokasi Bus Layanan.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureSBLocation [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Topik ini menguraikan cmdlet dalam modul Microsoft Azure PowerShell versi 0.8.10.
Untuk mendapatkan versi modul yang Anda gunakan, di konsol Azure PowerShell, ketik `(Get-Module -Name Azure).Version` .

Cmdlet **Get-AzureSBLocation** mengembalikan lokasi tempat Bus Layanan tersedia.

[!INCLUDE [sb-deprecation.md](../include/sb-deprecation.md)]

## EXAMPLES

### Contoh 1: Dapatkan Bus Layanan lokasi baru
```
PS C:\> Get-AzureSBLocation
```

Contoh ini mendapatkan lokasi Bus Layanan.

## PARAMETERS

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

[Get-AzureSBNamespace](./Get-AzureSBNamespace.md)


