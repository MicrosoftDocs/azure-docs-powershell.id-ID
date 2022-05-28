---
external help file: ''
Module Name: Az.Marketplace
online version: https://docs.microsoft.com/powershell/module/az.marketplace/get-azmarketplacecollectiontosubscriptionmapping
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Marketplace/Marketplace/help/Get-AzMarketplaceCollectionToSubscriptionMapping.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Marketplace/Marketplace/help/Get-AzMarketplaceCollectionToSubscriptionMapping.md
ms.openlocfilehash: 2f16c475faefc69249d518e9732684de2ffa416b
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145555812"
---
# Get-AzMarketplaceCollectionToSubscriptionMapping

## SYNOPSIS
Untuk daftar langganan tertentu, API akan mengembalikan peta koleksi dan langganan terkait dari daftar yang disediakan.

## SYNTAX

### CollectionsExpanded (Default)
```
Get-AzMarketplaceCollectionToSubscriptionMapping -PrivateStoreId <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### Koleksi
```
Get-AzMarketplaceCollectionToSubscriptionMapping -PrivateStoreId <String>
 -Payload <ICollectionsToSubscriptionsMappingPayload> [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf]
 [<CommonParameters>]
```

### CollectionsViaIdentity
```
Get-AzMarketplaceCollectionToSubscriptionMapping -InputObject <IMarketplaceIdentity>
 -Payload <ICollectionsToSubscriptionsMappingPayload> [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf]
 [<CommonParameters>]
```

### CollectionsViaIdentityExpanded
```
Get-AzMarketplaceCollectionToSubscriptionMapping -InputObject <IMarketplaceIdentity>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Untuk daftar langganan tertentu, API akan mengembalikan peta koleksi dan langganan terkait dari daftar yang disediakan.

## EXAMPLES

### Contoh 1: Untuk daftar langganan tertentu, Cmdlet akan mengembalikan peta koleksi dan langganan terkait dari daftar yang disediakan.
```powershell
$res = Get-AzMarketplaceCollectionToSubscriptionMapping -PrivateStoreId a260d38c-96cf-492d-a340-404d0c4b3ad6 -Payload @{SubscriptionId = "53425a7b-4ac1-4729-8340-e1da5046212c"}
$res.keys
```

```output
e58535dc-1be3-4d2c-904c-1f97984ebe5d
fdb889a1-cf3e-49f0-95b8-2bb012fa01f1
```

Perintah Ini Untuk daftar langganan tertentu, akan mengembalikan peta koleksi dan langganan terkait dari daftar yang disediakan.

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

### -InputObject
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Marketplace.Models.IMarketplaceIdentity
Parameter Sets: CollectionsViaIdentity, CollectionsViaIdentityExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Payload
Daftar langganan untuk mendapatkan koleksi terkait Untuk membangun, lihat bagian CATATAN untuk properti PAYLOAD dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Marketplace.Models.Api20210601.ICollectionsToSubscriptionsMappingPayload
Parameter Sets: Collections, CollectionsViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PrivateStoreId
ID penyimpanan - harus menggunakan ID penyewa

```yaml
Type: System.String
Parameter Sets: Collections, CollectionsExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
Daftar id langganan

```yaml
Type: System.String[]
Parameter Sets: CollectionsExpanded, CollectionsViaIdentityExpanded
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

### Microsoft.Azure.PowerShell.Cmdlets.Marketplace.Models.Api20210601.ICollectionsToSubscriptionsMappingPayload

### Microsoft.Azure.PowerShell.Cmdlets.Marketplace.Models.IMarketplaceIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Marketplace.Models.Api20210601.ICollectionsToSubscriptionsMappingResponseProperties

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IMarketplaceIdentity>: Parameter Identitas
  - `[AdminRequestApprovalId <String>]`: ID persetujuan permintaan admin untuk membuat atau memperbarui
  - `[CollectionId <String>]`: ID koleksi
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[OfferId <String>]`: ID penawaran yang akan diperbarui atau dihapus
  - `[PrivateStoreId <String>]`: ID penyimpanan - harus menggunakan ID penyewa
  - `[RequestApprovalId <String>]`: ID persetujuan permintaan untuk membuat atau memperbarui

PAYLOAD <ICollectionsToSubscriptionsMappingPayload>: Daftar langganan untuk mendapatkan koleksi terkait
  - `[SubscriptionId <String[]>]`: Daftar id langganan

## RELATED LINKS

