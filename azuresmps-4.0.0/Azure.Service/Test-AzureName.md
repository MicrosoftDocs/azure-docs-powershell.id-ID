---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: 0DF54C9D-7A19-4591-A1FC-33C6A4C9BF33
online version: ''
schema: 2.0.0
ms.openlocfilehash: 8d0f56a3d20304b80eb83a89b6fa44fd294572f8168eeaf2952f617db1a6529b
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132417669"
---
# Test-AzureName

## SYNOPSIS
Menguji apakah nama Microsoft Azure layanan awan, nama layanan penyimpanan atau nama ruang nama bus layanan ada atau tidak.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### Layanan
```
Test-AzureName [-Service] -Name <String> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### Storage
```
Test-AzureName [-Storage] -Name <String> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### ServiceBusNamespace
```
Test-AzureName [-ServiceBusNamespace] -Name <String> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### Situs Web
```
Test-AzureName [-Website] -Name <String> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Jika nama ada, cmdlet akan mengembalikan $True.
Jika nama tidak ada, hasilnya akan $False.

## EXAMPLES

### Contoh 1
```
PS C:\> Test-AzureName -Service "MyNameService1"
```

Perintah ini menguji untuk melihat apakah "MyNameService1" sudah Microsoft Azure layanan awan.

### Contoh 2
```
PS C:\> Test-AzureName -Storage "mystorename1"
```

Perintah ini menguji untuk melihat apakah "mystorename1" sudah Microsoft Azure layanan penyimpanan.

### Contoh 3
```
PS C:\> Test-AzureName -ServiceBusNamespace "mynamespace"
```

Uji perintah ini untuk melihat apakah "mynamespace" adalah nama ruang nama Microsoft Azure bus layanan yang sudah ada.

## PARAMETERS

### -Nama
Menentukan nama layanan atau akun penyimpanan untuk diuji.

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

### -Layanan
Menentukan untuk menguji akun layanan yang sudah ada.

```yaml
Type: SwitchParameter
Parameter Sets: Service
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ServiceBusNamespace
Menentukan untuk menguji ruang nama bus layanan yang sudah ada.

```yaml
Type: SwitchParameter
Parameter Sets: ServiceBusNamespace
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Storage
Menentukan untuk menguji akun penyimpanan yang sudah ada.

```yaml
Type: SwitchParameter
Parameter Sets: Storage
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Situs web
Menentukan untuk menguji situs web yang sudah ada.

```yaml
Type: SwitchParameter
Parameter Sets: Website
Aliases: 

Required: True
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
* node-dev, php-dev, python-dev

## RELATED LINKS

