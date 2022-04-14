---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/new-azapplicationgatewayconnectiondraining
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzApplicationGatewayConnectionDraining.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzApplicationGatewayConnectionDraining.md
ms.openlocfilehash: 90f10d5fd4c444e28f576a60508be1fca5382a9f
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142176697"
---
# New-AzApplicationGatewayConnectionDraining

## SYNOPSIS
Membuat konfigurasi pengeringan koneksi baru untuk pengaturan HTTP ujung-belakang.

## SYNTAX

```
New-AzApplicationGatewayConnectionDraining -Enabled <Boolean> -DrainTimeoutInSec <Int32>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzApplicationGatewayConnectionDraining** membuat konfigurasi pengeringan koneksi baru untuk pengaturan HTTP ujung belakang.

## EXAMPLES

### Contoh 1
```powershell
$connectionDraining = New-AzApplicationGatewayConnectionDraining -Enabled $True -DrainTimeoutInSec 42
```

Perintah membuat konfigurasi pengurasan koneksi baru dengan Diaktifkan diatur ke True dan DrainTimeoutInSec diatur ke 42 detik dan menyimpannya di $connectionDraining.

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

### -DrainTimeoutInSec
Jumlah detik pengurasan koneksi aktif.
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

### -Difungsikan
Apakah koneksi menguras daya diaktifkan atau tidak.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayConnectionDraining

## CATATAN

## RELATED LINKS

[Get-AzApplicationGatewayConnectionDraining](./Get-AzApplicationGatewayConnectionDraining.md)

[Remove-AzApplicationGatewayConnectionDraining](./Remove-AzApplicationGatewayConnectionDraining.md)

[Set-AzApplicationGatewayConnectionDraining](./Set-AzApplicationGatewayConnectionDraining.md)

