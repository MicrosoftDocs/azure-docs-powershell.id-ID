---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.Network.dll-Help.xml
ms.assetid: 67260128-D57B-4587-BB61-2475703ABA66
online version: ''
schema: 2.0.0
ms.openlocfilehash: 2a03a09c030b1372dabda8bb8f1c50c96ceb9b31
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143103617"
---
# Remove-AzureVNetGatewayDefaultSite

## SYNOPSIS
Menghapus rute default untuk lalu lintas terowongan paksa.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Remove-AzureVNetGatewayDefaultSite -VNetName <String> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzureVNetGatewayDefaultSite** menghapus rute default ke situs lokal untuk lalu lintas terowongan paksa.
Cmdlet ini menghapus rute dari gateway jaringan privat virtual (VPN) Azure untuk jaringan virtual.

## EXAMPLES

### Contoh 1: Menghapus rute ke situs default
```
PS C:\> Remove-AzureVNetGatewayDefaultSite -VnetName "ContosoVNet01"
```

Perintah ini menghapus rute ke situs default dari VPN jaringan virtual bernama ContosoVNet01.

## PARAMETERS

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Set-AzureVNetGatewayDefaultSite](./Set-AzureVNetGatewayDefaultSite.md)
