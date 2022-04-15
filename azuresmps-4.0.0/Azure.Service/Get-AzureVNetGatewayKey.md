---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.Network.dll-Help.xml
ms.assetid: 8AD101BA-9275-4B2B-BB31-99FC34B8D1E8
online version: ''
schema: 2.0.0
ms.openlocfilehash: e275633edc444afd9d98b7bc605f8c4593ceafbc
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142313306"
---
# Get-AzureVNetGatewayKey

## SYNOPSIS
Mendapatkan kunci pra-berbagi untuk koneksi antara gateway jaringan virtual dan situs jaringan lokal.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureVNetGatewayKey -VNetName <String> -LocalNetworkSiteName <String> [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureVNetGatewayKey** mendapatkan kunci yang telah dibagikan sebelumnya untuk koneksi antara gateway jaringan virtual dan situs jaringan lokal.

## EXAMPLES

## PARAMETERS

### -LocalNetworkSiteName
Menentukan nama situs jaringan lokal yang tersambung ke gateway jaringan virtual.

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

### -VNetName
Menentukan jaringan virtual di mana cmdlet ini mendapatkan kunci bersama untuk koneksi.

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

## CATATAN

## RELATED LINKS

[Set-AzureVNetGatewayKey](./Set-AzureVNetGatewayKey.md)


