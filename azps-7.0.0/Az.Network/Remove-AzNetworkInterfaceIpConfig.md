---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: 015C7DB7-2B08-4033-9B6E-1738D4DDACDA
online version: https://docs.microsoft.com/powershell/module/az.network/remove-aznetworkinterfaceipconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Remove-AzNetworkInterfaceIpConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Remove-AzNetworkInterfaceIpConfig.md
ms.openlocfilehash: 14cf127a239f0c953f51c2743144e2960257e87d
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136530833"
---
# Remove-AzNetworkInterfaceIpConfig

## SYNOPSIS
Menghapus konfigurasi IP antarmuka jaringan dari antarmuka jaringan.

## SYNTAX

```
Remove-AzNetworkInterfaceIpConfig -Name <String> -NetworkInterface <PSNetworkInterface>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzNetworkInterfaceIpConfig** menghapus konfigurasi IP antarmuka jaringan dari antarmuka jaringan Azure.

## EXAMPLES

### Contoh 1: Menghapus konfigurasi IP dari antarmuka jaringan
```powershell
$nic = Get-AzNetworkInterface -Name mynic -ResourceGroupName myrg

Remove-AzNetworkInterfaceIpConfig -Name IPConfig-1 -NetworkInterface $nic

Set-AzNetworkInterface -NetworkInterface $nic
```

Perintah pertama mendapatkan antarmuka jaringan yang disebut mynic dan menyimpannya dalam variabel $nic. Perintah kedua menghapus konfigurasi IP yang disebut IPConfig-1 yang terkait dengan antarmuka jaringan ini. Perintah ketiga mengatur perubahan yang dibuat pada antarmuka jaringan.

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
Menentukan nama konfigurasi IP antarmuka jaringan yang akan dihapus.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NetworkInterface
Menentukan objek **NetworkInterface.**
Objek ini berisi konfigurasi IP antarmuka jaringan yang akan dihapus.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSNetworkInterface
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Microsoft.Azure.Commands.Network.Models.PSNetworkInterface

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSNetworkInterface

## CATATAN
* Kata kunci: azure, azurerm, arm, resource, management, manager, network, networking

## RELATED LINKS

[Add-AzNetworkInterfaceIpConfig](./Add-AzNetworkInterfaceIpConfig.md)

[Get-AzNetworkInterfaceIpConfig](./Get-AzNetworkInterfaceIpConfig.md)

[New-AzNetworkInterfaceIpConfig](./New-AzNetworkInterfaceIpConfig.md)

[Set-AzNetworkInterfaceIpConfig](./Set-AzNetworkInterfaceIpConfig.md)


