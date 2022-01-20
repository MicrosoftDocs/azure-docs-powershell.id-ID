---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/add-azvirtualhubroutetable
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Add-AzVirtualHubRouteTable.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Add-AzVirtualHubRouteTable.md
ms.openlocfilehash: 89790792c0f35275e6999c02620fe7b6e1bf060e
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136354446"
---
# Add-AzVirtualHubRouteTable

## SYNOPSIS
Membuat sumber daya Tabel Rute Virtual Hub yang merupakan anak dari VirtualHub.

## SYNTAX

```
Add-AzVirtualHubRouteTable -Name <String> -Route <PSVirtualHubRoute[]> -Connection <String[]>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Sumber daya tabel rute hub virtual berisi daftar rute dan daftar koneksi yang dapat dilampirkan dan digunakan untuk merutekan lalu lintas di Virtual Hub.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> $route1 = Add-AzVirtualHubRoute -DestinationType "CIDR" -Destination @("10.4.0.0/16", "10.5.0.0/16") -NextHopType "IPAddress" -NextHop @("10.0.0.68")
PS C:\> Add-AzVirtualHubRouteTable -Route @($route1) -Connection @("All_Vnets") -Name "routeTable1"

Name                : routeTable1
Id                  :
Routes              : {Microsoft.Azure.Commands.Network.Models.PSVirtualHubRoute}
Connections : {All_Vnets}
ProvisioningState   :
```

Perintah di atas akan membuat sumber daya Tabel Rute Virtual Hub dari rute yang dilewatinya dan objek ini bisa digunakan untuk merutekan lalu lintas di Virtual Hub.

## PARAMETERS

### -Connection
Daftar koneksi yang dilampirkan tabel rute ini.

```yaml
Type: String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama tabel rute.

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

### -Route
Daftar rute hub virtual.

```yaml
Type: PSVirtualHubRoute[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSVirtualHubRouteTable

## CATATAN

## RELATED LINKS
