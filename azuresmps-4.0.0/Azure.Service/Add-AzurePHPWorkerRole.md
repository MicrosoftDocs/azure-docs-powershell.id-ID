---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: FEFBF1EF-FBCE-45D8-8455-F3F8662F1F36
online version: ''
schema: 2.0.0
ms.openlocfilehash: 6c0e8d11d196033bf2d7c0e996a908e06f2076ac
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143044436"
---
# Add-AzurePHPWorkerRole

## SYNOPSIS
Membuat file dan konfigurasi yang diperlukan untuk aplikasi PHP yang akan dihosting di Azure melalui php.exe.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Add-AzurePHPWorkerRole [-Name <String>] [-Instances <Int32>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Topik ini menjelaskan cmdlet dalam versi 0.8.10 dari modul Microsoft Azure PowerShell.
Untuk mendapatkan versi modul yang Anda gunakan, di konsol Azure PowerShell, ketik `(Get-Module -Name Azure).Version`.

Membuat file dan konfigurasi yang diperlukan, terkadang disebut sebagai perancah, untuk aplikasi PHP yang akan dihosting di Azure melalui php.exe.

## EXAMPLES

### Contoh 1: Membuat peran pekerja dengan satu instans
```
PS C:\> Add-AzurePHPWorkerRole MyWorkerRole
```

Contoh ini menambahkan file dan konfigurasi yang diperlukan untuk satu peran pekerja bernama MyWorkerRole ke aplikasi saat ini.

### Contoh 2: Membuat peran pekerja dengan beberapa instans
```
PS C:\> Add-AzurePHPWorkerRole MyWorkerRole -I 2
```

Contoh ini menambahkan file dan konfigurasi yang diperlukan untuk peran pekerja baru ke aplikasi saat ini, menggunakan nama MyWorkerRole dengan jumlah instans peran 2.

## PARAMETERS

### -Instans
Menentukan jumlah instans peran untuk peran pekerja ini.
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

### -Name
Menentukan nama peran pekerja.
Nama menentukan nama folder yang berisi file dan konfigurasi yang diperlukan untuk layanan PHP yang dihosting dalam peran pekerja.
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
Menentukan profil Azure tempat cmdlet ini dibaca.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[New-AzureServiceProject](./New-AzureServiceProject.md)

[Add-AzurePHPWebRole](./Add-AzurePHPWebRole.md)


