---
external help file: Microsoft.WindowsAzure.Commands.TrafficManager.dll-Help.xml
ms.assetid: 92E2409B-14BC-428F-8BAF-60D8DAFA5F57
online version: ''
schema: 2.0.0
ms.openlocfilehash: 2992152675187be779f2cac3d2349f3ec718b9c2
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142334452"
---
# Test-AzureTrafficManagerDomainName

## SYNOPSIS
Memeriksa apakah nama domain tersedia sebagai profil Traffic Manager.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Test-AzureTrafficManagerDomainName -DomainName <String> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Test-AzureTrafficManagerDomainName** memeriksa apakah nama domain tersedia sebagai profil Microsoft Azure Traffic Manager.
Jika nama domain tersedia, cmdlet ini mengembalikan nilai $True.

## EXAMPLES

### Contoh 1: Memeriksa apakah nama domain tersedia
```
PS C:\>Test-AzureTrafficManagerDomainName -DomainName "ContosoApp.trafficmanager.net"
$True
```

Perintah ini memeriksa apakah nama domain ContosoApp.trafficmanager.net tersedia sebagai profil Traffic Manager.

## PARAMETERS

### -DomainName
Menentukan nama domain yang akan diuji.
Anda harus menyertakan string berikut: 

.trafficmanager.net

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profil
Menentukan profil Azure tempat cmdlet ini dibaca. Jika Anda tidak menentukan profil, cmdlet ini akan dibaca dari profil default lokal.

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

### System.Boolean
Cmdlet ini menghasilkan $True atau $False.
Jika nama domain tersedia, cmdlet ini mengembalikan nilai $True.

## CATATAN

## RELATED LINKS

