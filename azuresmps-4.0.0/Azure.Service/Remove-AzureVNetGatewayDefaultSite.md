---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.Network.dll-Help.xml
ms.assetid: 67260128-D57B-4587-BB61-2475703ABA66
online version: ''
schema: 2.0.0
ms.openlocfilehash: 3b2facf26db2c1e81cc912bcaa95e9888c2825f87a7598bec31adb7986a8ad09
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132415363"
---
# Remove-AzureVNetGatewayDefaultSite

## SYNOPSIS
Menghapus rute default untuk lalu lintas paksa.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Remove-AzureVNetGatewayDefaultSite -VNetName <String> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzureVNetGatewayDefaultSite** menghapus rute default ke situs lokal untuk lalu lintas paksa.
Cmdlet ini menghapus rute dari gateway Jaringan privat virtual Azure (VPN) untuk jaringan virtual.

## EXAMPLES

### Contoh 1: Menghapus rute ke situs default
```
PS C:\> Remove-AzureVNetGatewayDefaultSite -VnetName "ContosoVNet01"
```

Perintah ini akan menghapus rute ke situs default dari VPN jaringan virtual bernama ContosoVNet01.

## PARAMETERS

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

### -VNetName
Menentukan jaringan virtual.
Cmdlet ini menghapus rute default dari gateway VPN untuk jaringan virtual yang ditentukan parameter ini.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Set-AzureVNetGatewayDefaultSite](./Set-AzureVNetGatewayDefaultSite.md)
