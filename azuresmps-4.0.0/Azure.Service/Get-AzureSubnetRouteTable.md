---
external help file: Microsoft.WindowsAzure.Commands.ServiceManagement.Network.dll-Help.xml
ms.assetid: AEFC9094-144F-4E29-AC5A-DBFDA175A920
online version: ''
schema: 2.0.0
ms.openlocfilehash: dacf1d0f458cd489140a90ebc93053326f245f67
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142313368"
---
# Get-AzureSubnetRouteTable

## SYNOPSIS
Mendapatkan tabel rute untuk subnet.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureSubnetRouteTable -VirtualNetworkName <String> -SubnetName <String> [-Detailed]
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureSubnetRouteTable** mendapatkan tabel rute yang terkait dengan subnet.

## EXAMPLES

### Contoh 1: Menampilkan rute untuk subnet
```
PS C:\> Get-AzureSubnetRouteTable -VirtualNetworkName "VNetUSCentral" -SubnetName "ContosoSubnet" -Detailed
Routes                        Name                          Location                      Label
------                        ----                          --------                      -----
{internetroute}               PublicRT                      Central US                    Sample RT in Central US
```

Perintah ini menampilkan rute dalam nama tabel rute yang terkait dengan subnet bernama ContosoSubnet.

## PARAMETERS

### -Detail
Menunjukkan bahwa cmdlet ini menampilkan rute dalam tabel rute yang terkait dengan subnet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
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

### -SubnetName
Menentukan subnet tempat cmdlet ini mendapatkan tabel rute.

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

### -VirtualNetworkName
Menentukan nama jaringan virtual yang berisi subnet tempat cmdlet ini mendapatkan tabel rute.

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

[Hapus-AzureSubnetRouteTable](./Remove-AzureSubnetRouteTable.md)

[Set-AzureSubnetRouteTable](./Set-AzureSubnetRouteTable.md)


