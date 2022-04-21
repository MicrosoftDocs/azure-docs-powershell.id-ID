---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: A1327796-0CDC-43E0-97A6-FD1BF570066F
online version: ''
schema: 2.0.0
ms.openlocfilehash: b4f5e38a61775b27be36baf557a558b4f6d429e2
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142724032"
---
# Get-AzureMediaServicesAccount

## SYNOPSIS
Dapatkan akun Azure Media Services yang tersedia.

**Catatan:** Versi ini sudah tidak digunakan lagi, silakan lihat [versi yang lebih baru](https://docs.microsoft.com/powershell/module/azurerm.media/?view=azurermps-5.4.0#media_services).

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureMediaServicesAccount [-Name <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Topik ini menjelaskan cmdlet dalam versi 0.8.10 modul Microsoft Azure PowerShell.
Untuk mendapatkan versi modul yang Anda gunakan, di konsol Azure PowerShell, ketik .`(Get-Module -Name Azure).Version`

Untuk mencantumkan semua akun, gunakan `Get-AzureMediaServicesAccount` cmdlet.
Untuk mendapatkan informasi lebih mendetail tentang akun tertentu, gunakan `Get-AzureMediaServicesAccount -Name YourAccountName` cmdlet.

## EXAMPLES

### Contoh 1: Daftar semua akun Media Services
```
PS C:\> Get-AzureMediaServicesAccount
```

Perintah ini mencantumkan semua akun Media Services yang tersedia.

### Contoh 2: Dapatkan informasi mendetail tentang akun Media Services
```
PS C:\> Get-AzureMediaServicesAccount -Name accountname
```

Perintah ini menampilkan properti akun Media Services.

## PARAMETERS

### -Nama
Nama akun Media Services.

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

## NOTES

## RELATED LINKS

[Cara menggunakan Azure PowerShell untuk Media Services](https://go.microsoft.com/fwlink/?LinkId=324179)


