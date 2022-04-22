---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/sync-azvirtualnetworkpeering
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Sync-AzVirtualNetworkPeering.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Sync-AzVirtualNetworkPeering.md
ms.openlocfilehash: b6291a7f2bad90336624623ef4a9ae7a35647659
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142899209"
---
# Sync-AzVirtualNetworkPeering

## SYNOPSIS
Perintah untuk menyinkronkan ruang alamat pada tautan peering jika jaringan virtual jarak jauh memiliki ruang alamat baru.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.network/sync-azvirtualnetworkpeering) untuk informasi terbaru.

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
Memperbarui ruang alamat di jaringan virtual peered kini didukung. Namun, untuk menyinkronkan ruang alamat terbaru pada tautan peering, commandlet ini perlu dipanggil di jaringan virtual jarak jauh (peered). Ketika dipanggil, itu akan menyinkronkan ruang alamat pada tautan peering dengan ruang alamat terbaru dari jaringan virtual jarak jauh (peered).

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Sync-AzVirtualNetworkPeering -Name 'peering2' -VirtualNetworkName 'vnet1' -ResourceGroupName 'rg1'
```

Menyinkronkan ruang alamat di peering, peering2 di jaringan virtual, vnet1 dalam grup sumber daya, rg1.

### Contoh 2
```powershell
PS C:\> $s1h1 = Get-AzVirtualNetworkPeering -Name 'spoke1-hub1' -VirtualNetworkName 'spoke1' -ResourceGroupName 'HUB1-RG'
PS C:\> $s1h1 | Sync-AzVirtualNetworkPeering
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

### -Nama
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

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
