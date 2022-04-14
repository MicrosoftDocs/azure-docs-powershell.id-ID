---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: 453AEA42-E29C-4FF2-9210-0DD88B77DC07
online version: ''
schema: 2.0.0
ms.openlocfilehash: a9628a1874e3dfbf9edde37770619a006c319f0b
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142094733"
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

### Contoh 1: Dapatkan profil ukuran Peran VM Cloud dengan menggunakan nama
```
PS C:\> Get-WAPackCloudVMRoleSizeProfile -Name "Small"
```

Perintah ini mendapatkan profil ukuran bernama Small.

### Contoh 2: Dapatkan semua profil ukuran Peran VM Cloud
```
PS C:\> Get-WAPackCloudVMRoleSizeProfile
```

Perintah ini mendapatkan semua profil ukuran.

## PARAMETERS

### -Nama
Menentukan nama profil ukuran Peran VM Cloud.

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

## CATATAN

## RELATED LINKS

[Get-WAPackVM](./Get-WAPackVM.md)


