---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/add-azvirtualhubroutetable
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Add-AzVirtualHubRouteTable.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Add-AzVirtualHubRouteTable.md
ms.openlocfilehash: 6ff07fa6890bfcaac5cda4efe448c5601b295721
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144730652"
---
# Add-AzVirtualHubRouteTable

## SYNOPSIS
Membuat sumber daya Tabel Rute Hub Virtual yang merupakan anak dari VirtualHub.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.network/add-azvirtualhubroutetable) untuk informasi terbaru.

## SYNTAX

```
Add-AzVirtualHubRouteTable -Name <String> -Route <PSVirtualHubRoute[]> -Connection <String[]>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Sumber daya tabel rute hub virtual berisi daftar rute dan daftar koneksi yang dapat dilampirkan dan digunakan untuk merutekan lalu lintas di Hub Virtual.

## EXAMPLES

### Contoh 1
```powershell
$route1 = Add-AzVirtualHubRoute -DestinationType "CIDR" -Destination @("10.4.0.0/16", "10.5.0.0/16") -NextHopType "IPAddress" -NextHop @("10.0.0.68")
Add-AzVirtualHubRouteTable -Route @($route1) -Connection @("All_Vnets") -Name "routeTable1"
```

```output
Name                : routeTable1
Id                  :
Routes              : {Microsoft.Azure.Commands.Network.Models.PSVirtualHubRoute}
Connections : {All_Vnets}
ProvisioningState   :
```

Perintah di atas akan membuat sumber daya Tabel Rute Hub Virtual dari rute yang diteruskan ke dalamnya dan objek ini dapat digunakan untuk merutekan lalu lintas di Hub Virtual.

## PARAMETERS

### -Koneksi
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

### -Name
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

### -Rute
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSVirtualHubRouteTable

## NOTES

## RELATED LINKS
