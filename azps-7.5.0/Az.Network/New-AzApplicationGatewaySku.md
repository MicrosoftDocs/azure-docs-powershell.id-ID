---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
ms.assetid: 48C33FAF-83C1-4725-AD2A-CF48D0718182
online version: https://docs.microsoft.com/powershell/module/az.network/new-azapplicationgatewaysku
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzApplicationGatewaySku.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzApplicationGatewaySku.md
ms.openlocfilehash: 2d6baa7095f887f8a8cd3966dffcd00deb82e21c
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144223331"
---
# New-AzApplicationGatewaySku

## SYNOPSIS
Membuat SKU untuk gateway aplikasi.

## SYNTAX

```
New-AzApplicationGatewaySku -Name <String> -Tier <String> [-Capacity <Int32>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzApplicationGatewaySku** membuat unit penyimpanan stok (SKU) untuk gateway aplikasi Azure.

## EXAMPLES

### Contoh 1: Membuat SKU untuk gateway aplikasi Azure
```powershell
$SKU = New-AzApplicationGatewaySku -Name "Standard_Small" -Tier "Standard" -Capacity 2
```

Perintah ini membuat SKU bernama Standard_Small untuk gateway aplikasi Azure dan menyimpan hasilnya dalam variabel bernama $SKU.

## PARAMETERS

### -Kapasitas
Menentukan jumlah instans gateway aplikasi.

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
Menentukan nama SKU.
Nilai yang dapat diterima untuk parameter ini adalah:
- Standard_Small
- Standard_Medium
- Standard_Large
- WAF_Medium
- WAF_Large
- Standard_v2
- WAF_v2

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Standard_Small, Standard_Medium, Standard_Large, WAF_Medium, WAF_Large, Standard_v2, WAF_v2

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tingkat
Menentukan tingkat SKU.
Nilai yang dapat diterima untuk parameter ini adalah:
- Standar
- WAF
- Standard_v2
- WAF_v2

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Standard, WAF, Standard_v2, WAF_v2

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

### Microsoft.Azure.Commands.Network.Models.PSApplicationGatewaySku

## NOTES

## RELATED LINKS

[Get-AzApplicationGatewaySku](./Get-AzApplicationGatewaySku.md)

[Set-AzApplicationGatewaySku](./Set-AzApplicationGatewaySku.md)


