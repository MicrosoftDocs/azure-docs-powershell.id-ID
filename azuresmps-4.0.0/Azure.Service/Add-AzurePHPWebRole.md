---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: F9A06B8B-55DB-48A5-B246-53347E759E64
online version: ''
schema: 2.0.0
ms.openlocfilehash: 965df90e8a94048e64c0d4d92bcc0f86d6ffb37c
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141773078"
---
# Add-AzurePHPWebRole

## SYNOPSIS
Membuat file dan konfigurasi yang diperlukan untuk aplikasi PHP.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Add-AzurePHPWebRole [-Name <String>] [-Instances <Int32>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Topik ini menjelaskan cmdlet dalam versi 0.8.10 modul Microsoft Azure PowerShell.
Untuk mendapatkan versi modul yang Anda gunakan, di konsol Azure PowerShell, ketik .`(Get-Module -Name Azure).Version`

Cmdlet **Add-AzurePHPWebRole** membuat file dan konfigurasi, terkadang disebut sebagai perancah, untuk aplikasi PHP yang akan dihosting di Azure melalui IIS.

## EXAMPLES

### Contoh 1: Menambahkan peran web menggunakan nilai default
```
PS C:\> Add-AzurePHPWebRole
```

Contoh ini menambahkan file dan konfigurasi yang diperlukan untuk peran web baru menggunakan nilai default layanan bernama "WebRole1" dengan 1 instans.

### Contoh 2: Menambahkan peran web dengan beberapa contoh
```
PS C:\> Add-AzurePHPWebRole MyWebRole -I 2
```

Contoh ini menambahkan file dan konfigurasi yang diperlukan untuk peran web baru ke aplikasi saat ini, menggunakan nama "MyWebRole" dan jumlah contoh peran 2.

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
Nama menentukan nama direktori yang berisi file dan konfigurasi yang diperlukan untuk aplikasi PHP.
Defaultnya adalah WebRole#, di mana # adalah jumlah peran web dalam layanan.

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

[Add-AzurePHPWorkerRole](./Add-AzurePHPWorkerRole.md)

[New-AzureServiceProject](./New-AzureServiceProject.md)


