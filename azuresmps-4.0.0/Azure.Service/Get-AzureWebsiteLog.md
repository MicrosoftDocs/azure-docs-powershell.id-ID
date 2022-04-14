---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: BFB57100-93F6-4FD2-8ECA-7F54BEB0D6B0
online version: ''
schema: 2.0.0
ms.openlocfilehash: d0cc984e4930935201a0d92be005fb231dcb464f
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141921114"
---
# Get-AzureWebsiteLog

## SYNOPSIS
Mendapatkan log untuk situs web tertentu.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### Ekor
```
Get-AzureWebsiteLog [-Path <String>] [-Message <String>] [-Tail] [-Name <String>] [-Slot <String>]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### ListPath
```
Get-AzureWebsiteLog [-ListPath] [-Name <String>] [-Slot <String>] [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
Topik ini menjelaskan cmdlet dalam versi 0.8.10 modul Microsoft Azure PowerShell.
Untuk mendapatkan versi modul yang Anda gunakan, di konsol Azure PowerShell, ketik .`(Get-Module -Name Azure).Version`

Mendapatkan log untuk situs web tertentu.

## EXAMPLES

### Contoh 1: Mulai streaming log
```
PS C:\> Get-AzureWebsiteLog -Tail
```

Contoh ini memulai streaming log untuk semua log aplikasi.

### Contoh 2: Mulai streaming log untuk log http
```
PS C:\> Get-AzureWebsiteLog -Tail -Path http
```

Contoh ini memulai streaming log untuk log http.

### Contoh 3: Mulai streaming log untuk log kesalahan
```
PS C:\> Get-AzureWebsiteLog -Tail -Message Error
```

Contoh ini memulai streaming log dan memperlihatkan log kesalahan saja.

### Contoh 4: Menampilkan log yang tersedia
```
PS C:\> Get-AzureWebsiteLog -Name MyWebsite -ListPath
```

Contoh ini mencantumkan semua jalur log yang tersedia di situs web.

## PARAMETERS

### -ListPath
Menunjukkan apakah akan mencantumkan jalur log.

```yaml
Type: SwitchParameter
Parameter Sets: ListPath
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Pesan
Menentukan string yang akan digunakan untuk memfilter pesan log.
Hanya log yang berisi string ini yang akan diambil.

```yaml
Type: String
Parameter Sets: Tail
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nama
Nama situs web.

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

### -Jalur
Jalur dari mana log akan diambil.
Secara default adalah Root, yang berarti menyertakan semua jalur.

```yaml
Type: String
Parameter Sets: Tail
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

### -Slot
Menentukan nama slot.

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

### -Tail
Menentukan apakah akan melakukan streaming log.

```yaml
Type: SwitchParameter
Parameter Sets: Tail
Aliases: 

Required: True
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

[Dapatkan-AzureWebsite](./Get-AzureWebsite.md)

[Baru-AzureSitus Web](./New-AzureWebsite.md)

[Hapus-AzureSitus Web](./Remove-AzureWebsite.md)

[Mulai AzureSitus Web](./Start-AzureWebsite.md)


