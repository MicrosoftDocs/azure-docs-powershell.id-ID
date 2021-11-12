---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: EFBC8DCD-00CC-4BBF-9383-EA15376535F3
online version: ''
schema: 2.0.0
ms.openlocfilehash: 98c845a4a3ae57e19c10e8e0f86de6b37ad0e3704ca00bdc3db0185dc9fb96dc
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132417663"
---
# Update-AzureWebsiteRepository

## SYNOPSIS
Memperbarui penyimpanan jarak jauh repositori git lokal untuk semua slot.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Update-AzureWebsiteRepository [-Name <String>] -PublishingUsername <String> [-Profile <AzureSMProfile>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Update-AzureWebsiteRepository** memperbarui penyimpanan jarak jauh repositori git lokal untuk semua slot.

## EXAMPLES

### Contoh 1: Memperbarui Penyimpanan Jarak Jauh Situs Web
```
PS C:\> Update-AzureWebsiteRepository -Name MyWebsite
```

Memperbarui penyimpanan jarak jauh repositori git lokal untuk semua slot untuk situs web MyWebsite.

## PARAMETERS

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

### -PublishingUsername
Nama pengguna yang telah Anda tentukan di Microsoft Azure Portal untuk penyebaran Git.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak berjalan.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Get-AzureWebsite](./Get-AzureWebsite.md)

[New-AzureWebsite](./New-AzureWebsite.md)

[Start-AzureWebsite](./Start-AzureWebsite.md)

[Stop-AzureWebsite](./Stop-AzureWebsite.md)


