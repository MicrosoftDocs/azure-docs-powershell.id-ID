---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/new-azvirtualapplianceskuproperty
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzVirtualApplianceSkuProperty.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzVirtualApplianceSkuProperty.md
ms.openlocfilehash: 03824b1df3bf179dd23791daf8c04106c5f57075
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142080283"
---
# New-AzVirtualApplianceSkuProperty

## SYNOPSIS
Tentukan sku Network Virtual Appliance untuk sumber daya.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.network/new-azvirtualapplianceskuproperty) untuk informasi terbaru.

## SYNTAX

```
New-AzVirtualApplianceSkuProperty -VendorName <String> -BundledScaleUnit <String> -MarketPlaceVersion <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Perintah New-AzVirtualApplianceSkuProperties menentukan sumber daya Sku untuk Peralatan Virtual Jaringan.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> $var=New-AzVirtualApplianceSkuProperty -VendorName "barracudasdwanrelease" -BundledScaleUnit 1 -MarketPlaceVersion 'latest'
```

Buat objek Properti Sku Alat Virtual untuk digunakan dengan perintah New-AzNetworkVirtualAppliance. 

## PARAMETERS

### -BundledScaleUnit
Unit skala yang dibundel.

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

### -MarketPlaceVersion
Versi market place.

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

### -VendorName
Nama vendor.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Name

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSVirtualApplianceSkuProperties

## CATATAN

## RELATED LINKS
