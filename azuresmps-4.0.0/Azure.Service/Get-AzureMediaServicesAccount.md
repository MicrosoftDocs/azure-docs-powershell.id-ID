---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: A1327796-0CDC-43E0-97A6-FD1BF570066F
online version: ''
schema: 2.0.0
ms.openlocfilehash: b4f5e38a61775b27be36baf557a558b4f6d429e2
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132421584"
---
# Get-AzureMediaServicesAccount

## SYNOPSIS
Dapatkan akun Azure Media Services yang tersedia.

**Catatan:** Versi ini sudah tidak berlaku, silakan lihat versi [yang lebih baru.](https://docs.microsoft.com/powershell/module/azurerm.media/?view=azurermps-5.4.0#media_services)

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureMediaServicesAccount [-Name <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Topik ini menguraikan cmdlet dalam modul Microsoft Azure PowerShell versi 0.8.10.
Untuk mendapatkan versi modul yang Anda gunakan, di konsol Azure PowerShell, ketik `(Get-Module -Name Azure).Version` .

Untuk mencantumkan semua akun, gunakan `Get-AzureMediaServicesAccount` cmdlet.
Untuk mendapatkan informasi yang lebih mendetail tentang akun tertentu, gunakan `Get-AzureMediaServicesAccount -Name YourAccountName` cmdlet.

## EXAMPLES

### Contoh 1: List all Media Services accounts
```
PS C:\> Get-AzureMediaServicesAccount
```

Perintah ini mencantumkan semua akun Media Services tersedia.

### Contoh 2: Mendapatkan informasi detail tentang akun Media Services Anda
```
PS C:\> Get-AzureMediaServicesAccount -Name accountname
```

Perintah ini menampilkan properti akun Media Services Anda.

## PARAMETERS

### -Nama
Nama Media Services saya.

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

[Cara menggunakan Azure PowerShell untuk Media Services](https://go.microsoft.com/fwlink/?LinkId=324179)


