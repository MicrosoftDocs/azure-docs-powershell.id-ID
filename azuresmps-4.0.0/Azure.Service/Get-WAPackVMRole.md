---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: D7EB9FE4-BDEB-43A5-B6D3-FEAB16BC2711
online version: ''
schema: 2.0.0
ms.openlocfilehash: b5f5d719b8eabe842bb4d4882bb0bdef9c8de4c580b9e6e7361c29243fe987d8
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132419226"
---
# Get-WAPackVMRole

## SYNOPSIS

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### Kosong (Default)
```
Get-WAPackVMRole [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### FromName
```
Get-WAPackVMRole -Name <String> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### FromCloudService
```
Get-WAPackVMRole -Name <String> -CloudServiceName <String> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Topik ini sudah tidak berlaku dan akan dihapus di masa mendatang.
Topik ini menguraikan cmdlet dalam versi 0.8.1 modul Microsoft Azure PowerShell ini.
Untuk mencari tahu versi modul yang Anda gunakan, dari konsol Azure PowerShell, ketikkan `(Get-Module -Name Azure).Version` .

## EXAMPLES

### Contoh 1: Mendapatkan peran mesin virtual (dibuat melalui portal)
```
PS C:\> Get-WAPackVMRole -Name "ContosoVMRole01"
```

Perintah ini mendapatkan peran mesin virtual yang telah dibuat melalui portal bernama ContosoVMRole01.

### Contoh 2: Mendapatkan peran mesin virtual menggunakan nama dan nama layanan cloud
```
PS C:\> Get-WAPackVMRole -CloudServiceName "ContosoCloudService01" -Name "ContosoVMRole02"
```

Perintah ini mendapatkan peran mesin virtual bernama ContosoVMRole02 yang berdiri di layanan awan bernama ContosoCloudService01.

### Contoh 3: Mendapatkan semua peran mesin virtual
```
PS C:\> Get-WAPackVMRole
```

Perintah ini mendapatkan semua peran mesin virtual yang ada.

## PARAMETERS

### -CloudServiceName
Menentukan nama layanan awan dari peran mesin virtual.

```yaml
Type: String
Parameter Sets: FromCloudService
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nama
Menentukan nama peran mesin virtual.

```yaml
Type: String
Parameter Sets: FromName, FromCloudService
Aliases:

Required: True
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

[New-WAPackVMRole](./New-WAPackVMRole.md)

[Remove-WAPackVMRole](./Remove-WAPackVMRole.md)

[Set-WAPackvMRole](./Set-WAPackVMRole.md)


