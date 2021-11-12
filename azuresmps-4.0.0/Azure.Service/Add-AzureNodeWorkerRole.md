---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: 7190C668-6A0C-4E1D-9B5A-0CEEF53E3F85
online version: ''
schema: 2.0.0
ms.openlocfilehash: baa781938cfb3d0a89f38cb1a727f329bb295c79
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132423248"
---
# Add-AzureNodeWorkerRole

## SYNOPSIS
Membuat file dan folder yang diperlukan untuk Node.js yang akan dihosting di awan melalui node.exe

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Add-AzureNodeWorkerRole [-Name <String>] [-Instances <Int32>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Topik ini menguraikan cmdlet dalam modul Microsoft Azure PowerShell versi 0.8.10.
Untuk mendapatkan versi modul yang Anda gunakan, di konsol Azure PowerShell, ketik `(Get-Module -Name Azure).Version` .

Cmdlet **Add-AzureNodeWorkerRole** membuat file dan folder yang diperlukan, terkadang disebut sebagai foldercakup, untuk aplikasi Node.js yang akan dihosting di awan melalui node.exe.

## EXAMPLES

### Contoh 1: Peran pekerja contoh tunggal
```
PS C:\> Add-AzureWorkerRole MyWorkerRole
```

Contoh ini menambahkan peran peran peran pekerja tunggal bernama **MyWorkerRole ke** aplikasi saat ini.

### Contoh 2: Beberapa peran pekerja contoh
```
PS C:\> Add-AzureNodeWorkerRole MyWorkerRole -I 2
```

Contoh ini menambahkan peran pekerja tunggal bernama **MyWorkerRole** ke aplikasi saat ini, dengan hitungan contoh peran 2.

## PARAMETERS

### -Contoh
Menentukan jumlah contoh peran untuk peran pekerja ini.
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
Menentukan nama peran pekerja tersebut.
Nilai menentukan nama folder yang berisi folder folder untuk layanan node.js yang dihosting dalam peran pekerja.
Defaultnya adalah WorkerRole1.

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

[Add-AzureNodeWebRole](./Add-AzureNodeWebRole.md)

[New-AzureServiceProject](./New-AzureServiceProject.md)


