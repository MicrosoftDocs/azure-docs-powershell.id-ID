---
external help file: ''
Module Name: Az.Marketplace
online version: https://docs.microsoft.com/powershell/module/az.marketplace/set-azmarketplacebulkprivatestorecollectionaction
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Marketplace/Marketplace/help/Set-AzMarketplaceBulkPrivateStoreCollectionAction.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Marketplace/Marketplace/help/Set-AzMarketplaceBulkPrivateStoreCollectionAction.md
ms.openlocfilehash: e135ea1046da86022d8f1cc8de7b7df328a864ec
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145513474"
---
# Set-AzMarketplaceBulkPrivateStoreCollectionAction

## SYNOPSIS
Melakukan tindakan pada koleksi massal

## SYNTAX

### BulkExpanded (Default)
```
Set-AzMarketplaceBulkPrivateStoreCollectionAction -PrivateStoreId <String> [-Action <String>]
 [-CollectionId <String[]>] [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### /Bulk
```
Set-AzMarketplaceBulkPrivateStoreCollectionAction -PrivateStoreId <String> -Payload <IBulkCollectionsPayload>
 [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Melakukan tindakan pada koleksi massal

## EXAMPLES

### Contoh 1: Tindakan massal praformat pada koleksi 
```powershell
Set-AzMarketplaceBulkPrivateStoreCollectionAction -PrivateStoreId 3ac32d8c-e888-4dc6-b4ff-be4d755af13a -Payload @{Action = "EnableCollections"; CollectionId = "3ac32d8c-e888-4dc6-b4ff-be4d755af13a", "fdb889a1-cf3e-49f0-95b8-2bb012fa01f1" }
```

```output
Failed Succeeded
------ ---------
{}     {DefaultCollection, test}
```

Perintah ini Melakukan preformasi tindakan massal pada koleksi

## PARAMETERS

### -Tindakan
Tindakan yang harus dilakukan (Misalnya: EnableCollections, DisableCollections)

```yaml
Type: System.String
Parameter Sets: BulkExpanded
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CollectionId
id koleksi mencantumkan tindakan yang dilakukan

```yaml
Type: System.String[]
Parameter Sets: BulkExpanded
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -Payload
Properti tindakan koleksi massal Untuk membangun, lihat bagian CATATAN untuk properti PAYLOAD dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Marketplace.Models.Api20210601.IBulkCollectionsPayload
Parameter Sets: Bulk
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Marketplace.Models.Api20210601.IBulkCollectionsPayload

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Marketplace.Models.Api20210601.IBulkCollectionsResponse

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


PAYLOAD <IBulkCollectionsPayload>: Properti tindakan pengumpulan massal
  - `[Action <String>]`: Tindakan yang harus dilakukan (Misalnya: EnableCollections, DisableCollections)
  - `[CollectionId <String[]>]`: id koleksi mencantumkan bahwa tindakan dilakukan pada

## RELATED LINKS

