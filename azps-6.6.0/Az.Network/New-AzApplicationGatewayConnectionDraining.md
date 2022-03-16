---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/new-azapplicationgatewayconnectiondraining
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzApplicationGatewayConnectionDraining.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzApplicationGatewayConnectionDraining.md
ms.openlocfilehash: ecc419d2185a6e7e6d56c22e88e0e95a6f9bb965
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140070605"
---
# New-AzApplicationGatewayConnectionDraining

## SYNOPSIS
Membuat koneksi baru dengan cepat konfigurasi untuk pengaturan HTTP ujung belakang.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.network/new-azapplicationgatewayconnectiondraining) untuk informasi terkini.

## SYNTAX

```
New-AzApplicationGatewayConnectionDraining -Enabled <Boolean> -DrainTimeoutInSec <Int32>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzApplicationGatewayConnectionD cmdlet membuat** koneksi baru yang menghabiskan konfigurasi untuk pengaturan HTTP ujung belakang.

## EXAMPLES

### Contoh 1
```
PS C:\> $connectionDraining = New-AzApplicationGatewayConnectionDraining -Enabled $True -DrainTimeoutInSec 42
```

Perintah membuat konfigurasi koneksi baru dengan Enabled yang diatur ke True dan DrainTimeoutInSec diatur ke 42 detik dan menyimpannya dalam $connectionDraining.

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

### -DrainTimeoutInSec
Jumlah koneksi detik yang menghabiskan waktu aktif.
Nilai yang dapat diterima adalah dari 1 detik hingga 3600 detik.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Enabled
Apakah penguringan koneksi diaktifkan atau tidak.

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayConnectionD adaptering

## CATATAN

## RELATED LINKS

[Get-AzApplicationGatewayConnectionDriging](./Get-AzApplicationGatewayConnectionDraining.md)

[Remove-AzApplicationGatewayConnectionDriging](./Remove-AzApplicationGatewayConnectionDraining.md)

[Set-AzApplicationGatewayConnectionDriging](./Set-AzApplicationGatewayConnectionDraining.md)

