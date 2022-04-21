---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.Network.dll-Help.xml
ms.assetid: A34A2B01-A658-410E-8B68-98A6427DFC33
online version: ''
schema: 2.0.0
ms.openlocfilehash: e8ccdb8443c1ec201eb27522c5e512827db72fff
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142787050"
---
# Set-AzureVNetGatewayDefaultSite

## SYNOPSIS
Mengatur situs default untuk lalu lintas terowongan paksa.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Set-AzureVNetGatewayDefaultSite -VNetName <String> -DefaultSite <String> [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureVNetGatewayDefaultSite** mengatur rute default ke situs lokal untuk lalu lintas terowongan paksa.
Perintah ini mengatur rute di gateway jaringan privat virtual (VPN) Azure untuk jaringan virtual.

## EXAMPLES

## PARAMETERS

### -DefaultSite
Menentukan nama situs jaringan lokal lokal untuk lalu lintas terowongan paksa.

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
Cmdlet ini mengatur rute default gateway VPN untuk lalu lintas terowongan paksa untuk jaringan virtual yang ditentukan parameter ini.

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

[Hapus-AzureVNetGatewayDefaultSite](./Remove-AzureVNetGatewayDefaultSite.md)
