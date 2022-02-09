---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: C868DFA4-8A9D-4108-B88B-ACD7F100A63C
online version: https://docs.microsoft.com/powershell/module/az.network/add-azrouteconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Add-AzRouteConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Add-AzRouteConfig.md
ms.openlocfilehash: 4bfaa542dee8b44e5d5900fe67f115ccbd09002e
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138264828"
---
# Add-AzRouteConfig

## SYNOPSIS
Menambahkan rute ke tabel rute.

## SYNTAX

```
Add-AzRouteConfig -RouteTable <PSRouteTable> [-Name <String>] [-AddressPrefix <String>] [-NextHopType <String>]
 [-NextHopIpAddress <String>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Add-AzRouteConfig** menambahkan rute ke tabel rute Azure.

## EXAMPLES

### Contoh 1: Menambahkan rute ke tabel rute
```powershell
PS C:\>$RouteTable = Get-AzRouteTable -ResourceGroupName "ResourceGroup11" -Name "RouteTable01"
PS C:\> Add-AzRouteConfig -Name "Route13" -AddressPrefix 10.3.0.0/16 -NextHopType "VnetLocal" -RouteTable $RouteTable
```

Perintah pertama mendapatkan tabel rute bernama RouteTable01 dengan menggunakan cmdlet Get-AzRouteTable cmdlet.
Perintah menyimpan tabel di dalam $RouteTable tabel.
Perintah kedua menambahkan rute bernama Route13 ke tabel rute yang disimpan di $RouteTable.
Rute ini meneruskan paket ke jaringan virtual lokal.

### Contoh 2: Menambahkan rute ke tabel rute dengan menggunakan saluran
```powershell
PS C:\>Get-AzRouteTable -ResourceGroupName "ResourceGroup11" -Name "RouteTable01" | Add-AzRouteConfig -Name "Route02" -AddressPrefix 10.2.0.0/16 -NextHopType VnetLocal | Set-AzRouteTable
Name              : routetable01
ResourceGroupName : ResourceGroup11
Location          : eastus
Id                : /subscriptions/xxxx-xxxx-xxxx-xxxx/resourceGroups/ResourceGroup11/providers/Microsoft.Networ
                    k/routeTables/routetable01
Etag              : W/"f13e1bc8-d41f-44d0-882d-b8b5a1134f59"
ProvisioningState : Succeeded
Tags              : 
Routes            : [
                      {
                        "Name": "route07",
                        "Etag": "W/\"f13e1bc8-d41f-44d0-882d-b8b5a1134f59\"",
                        "Id": "/subscriptions/xxxx-xxxx-xxxx-xxxx/resourceGroups/ResourceGroup11/providers/Micro
                    soft.Network/routeTables/routetable01/routes/route07",
                        "AddressPrefix": "10.1.0.0/16",
                        "NextHopType": "VnetLocal",
                        "NextHopIpAddress": null, 
                        "ProvisioningState": "Succeeded"
                      },
                      {
                        "Name": "route02",
                        "Etag": "W/\"f13e1bc8-d41f-44d0-882d-b8b5a1134f59\"",
                        "Id": "/subscriptions/xxxx-xxxx-xxxx-xxxx/resourceGroups/ResourceGroup11/providers/Micro
                    soft.Network/routeTables/routetable01/routes/route02",
                        "AddressPrefix": "10.2.0.0/16",
                        "NextHopType": "VnetLocal",
                        "NextHopIpAddress": null, 
                        "ProvisioningState": "Succeeded"
                      },
                      {
                        "Name": "route13",
                        "Etag": null, 
                        "Id": null, 
                        "AddressPrefix": "10.3.0.0/16",
                        "NextHopType": "VnetLocal",
                        "NextHopIpAddress": null, 
                        "ProvisioningState": null
                      }
                    ] 
Subnets           : []
```

Perintah ini mendapatkan tabel rute bernama RouteTable01 dengan menggunakan **Get-AzRouteTable**.
Perintah itu meneruskan tabel itu ke cmdlet saat ini dengan menggunakan operator pipeline.
Cmdlet saat ini menambahkan rute bernama Route02, lalu meneruskan hasilnya ke cmdlet **Set-AzRouteTable** , yang memperbarui tabel agar mencerminkan perubahan Anda.

### Contoh 3: Menambahkan rute dengan Tag Layanan ke tabel rute (Pratinjau Publik)
```powershell
PS C:\>$RouteTable = Get-AzRouteTable -ResourceGroupName "ResourceGroup11" -Name "RouteTable01"
PS C:\> Add-AzRouteConfig -Name "Route13" -AddressPrefix "AppService" -NextHopType "VirtualAppliance" -NextHopIpAddress "10.0.2.4" -RouteTable $RouteTable
```

Perintah pertama mendapatkan tabel rute bernama RouteTable01 dengan menggunakan cmdlet Get-AzRouteTable cmdlet.
Perintah menyimpan tabel di dalam $RouteTable tabel.
Perintah kedua menambahkan rute bernama Route13 ke tabel rute yang disimpan di $RouteTable.
Ini merutekan lalu lintas ke prefiks IP yang terdapat dalam Tag AppService Service untuk alat virtual. 

## PARAMETERS

### -AddressPrefix
Menentukan tujuan, dalam format Classless Interdomain Routing (CIDR), ke mana rute tersebut diterapkan. Anda juga bisa menentukan Tag Layanan di sini (fitur ini berada di Pratinjau Publik).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Menentukan nama rute untuk ditambahkan ke tabel rute.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NextHopIpAddress
Menentukan alamat IP dari alat virtual yang Anda tambahkan ke jaringan virtual Azure Anda.
Ini merutekan paket ke alamat itu.
Tentukan parameter ini hanya jika Anda menentukan nilai VirtualAppliance untuk parameter *NextHopType* .

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NextHopType
Menentukan cara rute ini meneruskan paket.
Nilai yang dapat diterima untuk parameter ini adalah:
- Internet.
Gateway internet default yang disediakan oleh Azure. 
- Tidak ada.
Jika Anda menentukan nilai ini, rute tidak meneruskan paket. 
- VirtualAppliance.
Sebuah alat virtual yang Anda tambahkan ke jaringan virtual Azure Anda. 
- VirtualNetworkGateway.
Gateway jaringan privat virtual Azure server-ke-server. 
- VnetLocal.
Jaringan virtual lokal.
Jika Anda memiliki dua subnet, 10.1.0.0/16 dan 10.2.0.0/16 di jaringan virtual yang sama, pilih nilai VnetLocal untuk setiap subnet untuk diteruskan ke subnet lain.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RouteTable
Menentukan tabel rute yang menambahkan rute ke cmdlet ini.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSRouteTable
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak berjalan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Network.Models.PSRouteTable

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSRouteTable

## CATATAN

## RELATED LINKS

[Get-AzRouteConfig](./Get-AzRouteConfig.md)

[Get-AzRouteTable](./Get-AzRouteTable.md)

[New-AzRouteConfig](./New-AzRouteConfig.md)

[Remove-AzRouteConfig](./Remove-AzRouteConfig.md)

[Set-AzRouteConfig](./Set-AzRouteConfig.md)

[Set-AzRouteTable](./Set-AzRouteTable.md)


