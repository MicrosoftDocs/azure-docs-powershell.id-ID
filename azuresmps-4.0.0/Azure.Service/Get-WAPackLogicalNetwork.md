---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: 7D51BE56-C0A2-4A32-BB7F-8FA9CC67F8F9
online version: ''
schema: 2.0.0
ms.openlocfilehash: 8fb02cd450ac515f2473c4380123f681f402610523b1df2665072f681ecdc91a
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132418647"
---
# Get-WAPackLogicalNetwork

## SYNOPSIS
Mendapatkan objek jaringan logis.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### Kosong (Default)
```
Get-WAPackLogicalNetwork [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### FromName
```
Get-WAPackLogicalNetwork [-Name <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Topik ini sudah tidak berlaku dan akan dihapus di masa mendatang.
Topik ini menguraikan cmdlet dalam versi 0.8.1 modul Microsoft Azure PowerShell.
Untuk mencari tahu versi modul yang Anda gunakan, dari konsol Azure PowerShell, ketik `(Get-Module -Name Azure).Version` .

Cmdlet **Get-WAPackLogicalNetwork** mendapatkan objek jaringan logis.

## EXAMPLES

### Contoh 1: Mendapatkan jaringan logika dengan menggunakan nama
```
PS C:\> Get-WAPackLogicalNetwork -Name "ContosoLogicalNetwork01"
```

Perintah ini mendapatkan jaringan logis bernama ContosoLogicalNetwork01.

### Contoh 2: Mendapatkan semua jaringan logika
```
PS C:\> Get-WAPackLogicalNetwork
```

Perintah ini mendapatkan semua jaringan logika.

## PARAMETERS

### -Nama
Menentukan nama jaringan logika.

```yaml
Type: String
Parameter Sets: FromName
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

