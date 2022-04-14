---
external help file: Microsoft.WindowsAzure.Commands.RemoteApp.dll-Help.xml
ms.assetid: B35979E5-94C4-4DCC-B87D-D6915464CF69
online version: ''
schema: 2.0.0
ms.openlocfilehash: 0c20cea0284ddd1df55bdcd41000076eb8c89428
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141920179"
---
# Remove-AzureRemoteAppTemplateImage

## SYNOPSIS
Menghapus gambar templat Azure RemoteApp.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Remove-AzureRemoteAppTemplateImage [-ImageName] <String> [-Profile <AzureSMProfile>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzureRemoteAppTemplateImage** menghapus gambar templat Azure RemoteApp.
Gambar templat hanya dapat dihapus jika tidak ditautkan ke koleksi Azure RemoteApp apa pun.

## EXAMPLES

### Contoh 1: Menghapus gambar templat
```
PS C:\> Remove-AzureRemoteAppTemplateImage -ImageName "ContosoApps"
```

Perintah ini menghapus gambar templat bernama ContosoApps.

## PARAMETERS

### -ImageName
Menentukan nama gambar templat RemoteApp.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
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

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

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
Cmdlet tidak dijalankan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Get-AzureRemoteAppTemplateImage](./Get-AzureRemoteAppTemplateImage.md)

[AzureRemoteAppTemplateImage baru](./New-AzureRemoteAppTemplateImage.md)

[Ganti nama-AzureRemoteAppTemplateImage](./Rename-AzureRemoteAppTemplateImage.md)


