---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
online version: https://docs.microsoft.com/powershell/module/az.compute/new-azdiskpurchaseplanconfig.md
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/New-AzDiskPurchasePlanConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/New-AzDiskPurchasePlanConfig.md
ms.openlocfilehash: 70b4b79422ea6dc7aa322d59685a3ac48f1e38db
ms.sourcegitcommit: e109cc5320478db6aa8a52d49996b133007a65b9
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 01/12/2022
ms.locfileid: "136735215"
---
# New-AzDiskPurchasePlanConfig

## SYNOPSIS
Membuat Objek PurchasePlan

## SYNTAX

```
New-AzDiskPurchasePlanConfig [-Publisher <String>] [-Name <String>] [-Product <String>]
 [-PromotionCode <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Membuat Objek PurchasePlan

## EXAMPLES

### Contoh 1
```powershell
$diskPurchasePlan = New-AzDiskPurchasePlanConfig -Name �planName� -Publisher �planPublisher� -Product �planPorduct� -PromotionCode �planPromotionCode�
$diskConfig = New-AzDiskConfig -Location 'eastus2euap' -AccountType 'Premium_LRS' -CreateOption 'Empty' -DiskSizeGB 32 -PurchasePlan $diskPurchasePlan
New-AzDisk -ResourceGroupName 'ResourceGroup02' -DiskName 'Disk02' -Disk $diskConfig
$disk = Get-AzDisk -ResourceGroupName 'ResourceGroup02' -DiskName 'Disk02'
```

Pelanggan dapat mengatur PurchasePlan di Disk Terkelola.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama Konfigurasi

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Product
Nama Produk

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Kode Promosi
Kode Promosi untuk Paket Pembelian

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Publisher
Nama Publisher

```yaml
Type: String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Automation.Models.PSPurchasePlan

### Microsoft.Azure.Commands.Compute.Automation.Models.PSPurchasePlan

## CATATAN

## RELATED LINKS
