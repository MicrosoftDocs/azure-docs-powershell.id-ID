---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/new-azapplicationgatewayautoscaleconfiguration
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzApplicationGatewayAutoscaleConfiguration.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzApplicationGatewayAutoscaleConfiguration.md
ms.openlocfilehash: cbf59abd53a98b792f4d37d4ec37ba919f68cb48
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144632582"
---
# New-AzApplicationGatewayAutoscaleConfiguration

## SYNOPSIS
Membuat Konfigurasi Skala Otomatis untuk Application Gateway.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.network/new-azapplicationgatewayautoscaleconfiguration) untuk informasi terbaru.

## SYNTAX

```
New-AzApplicationGatewayAutoscaleConfiguration -MinCapacity <Int32> [-MaxCapacity <Int32>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzApplicationGatewayAutoscaleConfiguration** membuat Konfigurasi Skala Otomatis untuk gateway aplikasi Azure.

## EXAMPLES

### Contoh 1
```powershell
$autoscaleConfig = New-AzApplicationGatewayAutoscaleConfiguration -MinCapacity 3
$gw = New-AzApplicationGateway -Name $appgwName -ResourceGroupName $rgname ..  -AutoscaleConfiguration $autoscaleConfig
```

Perintah pertama membuat konfigurasi skala otomatis dengan kapasitas minimum 3.
Perintah kedua membuat gateway aplikasi dengan konfigurasi skala otomatis.

### Contoh 2

```powershell
$gw = Get-AzApplicationGateway -Name <Name> -ResourceGroupName <ResourceGroupName>
$gw.Sku.Capacity = $null
$gw.AutoscaleConfiguration = New-AzApplicationGatewayAutoscaleConfiguration -MinCapacity 2 -MaxCapacity 4
$gw = Set-AzApplicationGateway -ApplicationGateway $gw
```

Perintah pertama mendapatkan konfigurasi Application Gateway ke dalam variabel.
Perintah kedua menghapus variabel Kapasitas SKU untuk memungkinkan Konfigurasi Skala Otomatis diatur.
Perintah ketiga menentukan Konfigurasi Skala Otomatis baru untuk Application Gateway.
Perintah keempat menerapkan konfigurasi baru ke Application Gateway.

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

### -MaxCapacity
Unit kapasitas maksimum yang akan selalu tersedia [dan dikenakan biaya] untuk gateway aplikasi.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinCapacity
Unit kapasitas minimum yang akan selalu tersedia [dan dikenakan biaya] untuk gateway aplikasi. 

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
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
Cmdlet tidak dijalankan.

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

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewayAutoscaleConfiguration

## NOTES

## RELATED LINKS

[Get-AzApplicationGatewayAutoscaleConfiguration](./Get-AzApplicationGatewayAutoscaleConfiguration.md)

[Remove-AzApplicationGatewayAutoscaleConfiguration](./Remove-AzApplicationGatewayAutoscaleConfiguration.md)

[Set-AzApplicationGatewayAutoscaleConfiguration](./Set-AzApplicationGatewayAutoscaleConfiguration.md)
