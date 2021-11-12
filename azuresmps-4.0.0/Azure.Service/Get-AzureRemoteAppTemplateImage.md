---
external help file: Microsoft.WindowsAzure.Commands.RemoteApp.dll-Help.xml
ms.assetid: DAEA68EF-8153-4E03-B539-B720EA14776C
online version: ''
schema: 2.0.0
ms.openlocfilehash: 542ae898ef056b06e0f3bbd11a146e6118ae21f9
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132427527"
---
# Get-AzureRemoteAppTemplateImage

## SYNOPSIS
Mengambil informasi tentang gambar templat Azure RemoteApp.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureRemoteAppTemplateImage [[-ImageName] <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureRemoteAppTemplateImage** mengambil informasi tentang gambar templat Azure RemoteApp di Microsoft Azure.
Cmdlet ini mengembalikan objek yang berisi informasi tentang gambar templat tertentu.
Jika tidak ada gambar templat yang ditentukan, templat akan mengambil informasi tentang semua gambar templat dalam langganan saat ini.

## EXAMPLES

### Contoh 1: Mendapatkan daftar semua gambar templat
```
PS C:\> Get-AzureRemoteAppTemplateImage
```

Perintah ini mengembalikan daftar semua gambar templat.

### Contoh 2: Mengambil informasi tentang gambar templat yang ditentukan
```
PS C:\> Get-AzureRemoteAppTemplateImage -ImageName "ContosoApps"
```

Perintah ini mengambil informasi tentang gambar templat bernama ContosoApps.

## PARAMETERS

### -ImageName
Menentukan nama gambar templat Azure RemoteApp.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
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

[Get-AzureRemoteAppCollection](./Get-AzureRemoteAppCollection.md)

[Get-AzureRemoteAppStartMenuProgram](./Get-AzureRemoteAppStartMenuProgram.md)


