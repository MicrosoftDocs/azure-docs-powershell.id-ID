---
external help file: ''
Module Name: Az.EdgeOrder
online version: https://docs.microsoft.com/powershell/module/az.edgeorder/get-azedgeorderproductfamilymetadata
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EdgeOrder/help/Get-AzEdgeOrderProductFamilyMetadata.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EdgeOrder/help/Get-AzEdgeOrderProductFamilyMetadata.md
ms.openlocfilehash: 77a75c21f8f0bf1e4f1002378d97d7943e902b7f
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140237419"
---
# Get-AzEdgeOrderProductFamilyMetadata

## SYNOPSIS
Metode ini menyediakan daftar metadata keluarga produk untuk langganan tertentu.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.edgeorder/get-azedgeorderproductfamilymetadata) untuk informasi terkini.

## SYNTAX

```
Get-AzEdgeOrderProductFamilyMetadata [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [-Confirm]
 [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Metode ini menyediakan daftar metadata keluarga produk untuk langganan tertentu.

## EXAMPLES

### Contoh 1: Mendapatkan keluarga produk yang tersedia pada langganan yang di pengadaan
```powershell
PS C:\> $productFamilyMeta = Get-AzEdgeOrderProductFamilyMetadata -SubscriptionId SubscriptionId
PS C:\> $productFamilyMeta.HierarchyInformation

ConfigurationName ProductFamilyName ProductLineName ProductName
----------------- ----------------- --------------- -----------
                  azurestackedge
                  azurestackhub
```

Perintah ini menyediakan keluarga produk di langganan yang di pengadaan.

Pastikan registerProvider di Microsoft.EdgeOrder dilakukan sebelum menjalankan perintah ini.

Untuk mendapatkan detail tentang penggunaan perintah Get-AzEdgeOrderProductFamily keluarga

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases: AzureRMContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
ID langganan target.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.EdgeOrder.Models.Api20211201.IProductFamiliesMetadataDetails

## CATATAN

ALIAS

## RELATED LINKS

