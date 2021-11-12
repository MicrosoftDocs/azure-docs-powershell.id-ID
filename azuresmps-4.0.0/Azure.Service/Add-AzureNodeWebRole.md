---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: C2DAFB2C-A58B-406C-8349-8728771B279E
online version: ''
schema: 2.0.0
ms.openlocfilehash: f8bb671ef725503da88ba405ad56af620fe3069e
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132423254"
---
# Add-AzureNodeWebRole

## SYNOPSIS
Membuat file dan folder yang diperlukan untuk Node.js folder.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Add-AzureNodeWebRole [-Name <String>] [-Instances <Int32>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Topik ini menguraikan cmdlet dalam modul Microsoft Azure PowerShell versi 0.8.10.
Untuk mendapatkan versi modul yang Anda gunakan, di konsol Azure PowerShell, ketik `(Get-Module -Name Azure).Version` .

**Add-AzureNodeWebRole** membuat file dan folder yang diperlukan, terkadang disebut perancah, untuk aplikasi Node.js yang akan dihosting di awan melalui IIS.

## EXAMPLES

### Contoh 1: Peran web contoh tunggal
```
PS C:\> Add-AzureNodeWebRole -Name MyWebRole
```

Contoh ini menambahkan peran peran web tunggal bernama **MyWebRole ke** aplikasi saat ini.

### Contoh 2: Peran web beberapa contoh
```
PS C:\> Add-AzureNodeWebRole MyWebRole -I 2
```

Contoh ini menambahkan peran peran web baru bernama **MyWebRole** ke aplikasi saat ini, dengan hitungan contoh peran 2.

## PARAMETERS

### -Contoh
Menentukan jumlah contoh peran untuk peran di web ini.
Nilai default adalah 1.

```yaml
Type: Int32
Parameter Sets: (All)
Aliases: i

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Menentukan nama peran web.
Cara ini juga menentukan nama direktori yang berisi lipatan untuk aplikasi node.js yang akan dihosting di peran web.
Defaultnya adalah WebRole#, di mana # menunjukkan jumlah peran web dalam layanan.

```yaml
Type: String
Parameter Sets: (All)
Aliases: n

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Add-AzureNodeWorkerRole](./Add-AzureNodeWorkerRole.md)

[New-AzureServiceProject](./New-AzureServiceProject.md)


