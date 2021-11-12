---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: 410A58A3-CB0E-43FE-B490-B1520BD1CCEC
online version: ''
schema: 2.0.0
ms.openlocfilehash: 51c11b798364773660b6f49d8eba1a2905fa70fc0d1aa306b19768166beb7e76
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132415218"
---
# Get-AzureSchedulerLocation

## SYNOPSIS
Mendapatkan lokasi penjadwal yang tersedia.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureSchedulerLocation [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Topik ini menguraikan cmdlet dalam modul Microsoft Azure PowerShell versi 0.8.10.
Untuk mendapatkan versi modul yang Anda gunakan, di konsol Azure PowerShell, ketik `(Get-Module -Name Azure).Version` .

Cmdlet **Get-AzureSchedulerLocation** mendapatkan lokasi penjadwal yang tersedia.

## EXAMPLES

### Contoh 1: Dapatkan lokasi penjadwal yang tersedia
```
PS C:\> Get-AzureSchedulerLocation
```

Perintah ini akan menyediakan lokasi penjadwal.

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

[Get-AzureSchedulerJob](./Get-AzureSchedulerJob.md)

[Get-AzureSchedulerJobCollection](./Get-AzureSchedulerJobCollection.md)

[Get-AzureSchedulerJobHistory](./Get-AzureSchedulerJobHistory.md)


