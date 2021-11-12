---
external help file: Microsoft.WindowsAzure.Commands.TrafficManager.dll-Help.xml
ms.assetid: 92E2409B-14BC-428F-8BAF-60D8DAFA5F57
online version: ''
schema: 2.0.0
ms.openlocfilehash: 78c2a280e77ce4c9d85263e6213149904223dd4b139cf912f345a1aeb4ca0a23
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132417668"
---
# Test-AzureTrafficManagerDomainName

## SYNOPSIS
Memeriksa apakah nama domain tersedia sebagai Traffic Manager profil.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Test-AzureTrafficManagerDomainName -DomainName <String> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Test-AzureTrafficManagerDomainName** memeriksa apakah nama domain tersedia sebagai profil Microsoft Azure Traffic Manager Anda.
Jika nama domain tersedia, cmdlet ini akan mengembalikan nilai $True.

## EXAMPLES

### Contoh 1: Periksa apakah nama domain tersedia
```
PS C:\>Test-AzureTrafficManagerDomainName -DomainName "ContosoApp.trafficmanager.net"
$True
```

Perintah ini akan memeriksa apakah nama domain ContosoApp.trafficmanager.net tersedia sebagai Traffic Manager profil.

## PARAMETERS

### -DomainName
Menentukan nama domain untuk diuji.
Anda harus menyertakan string berikut ini: 

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
Menentukan profil Azure yang akan dibaca cmdlet ini. Jika Anda tidak menentukan profil, cmdlet ini akan membaca dari profil default lokal.

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

### System.Boolean
Cmdlet ini menghasilkan $True atau $False.
Jika nama domain tersedia, cmdlet ini akan mengembalikan nilai $True.

## CATATAN

## RELATED LINKS

