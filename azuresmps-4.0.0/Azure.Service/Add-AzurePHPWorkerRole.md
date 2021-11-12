---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: FEFBF1EF-FBCE-45D8-8455-F3F8662F1F36
online version: ''
schema: 2.0.0
ms.openlocfilehash: 0e0d3575623e7eaf0f9223f7796e1d549081a2849ced46ac8b445fd96d2eeb6b
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132417275"
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
Topik ini menguraikan cmdlet dalam modul Microsoft Azure PowerShell versi 0.8.10.
Untuk mendapatkan versi modul yang Anda gunakan, di konsol Azure PowerShell, ketik `(Get-Module -Name Azure).Version` .

Membuat file dan konfigurasi yang diperlukan, terkadang disebut sebagai lipatan, untuk aplikasi PHP yang akan dihosting di Azure melalui php.exe.

## EXAMPLES

### Contoh 1: Membuat peran pekerja dengan sebuah contoh
```
PS C:\> Add-AzurePHPWorkerRole MyWorkerRole
```

Contoh ini menambahkan file dan konfigurasi yang diperlukan untuk peran pekerja tunggal bernama MyWorkerRole ke aplikasi saat ini.

### Contoh 2: Membuat peran pekerja dengan beberapa contoh
```
PS C:\> Add-AzurePHPWorkerRole MyWorkerRole -I 2
```

Contoh ini menambahkan file dan konfigurasi yang diperlukan untuk peran pekerja baru ke aplikasi saat ini, menggunakan nama MyWorkerRole dengan hitungan contoh peran 2.

## PARAMETERS

### -Contoh
Menentukan jumlah contoh peran untuk peran pekerja ini.
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
Menentukan nama peran pekerja tersebut.
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

[New-AzureServiceProject](./New-AzureServiceProject.md)

[Add-AzurePHPWebRole](./Add-AzurePHPWebRole.md)


