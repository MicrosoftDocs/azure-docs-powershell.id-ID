---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: C2DAFB2C-A58B-406C-8349-8728771B279E
online version: ''
schema: 2.0.0
ms.openlocfilehash: f8bb671ef725503da88ba405ad56af620fe3069e
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141922842"
---
# Add-AzureNodeWebRole

## SYNOPSIS
Membuat file dan folder yang diperlukan untuk aplikasi Node.js.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Add-AzureNodeWebRole [-Name <String>] [-Instances <Int32>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Topik ini menjelaskan cmdlet dalam versi 0.8.10 modul Microsoft Azure PowerShell.
Untuk mendapatkan versi modul yang Anda gunakan, di konsol Azure PowerShell, ketik .`(Get-Module -Name Azure).Version`

**Add-AzureNodeWebRole** membuat file dan folder yang diperlukan, terkadang disebut sebagai perancah, agar aplikasi Node.js dihosting di awan melalui IIS.

## EXAMPLES

### Contoh 1: Peran web instans tunggal
```
PS C:\> Add-AzureNodeWebRole -Name MyWebRole
```

Contoh ini menambahkan perancah untuk peran web tunggal bernama **MyWebRole** ke aplikasi saat ini.

### Contoh 2: Peran web beberapa contoh
```
PS C:\> Add-AzureNodeWebRole MyWebRole -I 2
```

Contoh ini menambahkan perancah untuk peran web baru bernama **MyWebRole** ke aplikasi saat ini, dengan jumlah contoh peran 2.

## PARAMETERS

### -Instances
Menentukan jumlah contoh peran untuk peran web ini.
Defaultnya adalah 1.

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
Ini juga menentukan nama direktori yang berisi perancah untuk aplikasi node.js yang akan dihosting dalam peran web.
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

[Add-AzureNodeWorkerRole](./Add-AzureNodeWorkerRole.md)

[New-AzureServiceProject](./New-AzureServiceProject.md)


