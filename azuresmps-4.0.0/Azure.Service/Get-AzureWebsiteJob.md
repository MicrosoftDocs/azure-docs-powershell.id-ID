---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: 6B406310-287F-4BD3-BA38-A9C97E8EDC45
online version: ''
schema: 2.0.0
ms.openlocfilehash: c17c0c8f4ad93c63bcebce6ea408d6f9e77e0dbc
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132421573"
---
# Get-AzureWebsiteJob

## SYNOPSIS
Mendapatkan pekerjaan web terkait dengan situs web.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureWebsiteJob [-JobName <String>] [-JobType <String>] [-Name <String>] [-Slot <String>]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan pekerjaan web terkait dengan situs web.

## EXAMPLES

### Contoh 1: Mendapatkan info pekerjaan web tertentu
```
PS C:\> Get-AzureWebsiteJob -Name MyWebsite -JobName MyWebJob
```

Mendapatkan pekerjaan web bernama MyWebJob dari slot produksi Situs WebSaya.

### Contoh 2: Mendapatkan semua pekerjaan web untuk situs web
```
PS C:\> Get-AzureWebsiteJob -Name MyWebsite
```

Mendapatkan semua pekerjaan web terkait slot produksi MyWebsite.

### Contoh 3: Mendapatkan semua pekerjaan web yang dipicu
```
PS C:\> Get-AzureWebsiteJob -Name MyWebsite -Slot staging -Type Triggered
```

Mendapatkan semua pekerjaan web yang dipicu dari pengembangan slot SitusSaya.

## PARAMETERS

### -JobName
Nama pekerjaan web

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

### -JobType
Tipe pekerjaan web.
Nilai yang dapat diterima untuk parameter ini adalah:

- Dipicu
- Berkelanjutan

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

### -Nama
Nama situs web Azure.

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

### -Slot
Nama slot situs web Azure.

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

[Get-AzureWebsite](./Get-AzureWebsite.md)

[New-AzureWebsiteJob](./New-AzureWebsiteJob.md)

[Remove-AzureWebsiteJob](./Remove-AzureWebsiteJob.md)

[Start-AzureWebsiteJob](./Start-AzureWebsiteJob.md)

[Stop-AzureWebsiteJob](./Stop-AzureWebsiteJob.md)


