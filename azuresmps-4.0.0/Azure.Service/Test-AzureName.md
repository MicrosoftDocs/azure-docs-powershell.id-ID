---
external help file: Microsoft.WindowsAzure.Commands.dll-Help.xml
ms.assetid: 0DF54C9D-7A19-4591-A1FC-33C6A4C9BF33
online version: ''
schema: 2.0.0
ms.openlocfilehash: 71d1f9ce5c0cd7084fb268cb16baa7e6d3041741
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142653850"
---
# Test-AzureName

## SYNOPSIS
Menguji apakah nama layanan cloud Microsoft Azure, nama layanan penyimpanan, atau nama ruang nama bus layanan ada atau tidak.

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

### Website
```
Test-AzureName [-Website] -Name <String> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Jika nama ada, cmdlet akan mengembalikan $True.
Jika nama tidak ada, nama akan mengembalikan $False.

## EXAMPLES

### Contoh 1
```
PS C:\> Test-AzureName -Service "MyNameService1"
```

Perintah ini menguji untuk melihat apakah "MyNameService1" adalah nama layanan cloud Microsoft Azure yang sudah ada.

### Contoh 2
```
PS C:\> Test-AzureName -Storage "mystorename1"
```

Perintah ini menguji untuk melihat apakah "mystorename1" adalah nama layanan penyimpanan Microsoft Azure yang sudah ada.

### Contoh 3
```
PS C:\> Test-AzureName -ServiceBusNamespace "mynamespace"
```

Perintah ini menguji untuk melihat apakah "mynamespace" adalah nama ruang nama bus layanan Microsoft Azure yang sudah ada.

## PARAMETERS

### -Nama
Menentukan nama akun layanan atau penyimpanan untuk diuji.

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

### -Situs Web
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES
* node-dev, php-dev, python-dev

## RELATED LINKS

