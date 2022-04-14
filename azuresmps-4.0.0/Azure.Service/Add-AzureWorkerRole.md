---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: 8632A865-D4CC-4AE5-8307-055CDD776D26
online version: ''
schema: 2.0.0
ms.openlocfilehash: 4be2c2ac3ed189c4831613890648cbdbebb31f7c
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141922821"
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
Topik ini menjelaskan cmdlet dalam versi 0.8.10 modul Microsoft Azure PowerShell.
Untuk mendapatkan versi modul yang Anda gunakan, di konsol Azure PowerShell, ketik .`(Get-Module -Name Azure).Version`

Cmdlet **Add-AzureWorkerRole** membuat file dan konfigurasi yang diperlukan, terkadang disebut sebagai perancah, untuk peran pekerja kustom.

## EXAMPLES

### Contoh 1: Membuat peran pekerja instans tunggal
```
PS C:\> Add-AzureWorkerRole -Name MyWorkerRole
```

Contoh ini menambahkan perancah untuk peran pekerja tunggal bernama MyWorkerRole ke aplikasi saat ini.

### Contoh 2: Membuat peran beberapa contoh pekerja
```
PS C:\> Add-AzureWorkerRole MyWorkerRole -I 2
```

Contoh ini menambahkan peran peran pekerja baru bernama MyWorkerRole ke aplikasi saat ini, dengan jumlah contoh peran 2.

### Contoh 3: Membuat peran pekerja dengan perancah kustom
```
PS C:\> Add-AzureWorkerRole MyWorkerRole -TemplateFoldr .\MyWorkerRoleTemplate
```

Contoh ini membuat peran pekerja dengan perancah kustom.

## PARAMETERS

### -Instances
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
Menentukan nama peran pekerja.
Nilai ini menentukan nama folder yang berisi perancah untuk aplikasi kustom yang akan dihosting dalam peran pekerja.
Defaultnya adalah WorkerRolenumber, di mana angka adalah jumlah peran pekerja dalam layanan.

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

### -TemplateFolder
Menentukan folder templat perancah yang akan digunakan untuk membuat peran pekerja.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Add-AzureWebRole](./Add-AzureWebRole.md)

[AzureRoleTemplate baru](./New-AzureRoleTemplate.md)


