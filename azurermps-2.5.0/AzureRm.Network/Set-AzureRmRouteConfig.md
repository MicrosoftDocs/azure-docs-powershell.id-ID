---
external help file: Microsoft.Azure.Commands.Network.dll-Help.xml
Module Name: AzureRM.Network
ms.assetid: 6E967F9C-949E-4485-9B57-FC4F523D5DC9
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.network/set-azurermrouteconfig
schema: 2.0.0
ms.openlocfilehash: 3a7187afe4995a14deea0888caac5c7a06b35e2c4d2d1c9c6bbc274d65f75d9f
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132418933"
---
# Set-AzureRmRouteConfig

## SYNOPSIS
Menetapkan status tujuan untuk rute.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Set-AzureRmRouteConfig -RouteTable <PSRouteTable> [-AddressPrefix <String>] [-NextHopType <String>]
 [-NextHopIpAddress <String>] [-Name <String>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzureRmRouteConfig** mengatur status tujuan untuk rute Azure.

## EXAMPLES

### Contoh 1: Mengubah rute
```
PS C:\>Get-AzureRmRouteTable -ResourceGroupName "ResourceGroup11" -Name "RouteTable01" | Set-AzureRmRouteConfig -Name "Route02" -AddressPrefix 10.4.0.0/16 -NextHopType VnetLocal | Set-AzureRmRouteTable
Name              : Routetable01
ResourceGroupName : ResourceGroup11
Location          : eastus
Id                : /subscriptions/xxxx-xxxx-xxxx-xxxx/resourceGroups/ResourceGroup11/providers/Microsoft.Networ
                    k/routeTables/RouteTable01
Etag              : W/"58c2922e-9efe-4554-a457-956ef44bc718"
ProvisioningState : Succeeded
Tags              : 
Routes            : [
                      {
                        "Name": "Route07",
                        "Etag": "W/\"58c2922e-9efe-4554-a457-956ef44bc718\"",
                        "Id": "/subscriptions/xxxx-xxxx-xxxx-xxxx/resourceGroups/ResourceGroup11/providers/Micro
                    soft.Network/routeTables/Routetable01/routes/Route07",
                        "AddressPrefix": "10.1.0.0/16",
                        "NextHopType": "VnetLocal",
                        "NextHopIpAddress": null, 
                        "ProvisioningState": "Succeeded"
                      },
                      {
                        "Name": "route02",
                        "Etag": "W/\"58c2922e-9efe-4554-a457-956ef44bc718\"",
                        "Id": "/subscriptions/xxxx-xxxx-xxxx-xxxx/resourceGroups/ResourceGroup11/providers/Micro
                    soft.Network/routeTables/routetable01/routes/route02",
                        "AddressPrefix": "10.4.0.0/16",
                        "NextHopType": "VnetLocal",
                        "NextHopIpAddress": null, 
                        "ProvisioningState": "Succeeded"
                      }
                    ] 
Subnets           : []
```

Perintah ini mendapatkan tabel rute yang bernama RouteTable01 dengan menggunakan cmdlet Get-AzureRmRouteTable cmdlet.
Perintah itu meneruskan tabel itu ke cmdlet saat ini dengan menggunakan operator pipeline.
Cmdlet saat ini mengubah rute yang bernama Route02, lalu meneruskan hasilnya ke cmdlet **Set-AzureRmRouteTable,** yang memperbarui tabel agar mencerminkan perubahan Anda.

## PARAMETERS

### -AddressPrefix
Menentukan tujuan, dalam format Classless Interdomain Routing (CIDR), ke mana rute tersebut diterapkan.

```yaml
Type: String
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
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Menentukan nama rute yang akan memodifikasi cmdlet ini.

```yaml
Type: String
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
Tentukan parameter ini hanya jika Anda menentukan nilai VirtualAppliance untuk parameter *NextHopType.*

```yaml
Type: String
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
Gateway jaringan privat virtual Azureserver-to-server. 
- VnetLocal.
Jaringan virtual lokal.
Jika Anda memiliki dua subnet, 10.1.0.0/16 dan 10.2.0.0/16 di jaringan virtual yang sama, pilih nilai VnetLocal untuk setiap subnet untuk diteruskan ke subnet lain.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -RouteTable
Menentukan tabel rute yang terkait dengan rute ini.

```yaml
Type: PSRouteTable
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
Type: SwitchParameter
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
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### PSRouteTable
Parameter 'RouteTable' menerima nilai tipe 'PSRouteTable' dari saluran

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSRouteTable

## CATATAN

## RELATED LINKS

[Add-AzureRmRouteConfig](./Add-AzureRmRouteConfig.md)

[Get-AzureRmRouteConfig](./Get-AzureRmRouteConfig.md)

[New-AzureRmRouteConfig](./New-AzureRmRouteConfig.md)

[Remove-AzureRmRouteConfig](./Remove-AzureRmRouteConfig.md)


