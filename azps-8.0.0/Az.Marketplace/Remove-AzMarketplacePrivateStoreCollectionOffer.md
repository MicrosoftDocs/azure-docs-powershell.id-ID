---
external help file: ''
Module Name: Az.Marketplace
online version: https://docs.microsoft.com/powershell/module/az.marketplace/remove-azmarketplaceprivatestorecollectionoffer
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Marketplace/Marketplace/help/Remove-AzMarketplacePrivateStoreCollectionOffer.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Marketplace/Marketplace/help/Remove-AzMarketplacePrivateStoreCollectionOffer.md
ms.openlocfilehash: b42bc2154ae8e85587ef93a0cd8ff95343bbc132
ms.sourcegitcommit: 5df8b100721844736630242c724da453a2168434
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/26/2022
ms.locfileid: "146605596"
---
# Remove-AzMarketplacePrivateStoreCollectionOffer

## SYNOPSIS
Menghapus penawaran dari koleksi penyimpanan privat yang diberikan.

## SYNTAX

### Hapus (Default)
```
Remove-AzMarketplacePrivateStoreCollectionOffer -CollectionId <String> -OfferId <String>
 -PrivateStoreId <String> [-DefaultProfile <PSObject>] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### DeleteViaIdentity
```
Remove-AzMarketplacePrivateStoreCollectionOffer -InputObject <IMarketplaceIdentity>
 [-DefaultProfile <PSObject>] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Menghapus penawaran dari koleksi penyimpanan privat yang diberikan.

## EXAMPLES

### Contoh 1: Menghapus penawaran dari koleksi penyimpanan privat
```powershell
Remove-AzMarketplacePrivateStoreCollectionOffer -PrivateStoreId 3ac32d8c-e888-4dc6-b4ff-be4d755af13a -CollectionId fdb889a1-cf3e-49f0-95b8-2bb012fa01f1 -OfferId aumatics.azure_managedservices
```

Perintah ini menghapus penawaran dari koleksi penyimpanan privat

## PARAMETERS

### -CollectionId
ID koleksi

```yaml
Type: System.String
Parameter Sets: Delete
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

### -InputObject
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Marketplace.Models.IMarketplaceIdentity
Parameter Sets: DeleteViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -OfferId
ID penawaran untuk diperbarui atau dihapus

```yaml
Type: System.String
Parameter Sets: Delete
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Mengembalikan true saat perintah berhasil

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

### -PrivateStoreId
ID penyimpanan - harus menggunakan ID penyewa

```yaml
Type: System.String
Parameter Sets: Delete
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

### Microsoft.Azure.PowerShell.Cmdlets.Marketplace.Models.IMarketplaceIdentity

## OUTPUTS

### System.Boolean

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT `<IMarketplaceIdentity>`: Parameter Identitas
  - `[AdminRequestApprovalId <String>]`: ID persetujuan permintaan admin untuk membuat atau memperbarui
  - `[CollectionId <String>]`: ID koleksi
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[OfferId <String>]`: ID penawaran untuk memperbarui atau menghapus
  - `[PrivateStoreId <String>]`: ID penyimpanan - harus menggunakan ID penyewa
  - `[RequestApprovalId <String>]`: ID persetujuan permintaan untuk membuat atau memperbarui

## RELATED LINKS

