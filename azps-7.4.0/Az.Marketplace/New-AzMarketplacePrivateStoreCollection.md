---
external help file: ''
Module Name: Az.Marketplace
online version: https://docs.microsoft.com/powershell/module/az.marketplace/new-azmarketplaceprivatestorecollection
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Marketplace/Marketplace/help/New-AzMarketplacePrivateStoreCollection.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Marketplace/Marketplace/help/New-AzMarketplacePrivateStoreCollection.md
ms.openlocfilehash: 108670c31872ee96d80f44e77a3da9dd0eccbb2f
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144569378"
---
# New-AzMarketplacePrivateStoreCollection

## SYNOPSIS
Membuat atau memperbarui koleksi penyimpanan privat

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.marketplace/new-azmarketplaceprivatestorecollection) untuk informasi terbaru.

## SYNTAX

```
New-AzMarketplacePrivateStoreCollection -CollectionId <String> -PrivateStoreId <String> [-AllSubscription]
 [-Claim <String>] [-CollectionName <String>] [-Enabled] [-SubscriptionsList <String[]>]
 [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Membuat atau memperbarui koleksi penyimpanan privat

## EXAMPLES

### Contoh 1: Membuat atau memperbarui koleksi penyimpanan privat
```powershell
New-AzMarketplacePrivateStoreCollection -CollectionName test -CollectionId fdb889a1-cf3e-49f0-95b8-2bb012fa01f1 -PrivateStoreId 3ac32d8c-e888-4dc6-b4ff-be4d755af13a -SubscriptionsList 7f5402e4-e8f4-46bd-9bd1-8d27866a606b
```

```output
Name                                 SystemDataCreatedAt    SystemDataCreatedBy SystemDataCreatedByType SystemDataLastModifiedAt SystemDataLastModifiedBy SystemDataLastModifiedByType
----                                 -------------------    ------------------- ----------------------- ------------------------ ------------------------ ----------------------------
fdb889a1-cf3e-49f0-95b8-2bb012fa01f1 12/13/2021 11:12:27 AM                     User                    12/13/2021 11:12:27 AM                            User
```

Perintah ini membuat atau memperbarui koleksi penyimpanan privat

## PARAMETERS

### -AllSubscription
Menunjukkan apakah semua langganan dipilih (=true) atau tidak (=false).

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
Mendapatkan atau menetapkan asosiasi dengan Akun Penagihan Komersial.

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

### -Diaktifkan
Menunjukkan apakah koleksi diaktifkan atau dinonaktifkan.

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

### Microsoft.Azure.PowerShell.Cmdlets.Marketplace.Models.Api20210601.ICollection

## NOTES

ALIAS

## RELATED LINKS

