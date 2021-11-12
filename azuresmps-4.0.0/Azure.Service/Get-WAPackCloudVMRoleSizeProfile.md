---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: 453AEA42-E29C-4FF2-9210-0DD88B77DC07
online version: ''
schema: 2.0.0
ms.openlocfilehash: 2f96f2796a219f68087d2e918eeb018d53219580ef090b8ceaa14dbd99d9da26
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132418200"
---
# Get-WAPackCloudVMRoleSizeProfile

## SYNOPSIS
Mendapatkan objek profil Ukuran Peran VM Cloud.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### Kosong (Default)
```
Get-WAPackCloudVMRoleSizeProfile [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### FromName
```
Get-WAPackCloudVMRoleSizeProfile [-Name <String>] [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-WAPackCloudVMRoleSizeProfile** mendapatkan objek profil ukuran Peran VM Cloud untuk mesin virtual.

## EXAMPLES

### Contoh 1: Dapatkan profil ukuran Peran VM Cloud menggunakan nama
```
PS C:\> Get-WAPackCloudVMRoleSizeProfile -Name "Small"
```

Perintah ini mendapatkan profil ukuran bernama Small.

### Contoh 2: Mendapatkan semua profil Ukuran peran VM Cloud
```
PS C:\> Get-WAPackCloudVMRoleSizeProfile
```

Perintah ini memiliki semua profil berukuran.

## PARAMETERS

### -Nama
Menentukan nama profil ukuran Peran VM Awan.

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

[Get-WAPackvm](./Get-WAPackVM.md)


