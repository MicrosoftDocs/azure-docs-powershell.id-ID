---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: C868DFA4-8A9D-4108-B88B-ACD7F100A63C
online version: https://docs.microsoft.com/powershell/module/az.network/add-azrouteconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Add-AzRouteConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Add-AzRouteConfig.md
ms.openlocfilehash: bb389e63e1332fa263655e49821f0f8abfa6512e
ms.sourcegitcommit: 321c644cf2161807a71e1af318fc5c5311d22e25
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/25/2022
ms.locfileid: "145803030"
---
# New-AzRouteConfig

## SYNOPSIS
Menambahkan rute ke tabel rute.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.network/add-azrouteconfig) untuk informasi terbaru.

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
$RouteTable = Get-AzRouteTable -ResourceGroupName "ResourceGroup11" -Name "RouteTable01"
Add-AzRouteConfig -Name "Route13" -AddressPrefix 10.3.0.0/16 -NextHopType "VnetLocal" -RouteTable $RouteTable
```

Perintah pertama mendapatkan tabel rute bernama RouteTable01 dengan menggunakan cmdlet Get-AzRouteTable.
Perintah menyimpan tabel dalam variabel $RouteTable.
Perintah kedua menambahkan rute bernama Route13 ke tabel rute yang disimpan di $RouteTable.
Rute ini meneruskan paket ke jaringan virtual lokal.

### Contoh 2: Menambahkan rute ke tabel rute dengan menggunakan alur
```powershell
Get-AzRouteTable -ResourceGroupName "ResourceGroup11" -Name "RouteTable01" | Add-AzRouteConfig -Name "Route02" -AddressPrefix 10.2.0.0/16 -NextHopType VnetLocal | Set-AzRouteTable
```

```output
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
Perintah meneruskan tabel tersebut ke cmdlet saat ini dengan menggunakan operator alur.
Cmdlet saat ini menambahkan rute bernama Route02, lalu meneruskan hasilnya ke cmdlet **Set-AzRouteTable** , yang memperbarui tabel untuk mencerminkan perubahan Anda.

### Contoh 3: Menambahkan rute dengan Tag Layanan ke tabel rute (Pratinjau Umum)
```powershell
$RouteTable = Get-AzRouteTable -ResourceGroupName "ResourceGroup11" -Name "RouteTable01"
Add-AzRouteConfig -Name "Route13" -AddressPrefix "AppService" -NextHopType "VirtualAppliance" -NextHopIpAddress "10.0.2.4" -RouteTable $RouteTable
```

Perintah pertama mendapatkan tabel rute bernama RouteTable01 dengan menggunakan cmdlet Get-AzRouteTable.
Perintah menyimpan tabel dalam variabel $RouteTable.
Perintah kedua menambahkan rute bernama Route13 ke tabel rute yang disimpan di $RouteTable.
Rute ini meneruskan lalu lintas ke prefiks IP yang terkandung dalam Tag Layanan AppService ke appliance virtual. 

## PARAMETERS

### -AddressPrefix
Menentukan tujuan, dalam format Classless Interdomain Routing (CIDR), tempat rute diterapkan. Anda juga dapat menentukan Tag Layanan di sini (fitur ini ada di Pratinjau Umum).

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
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

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

### -Name
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
Menentukan alamat IP appliance virtual yang Anda tambahkan ke jaringan virtual Azure Anda.
Rute ini meneruskan paket ke alamat tersebut.
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
Menentukan bagaimana rute ini meneruskan paket.
Nilai yang dapat diterima untuk parameter ini adalah:
- Internet.
Gateway Internet default yang disediakan oleh Azure. 
- Tidak ada.
Jika Anda menentukan nilai ini, rute tidak meneruskan paket. 
- VirtualAppliance.
Appliance virtual yang Anda tambahkan ke jaringan virtual Azure Anda. 
- VirtualNetworkGateway.
Gateway jaringan privat virtual server-ke-server Azure. 
- VnetLocal.
Jaringan virtual lokal.
Jika Anda memiliki dua subnet, 10.1.0.0/16 dan 10.2.0.0/16 di jaringan virtual yang sama, pilih nilai VnetLocal untuk setiap subnet untuk diteruskan ke subnet lainnya.

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
Menentukan tabel rute tempat cmdlet ini menambahkan rute.

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

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

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
Menunjukkan yang akan terjadi jika cmdlet dijalankan. Cmdlet tidak dijalankan.

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

## NOTES

## RELATED LINKS

[Get-AzRouteConfig](./Get-AzRouteConfig.md)

[Get-AzRouteTable](./Get-AzRouteTable.md)

[New-AzRouteConfig](./New-AzRouteConfig.md)

[Remove-AzRouteConfig](./Remove-AzRouteConfig.md)

[Set-AzRouteConfig](./Set-AzRouteConfig.md)

[New-AzRouteTable](./Set-AzRouteTable.md)


