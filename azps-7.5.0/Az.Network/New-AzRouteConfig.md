---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: 356764CF-A860-432A-907A-9058CEB2BF8E
online version: https://docs.microsoft.com/powershell/module/az.network/new-azrouteconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzRouteConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzRouteConfig.md
ms.openlocfilehash: 22defa50cbf2f4fd300bece9acce16ad8d4b133a
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145673500"
---
# New-AzRouteConfig

## SYNOPSIS
Membuat rute untuk tabel rute.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.network/new-azrouteconfig) untuk informasi terbaru.

## SYNTAX

```
New-AzRouteConfig [-Name <String>] [-AddressPrefix <String>] [-NextHopType <String>]
 [-NextHopIpAddress <String>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzRouteConfig** membuat rute untuk tabel rute Azure.

## EXAMPLES

### Contoh 1: Membuat rute
```powershell
$Route = New-AzRouteConfig -Name "Route07" -AddressPrefix 10.1.0.0/16 -NextHopType "VnetLocal"
$Route
```

```output
Name              : Route07
Id                : 
Etag              : 
ProvisioningState : 
AddressPrefix     : 10.1.0.0/16
NextHopType       : VnetLocal
NextHopIpAddress  :
```

Perintah pertama membuat rute bernama Route07, lalu menyimpannya dalam variabel $Route.
Rute ini meneruskan paket ke jaringan virtual lokal.
Perintah kedua menampilkan properti rute.

### Contoh 2

Membuat rute untuk tabel rute. (dibuat otomatis)

<!-- Aladdin Generated Example -->
```powershell
New-AzRouteConfig -AddressPrefix 10.1.0.0/16 -Name 'Route07' -NextHopIpAddress '12.0.0.5' -NextHopType 'VnetLocal'
```

### Contoh 3: Membuat rute dengan Tag Layanan (Pratinjau Umum)
```powershell
New-AzRouteConfig -Name "Route07" -AddressPrefix "AppService" -NextHopType "VirtualAppliance" -NextHopIpAddress "10.0.2.4"
```

Perintah ini membuat rute bernama Route07 yang meneruskan lalu lintas ke awalan IP yang terkandung dalam Tag Layanan AppService ke appliance virtual. 

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
Menentukan nama untuk rute.

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
Menentukan alamat IP appliance virtual yang Anda tambahkan ke jaringan Azurevirtual Anda.
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

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSRoute

## NOTES

## RELATED LINKS

[New-AzRouteConfig](./Add-AzRouteConfig.md)

[Get-AzRouteConfig](./Get-AzRouteConfig.md)

[Remove-AzRouteConfig](./Remove-AzRouteConfig.md)

[Set-AzRouteConfig](./Set-AzRouteConfig.md)


