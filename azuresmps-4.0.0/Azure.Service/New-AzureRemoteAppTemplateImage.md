---
external help file: Microsoft.WindowsAzure.Commands.RemoteApp.dll-Help.xml
ms.assetid: DBC4A0B8-A34A-47AC-930B-EFE23A95A216
online version: ''
schema: 2.0.0
ms.openlocfilehash: 5eb61bdd3acb1c1e3a51376be8681018ac5320a6
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142313142"
---
# New-AzureRemoteAppTemplateImage

## SYNOPSIS
Mengunggah atau mengimpor gambar templat Azure RemoteApp.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### UploadLocalVhd (Default)
```
New-AzureRemoteAppTemplateImage [-ImageName] <String> [-Location] <String> [-Path] <String> [-Resume]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### AzureVmUpload
```
New-AzureRemoteAppTemplateImage [-ImageName] <String> [-Location] <String> -AzureVmImageName <String>
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzureRemoteAppTemplateImage** mengunggah atau mengimpor gambar templat Azure RemoteApp.

## EXAMPLES

### Contoh 1: Upload file VHD untuk membuat gambar templat
```
PS C:\> New-AzureRemoteAppTemplateImage -ImageName "ContosoApps" -Location "North Europe" -Path "C:\RemoteAppImages\ContosoApps.vhd"
```

Perintah ini mengunggah C:\RemoteAppImages\ContosoApps.vhd untuk membuat gambar templat bernama ContosoApps di pusat data Eropa Utara.

## PARAMETERS

### -AzureVmImageName
Menentukan nama mesin virtual Azure untuk digunakan sebagai gambar templat.

```yaml
Type: String
Parameter Sets: AzureVmUpload
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ImageName
Menentukan nama gambar templat Azure RemoteApp.

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

### -Lokasi
Menentukan kawasan Azure dari gambar templat.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Jalur
Menentukan jalur file gambar templat.

```yaml
Type: String
Parameter Sets: UploadLocalVhd
Aliases: 

Required: True
Position: 3
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

### -Lanjutkan
Menunjukkan bahwa cmdlet ini dilanjutkan jika unggahan gambar templat terganggu.

```yaml
Type: SwitchParameter
Parameter Sets: UploadLocalVhd
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

[Get-AzureRemoteAppTemplateImage](./Get-AzureRemoteAppTemplateImage.md)

[Hapus-AzureRemoteAppTemplateImage](./Remove-AzureRemoteAppTemplateImage.md)

[Ganti nama-AzureRemoteAppTemplateImage](./Rename-AzureRemoteAppTemplateImage.md)


