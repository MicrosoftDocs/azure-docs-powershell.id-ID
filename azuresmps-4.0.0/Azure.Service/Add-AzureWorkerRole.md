---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: 8632A865-D4CC-4AE5-8307-055CDD776D26
online version: ''
schema: 2.0.0
ms.openlocfilehash: 3eda6181fa6ba78d56ec8cc1407c4cc6a6ab96a013055312dd3788ee1bc5f62e
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132417272"
---
# Add-AzureWorkerRole

## SYNOPSIS
Membuat file dan konfigurasi yang diperlukan untuk peran pekerja kustom.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Add-AzureWorkerRole [-TemplateFolder <String>] [-Name <String>] [-Instances <Int32>]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Topik ini menguraikan cmdlet dalam modul Microsoft Azure PowerShell versi 0.8.10.
Untuk mendapatkan versi modul yang Anda gunakan, di konsol Azure PowerShell, ketik `(Get-Module -Name Azure).Version` .

Cmdlet **Add-AzureWorkerRole** membuat file dan konfigurasi yang diperlukan, terkadang disebut peran pekerja kustom.

## EXAMPLES

### Contoh 1: Membuat peran pekerja contoh tunggal
```
PS C:\> Add-AzureWorkerRole -Name MyWorkerRole
```

Contoh ini menambahkan peran peran peran pekerja tunggal bernama MyWorkerRole ke aplikasi saat ini.

### Contoh 2: Membuat beberapa peran pekerja contoh
```
PS C:\> Add-AzureWorkerRole MyWorkerRole -I 2
```

Contoh ini menambahkan peran peran peran pekerja baru bernama MyWorkerRole ke aplikasi saat ini, dengan jumlah contoh peran 2.

### Contoh 3: Membuat peran pekerja dengan folder scaffolding kustom
```
PS C:\> Add-AzureWorkerRole MyWorkerRole -TemplateFoldr .\MyWorkerRoleTemplate
```

Contoh ini membuat peran pekerja dengan peran peran scaffolding kustom.

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
Nilai ini menentukan nama folder yang berisi folder untuk aplikasi kustom yang akan dihosting dalam peran pekerja.
Defaultnya adalah WorkerRolenumber, di mana jumlah peran pekerja di layanan.

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

### -TemplateFolder
Menentukan folder templat folder perancah yang akan digunakan untuk membuat peran pekerja.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Add-AzureWebRole](./Add-AzureWebRole.md)

[New-AzureRoleTemplate](./New-AzureRoleTemplate.md)


