---
external help file: ''
Module Name: Az.Marketplace
online version: https://docs.microsoft.com/powershell/module/az.marketplace/copy-azmarketplaceprivatestorecollectionoffer
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Marketplace/Marketplace/help/Copy-AzMarketplacePrivateStoreCollectionOffer.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Marketplace/Marketplace/help/Copy-AzMarketplacePrivateStoreCollectionOffer.md
ms.openlocfilehash: 3c20ca47c9fe14137906aaf4de6d0bbf8c363f95
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138164638"
---
# Copy-AzMarketplacePrivateStoreCollectionOffer

## SYNOPSIS
mentransfer penawaran (menyalin atau memindahkan) dari kumpulan sumber ke kumpulan target

## SYNTAX

### TransferExpanded (Default)
```
Copy-AzMarketplacePrivateStoreCollectionOffer -CollectionId <String> -PrivateStoreId <String>
 [-OfferIdList <String[]>] [-Operation <String>] [-TargetCollection <String[]>] [-DefaultProfile <PSObject>]
 [-Confirm] [-WhatIf] [<CommonParameters>]
```

### Transfer
```
Copy-AzMarketplacePrivateStoreCollectionOffer -CollectionId <String> -PrivateStoreId <String>
 -Payload <ITransferOffersProperties> [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### TransferViaIdentity
```
Copy-AzMarketplacePrivateStoreCollectionOffer -InputObject <IMarketplaceIdentity>
 -Payload <ITransferOffersProperties> [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### TransferViaIdentityExpanded
```
Copy-AzMarketplacePrivateStoreCollectionOffer -InputObject <IMarketplaceIdentity> [-OfferIdList <String[]>]
 [-Operation <String>] [-TargetCollection <String[]>] [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
mentransfer penawaran (menyalin atau memindahkan) dari kumpulan sumber ke kumpulan target

## EXAMPLES

### Contoh 1: Salin penawaran dari kumpulan sumber ke kumpulan target.
```powershell
PS C:\> $payload = @{OfferIdsList = "aumatics.azure_managedservices"; Operation = "Copy"; TargetCollection = "3ac32d8c-e888-4dc6-b4ff-be4d755af13a"}
PS C:\>  Copy-AzMarketplacePrivateStoreCollectionOffer -PrivateStoreId 3ac32d8c-e888-4dc6-b4ff-be4d755af13a -CollectionId fdb889a1-cf3e-49f0-95b8-2bb012fa01f1 -Payload $payload

Failed Succeeded
------ ---------
{}     {DefaultCollection}
```

Salinan perintah ini menawarkan dari kumpulan sumber ke kumpulan target.

## PARAMETERS

### -CollectionId
ID koleksi

```yaml
Type: System.String
Parameter Sets: Transfer, TransferExpanded
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
Parameter Identitas Untuk membuat, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Marketplace.Models.IMarketplaceIdentity
Parameter Sets: TransferViaIdentity, TransferViaIdentityExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -OfferIdList
Menawarkan daftar id untuk ditransfer dari kumpulan sumber ke kumpulan target

```yaml
Type: System.String[]
Parameter Sets: TransferExpanded, TransferViaIdentityExpanded
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Operasi
Operasi untuk dilakukan (Misalnya: Menyalin atau Memindahkan)

```yaml
Type: System.String
Parameter Sets: TransferExpanded, TransferViaIdentityExpanded
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Payload
Transfer menawarkan properti Untuk membangun, lihat bagian CATATAN untuk properti PAYLOAD dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Marketplace.Models.Api20210601.ITransferOffersProperties
Parameter Sets: Transfer, TransferViaIdentity
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
Parameter Sets: Transfer, TransferExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetCollection
Id kumpulan target

```yaml
Type: System.String[]
Parameter Sets: TransferExpanded, TransferViaIdentityExpanded
Aliases:

Required: False
Position: Named
Default value: None
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

### Microsoft.Azure.PowerShell.Cmdlets.Marketplace.Models.Api20210601.ITransferOffersProperties

### Microsoft.Azure.PowerShell.Cmdlets.Marketplace.Models.IMarketplaceIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Marketplace.Models.Api20210601.ITransferOffersResponse

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IMarketplaceIdentity>: Parameter Identitas
  - `[AdminRequestApprovalId <String>]`: ID persetujuan permintaan admin untuk mendapatkan buat atau perbarui
  - `[CollectionId <String>]`: ID koleksi
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[OfferId <String>]`: ID penawaran untuk memperbarui atau menghapus
  - `[PrivateStoreId <String>]`: ID bursa - harus menggunakan ID penyewa
  - `[RequestApprovalId <String>]`: ID persetujuan permintaan untuk mendapatkan buat atau perbarui

PAYLOAD <ITransferOffersProperties>: Transfer menawarkan properti
  - `[OfferIdsList <String[]>]`: Menawarkan daftar id untuk ditransfer dari kumpulan sumber ke kumpulan target
  - `[Operation <String>]`: Operasi untuk dilakukan (Misalnya: Menyalin atau Memindahkan)
  - `[TargetCollection <String[]>]`: Id kumpulan target

## RELATED LINKS

