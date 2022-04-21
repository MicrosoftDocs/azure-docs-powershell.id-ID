---
external help file: ''
Module Name: Az.Marketplace
online version: https://docs.microsoft.com/powershell/module/az.marketplace/set-azmarketplacebulkprivatestorecollectionaction
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Marketplace/Marketplace/help/Set-AzMarketplaceBulkPrivateStoreCollectionAction.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Marketplace/Marketplace/help/Set-AzMarketplaceBulkPrivateStoreCollectionAction.md
ms.openlocfilehash: 638dc55dee85090e3a0bee730f8cae777aa218a5
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142764856"
---
# Set-AzMarketplaceBulkPrivateStoreCollectionAction

## SYNOPSIS
Melakukan tindakan pada koleksi massal

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.marketplace/set-azmarketplacebulkprivatestorecollectionaction) untuk informasi terbaru.

## SYNTAX

### MassalExpanded (Default)
```
Set-AzMarketplaceBulkPrivateStoreCollectionAction -PrivateStoreId <String> [-Action <String>]
 [-CollectionId <String[]>] [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### Massal
```
Set-AzMarketplaceBulkPrivateStoreCollectionAction -PrivateStoreId <String> -Payload <IBulkCollectionsPayload>
 [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Melakukan tindakan pada koleksi massal

## EXAMPLES

### Contoh 1: Tindakan massal praformat pada koleksi 
```powershell
PS C:\> Set-AzMarketplaceBulkPrivateStoreCollectionAction -PrivateStoreId 3ac32d8c-e888-4dc6-b4ff-be4d755af13a -Payload @{Action = "EnableCollections"; CollectionId = "3ac32d8c-e888-4dc6-b4ff-be4d755af13a", "fdb889a1-cf3e-49f0-95b8-2bb012fa01f1" }

Failed Succeeded
------ ---------
{}     {DefaultCollection, test}
```

Perintah ini Melakukan preformasi tindakan massal pada koleksi

## PARAMETERS

### -Tindakan
Tindakan untuk dijalankan (Misalnya: EnableCollections, DisableCollections)

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
daftar id koleksi tempat tindakan dijalankan pada

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
Properti tindakan kumpulan massal Untuk membangun, lihat bagian CATATAN untuk properti PAYLOAD dan membuat tabel hash.

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
ID bursa - harus menggunakan ID penyewa

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

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Marketplace.Models.Api20210601.IBulkCollectionsPayload

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Marketplace.Models.Api20210601.IBulkCollectionsResponse

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


PAYLOAD <IBulkCollectionsPayload>: Properti tindakan pengumpulan massal
  - `[Action <String>]`: Tindakan untuk dijalankan (Misalnya: EnableCollections, DisableCollections)
  - `[CollectionId <String[]>]`: pengumpulan id daftar bahwa tindakan dilakukan pada

## RELATED LINKS

