---
external help file: ''
Module Name: Az.Marketplace
online version: https://docs.microsoft.com/powershell/module/az.marketplace/set-azmarketplaceprivatestorecollection
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Marketplace/Marketplace/help/Set-AzMarketplacePrivateStoreCollection.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Marketplace/Marketplace/help/Set-AzMarketplacePrivateStoreCollection.md
ms.openlocfilehash: 7c78ff179ce88a278a6e741644f0fed3c65779cc
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142177507"
---
# Set-AzMarketplacePrivateStoreCollection

## SYNOPSIS
Membuat atau memperbarui koleksi bursa pribadi

## SYNTAX

```
Set-AzMarketplacePrivateStoreCollection -CollectionId <String> -PrivateStoreId <String> [-AllSubscription]
 [-Claim <String>] [-CollectionName <String>] [-Enabled] [-SubscriptionsList <String[]>]
 [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Membuat atau memperbarui koleksi bursa pribadi

## EXAMPLES

### Contoh 1: Membuat atau memperbarui koleksi bursa pribadi
```powershell
Set-AzMarketplacePrivateStoreCollection -CollectionId 7f5402e4-e8f4-46bd-9bd1-8d27866a606b -PrivateStoreId 7f5402e4-e8f4-46bd-9bd1-8d27866a606b -AllSubscription
```

```output
Name                                 SystemDataCreatedAt SystemDataCreatedBy SystemDataCreatedByType SystemDataLastModifiedAt SystemDataLastModifiedBy SystemDataLastModifiedByType
----                                 ------------------- ------------------- ----------------------- ------------------------ ------------------------ ----------------------------
7f5402e4-e8f4-46bd-9bd1-8d27866a606b                                         User                    12/13/2021 1:21:57 PM                             User
```

Perintah ini membuat atau memperbarui koleksi bursa pribadi

## PARAMETERS

### -AllSubscription
Mengindikasikan apakah semua langganan dipilih (=true) atau tidak (=false).

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

### -Klaim
Mendapatkan atau mengatur asosiasi dengan Akun Tagihan Komersial.

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

### -CollectionName
Mendapatkan atau mengatur nama koleksi.

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

### -Difungsikan
Mengindikasikan apakah kumpulan diaktifkan atau dinonaktifkan.

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

### -SubscriptionsList
Mendapatkan atau mengatur daftar id langganan.
Daftar kosong menunjukkan semua langganan dipilih, null menunjukkan tidak ada pembaruan yang dilakukan, daftar eksplisit menunjukkan langganan yang dipilih secara eksplisit.
Saat disisipkan, null dianggap sebagai permintaan yang buruk

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

### Microsoft.Azure.PowerShell.Cmdlets.Marketplace.Models.Api20210601.ICollection

## CATATAN

ALIAS

## RELATED LINKS

