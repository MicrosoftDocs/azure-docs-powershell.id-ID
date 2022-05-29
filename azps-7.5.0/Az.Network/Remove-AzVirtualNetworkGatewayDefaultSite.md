---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: 65E9C4D5-4D2C-4039-A87B-4E693B97C4CB
online version: https://docs.microsoft.com/powershell/module/az.network/remove-azvirtualnetworkgatewaydefaultsite
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Remove-AzVirtualNetworkGatewayDefaultSite.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Remove-AzVirtualNetworkGatewayDefaultSite.md
ms.openlocfilehash: 705913116b3ab0366be195c36498c1d475657f42
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145668640"
---
# Remove-AzVirtualNetworkGatewayDefaultSite

## SYNOPSIS
Menghapus situs default dari gateway jaringan virtual.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.network/remove-azvirtualnetworkgatewaydefaultsite) untuk informasi terbaru.

## SYNTAX

```
Remove-AzVirtualNetworkGatewayDefaultSite -VirtualNetworkGateway <PSVirtualNetworkGateway>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzVirtualNetworkGatewayDefaultSite** menghapus situs default penerowongan paksa dari gateway jaringan virtual.
Penerowongan paksa menyediakan cara bagi Anda untuk mengalihkan lalu lintas yang terikat Internet dari komputer virtual Azure ke jaringan lokal Anda; ini memungkinkan Anda memeriksa dan mengaudit lalu lintas sebelum merilisnya.
Penerowongan paksa dilakukan dengan menggunakan terowongan jaringan privat maya (VPN) ; terowongan ini memerlukan situs default, gateway lokal tempat semua lalu lintas terikat Internet Azure dialihkan.
**Remove-AzVirtualNetworkGatewayDefaultSite** menghapus situs default yang ditetapkan ke gateway.
Jika Anda melakukan ini, Anda harus menggunakan Set-AzVirtualNetworkGatewayDefaultSite untuk menetapkan situs default baru sebelum gateway dapat digunakan untuk penerowongan paksa.

## EXAMPLES

### Contoh 1: Menghapus situs default yang ditetapkan ke gateway jaringan virtual
```powershell
$Gateway = Get-AzVirtualNetworkGateway -Name "ContosoVirtualGateway"
Remove-AzVirtualNetworkGatewayDefaultSite -VirtualNetworkGateway $Gateway
```

Contoh ini menghapus situs default yang saat ini ditetapkan ke gateway jaringan virtual bernama ContosoVirtualGateway.
Perintah pertama menggunakan **Get-AzVirtualNetworkGateway** untuk membuat referensi objek ke gateway; referensi objek ini disimpan dalam variabel bernama $Gateway.
Perintah kedua kemudian menggunakan **Remove-AzVirtualNetworkGatewayDefaultSite** untuk menghapus situs default yang ditetapkan ke gateway tersebut.

## PARAMETERS

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

### -VirtualNetworkGateway
Menentukan referensi objek ke gateway jaringan virtual yang berisi situs default yang akan dihapus.
Anda bisa membuat referensi objek ke gateway jaringan virtual dengan menggunakan Get-AzVirtualNetworkGateway dan menentukan nama gateway.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSVirtualNetworkGateway
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Network.Models.PSVirtualNetworkGateway

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSVirtualNetworkGateway

## NOTES

## RELATED LINKS

[Dapatkan-AzVirtualNetworkGateway](./Get-AzVirtualNetworkGateway.md)

[Set-AzVirtualNetworkGatewayDefaultSite](./Set-AzVirtualNetworkGatewayDefaultSite.md)


