---
external help file: ''
Module Name: Az.EdgeOrder
online version: https://docs.microsoft.com/powershell/module/az.edgeorder/get-azedgeorderproductfamily
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EdgeOrder/help/Get-AzEdgeOrderProductFamily.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EdgeOrder/help/Get-AzEdgeOrderProductFamily.md
ms.openlocfilehash: c36e28feb7d87670fb7e7990453044cb80990660
ms.sourcegitcommit: 5df8b100721844736630242c724da453a2168434
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/26/2022
ms.locfileid: "146615080"
---
# Get-AzEdgeOrderProductFamily

## SYNOPSIS
Metode ini menyediakan daftar keluarga produk untuk langganan yang diberikan.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.edgeorder/get-azedgeorderproductfamily) untuk informasi terbaru.

## SYNTAX

```
Get-AzEdgeOrderProductFamily -FilterableProperty <Hashtable> [-SubscriptionId <String[]>] [-Expand <String>]
 [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Metode ini menyediakan daftar keluarga produk untuk langganan yang diberikan.

## EXAMPLES

### Contoh 1: Mendapatkan detail productFamilies tertentu
```powershell
$familyDetails = Get-AzEdgeOrderProductFamily -SubscriptionId SubscriptionId -FilterableProperty  @{"azurestackedge"=@($filterableProperty)} -Expand "configurations"
$familyDetails.ProductLine.Product.Configuration.HierarchyInformation
```

```output
ConfigurationName ProductFamilyName ProductLineName ProductName
----------------- ----------------- --------------- -----------
edgep_high        azurestackedge    azurestackedge  azurestackedgegpu
edgepr_base       azurestackedge    azurestackedge  azurestackedgepror
edgemr_mini       azurestackedge    azurestackedge  azurestackedgeminir
```

Perintah ini mendapatkan wawasan tentang keluarga yang difilter.
Pastikan Anda menjalankan registerProvider di Microsoft.EdgeOrder sebelum menjalankan perintah ini.
Anda dapat menjalankan Get-AzEdgeOrderConfiguration untuk mendapatkan detail setiap konfigurasi

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

### -Perluas
$expand didukung pada parameter konfigurasi untuk produk, yang memberikan detail tentang konfigurasi untuk produk.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FilterableProperty
Kamus properti yang dapat difilter pada keluarga produk.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: True
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.EdgeOrder.Models.Api20211201.IProductFamily

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


CUSTOMERSUBSCRIPTIONDETAIL `<ICustomerSubscriptionDetails>`: Properti langganan pelanggan. Klien dapat menampilkan produk yang tersedia untuk pelanggan yang tidak terdaftar dengan secara eksplisit meneruskan detail langganan
  - `QuotaId <String>`: ID Kuota langganan
  - `[LocationPlacementId <String>]`: Id penempatan lokasi langganan
  - `[RegisteredFeature <ICustomerSubscriptionRegisteredFeatures[]>]`: Daftar bendera fitur terdaftar untuk langganan
    - `[Name <String>]`: Nama fitur terdaftar langganan
    - `[State <String>]`: Status fitur terdaftar langganan

## RELATED LINKS

