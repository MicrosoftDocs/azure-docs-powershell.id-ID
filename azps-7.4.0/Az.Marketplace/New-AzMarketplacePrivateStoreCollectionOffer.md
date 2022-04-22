---
external help file: ''
Module Name: Az.Marketplace
online version: https://docs.microsoft.com/powershell/module/az.marketplace/new-azmarketplaceprivatestorecollectionoffer
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Marketplace/Marketplace/help/New-AzMarketplacePrivateStoreCollectionOffer.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Marketplace/Marketplace/help/New-AzMarketplacePrivateStoreCollectionOffer.md
ms.openlocfilehash: ef657c0f45423cbc610cab1046b1365a8105e348
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142873234"
---
# New-AzMarketplacePrivateStoreCollectionOffer

## SYNOPSIS
Perbarui atau tambahkan penawaran ke koleksi toko pribadi tertentu.

## SYNTAX

```
New-AzMarketplacePrivateStoreCollectionOffer -CollectionId <String> -OfferId <String> -PrivateStoreId <String>
 [-ETag <String>] [-IconFileUri <Hashtable>] [-Plan <IPlan[]>] [-SpecificPlanIdLimitation <String[]>]
 [-UpdateSuppressedDueIdempotence] [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Perbarui atau tambahkan penawaran ke koleksi toko pribadi tertentu.

## EXAMPLES

### Contoh 1: Membuat atau memperbarui penawaran untuk koleksi bursa pribadi 
```powershell
$acc = @{Accessibility = "azure_managedservices_professional"}
New-AzMarketplacePrivateStoreCollectionOffer -CollectionId fdb889a1-cf3e-49f0-95b8-2bb012fa01f1 -PrivateStoreId 7f5402e4-e8f4-46bd-9bd1-8d27866a606b  -OfferId aumatics.azure_managedservices -Plan $acc
```

```output
Name                           SystemDataCreatedAt SystemDataCreatedBy SystemDataCreatedByType SystemDataLastModifiedAt SystemDataLastModifiedBy SystemDataLastModifiedByType
----                           ------------------- ------------------- ----------------------- ------------------------ ------------------------ ----------------------------
aumatics.azure_managedservices
```

Perintah ini membuat atau memperbarui penawaran untuk koleksi bursa pribadi.

## PARAMETERS

### -CollectionId
ID koleksi

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
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases: AzureRMContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ETag
Pengidentifikasi untuk tujuan kondisi balapan

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

### -IconFileUri
Uris File Ikon

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OfferId
ID penawaran untuk memperbarui atau menghapus

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

### -Rencana
Menawarkan rencana Untuk membangun, lihat bagian CATATAN untuk properti PLAN dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Marketplace.Models.Api20210601.IPlan[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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

### -SpecificPlanIdLimitation
Batasan id paket untuk penawaran ini

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UpdateSuppressedDueIdempotence
Menunjukkan apakah penawaran tidak diperbarui ke db (true = tidak diperbarui).
Jika daftar yang diperbolehkan identik dengan daftar yang sudah ada dalam db, penawaran tidak akan diperbarui.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
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

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Marketplace.Models.Api20210601.IOffer

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


RENCANA <IPlan[]>: Paket penawaran
  - `[Accessibility <Accessibility?>]`: Merencanakan aksesibilitas

## RELATED LINKS

