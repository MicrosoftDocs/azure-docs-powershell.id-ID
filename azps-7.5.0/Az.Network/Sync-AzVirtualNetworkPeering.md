---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/sync-azvirtualnetworkpeering
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Sync-AzVirtualNetworkPeering.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Sync-AzVirtualNetworkPeering.md
ms.openlocfilehash: 7571d002439336c92c19a9849ca7e0b9fa41f97f
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145664248"
---
# Sync-AzVirtualNetworkPeering

## SYNOPSIS
Perintah untuk menyinkronkan ruang alamat pada tautan peering jika jaringan virtual jarak jauh memiliki ruang alamat baru.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.network/sync-azvirtualnetworkpeering) untuk informasi terbaru.

## SYNTAX

### Bidang
```
Sync-AzVirtualNetworkPeering -VirtualNetworkName <String> -ResourceGroupName <String> -Name <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### Objek
```
Sync-AzVirtualNetworkPeering -VirtualNetworkPeering <PSVirtualNetworkPeering>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Memperbarui ruang alamat pada jaringan virtual yang di-peering sekarang didukung. Namun, untuk menyinkronkan ruang alamat terbaru pada tautan peering, commandlet ini perlu dipanggil pada jaringan virtual jarak jauh (peered). Ketika dipanggil, itu akan menyinkronkan ruang alamat pada tautan peering dengan ruang alamat terbaru dari jaringan virtual jarak jauh (peered).

## EXAMPLES

### Contoh 1
```powershell
Sync-AzVirtualNetworkPeering -Name 'peering2' -VirtualNetworkName 'vnet1' -ResourceGroupName 'rg1'
```

Menyinkronkan ruang alamat pada peering, peering2 di jaringan virtual, vnet1 dalam grup sumber daya, rg1.

### Contoh 2
```powershell
$s1h1 = Get-AzVirtualNetworkPeering -Name 'spoke1-hub1' -VirtualNetworkName 'spoke1' -ResourceGroupName 'HUB1-RG'
$s1h1 | Sync-AzVirtualNetworkPeering
```

Commandlet pertama mendapatkan peering jaringan virtual. Commandlet piped kedua menerapkan operasi sinkronisasi pada peering.

## PARAMETERS

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

### -Name
Nama peering jaringan virtual.

```yaml
Type: System.String
Parameter Sets: Fields
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: Fields
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VirtualNetworkName
Nama jaringan virtual.

```yaml
Type: System.String
Parameter Sets: Fields
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VirtualNetworkPeering
Peering jaringan virtual

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSVirtualNetworkPeering
Parameter Sets: Object
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

### Microsoft.Azure.Commands.Network.Models.PSVirtualNetworkPeering

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSVirtualNetworkPeering

## NOTES

## RELATED LINKS

[Add-AzVirtualNetworkPeering](./Add-AzVirtualNetworkPeering.md)

[Get-AzVirtualNetworkPeering](./Get-AzVirtualNetworkPeering.md)

[Remove-AzVirtualNetworkPeering](./Remove-AzVirtualNetworkPeering.md)

[Set-AzVirtualNetworkPeering](./Set-AzVirtualNetworkPeering.md)
