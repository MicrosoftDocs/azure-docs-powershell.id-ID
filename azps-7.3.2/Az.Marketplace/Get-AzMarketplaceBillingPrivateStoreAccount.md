---
external help file: ''
Module Name: Az.Marketplace
online version: https://docs.microsoft.com/powershell/module/az.marketplace/get-azmarketplacebillingprivatestoreaccount
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Marketplace/Marketplace/help/Get-AzMarketplaceBillingPrivateStoreAccount.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Marketplace/Marketplace/help/Get-AzMarketplaceBillingPrivateStoreAccount.md
ms.openlocfilehash: cc1b1733f3add2012538f443c09f8752f2dface1
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141892412"
---
# Get-AzMarketplaceBillingPrivateStoreAccount

## SYNOPSIS
Nama akun tagihan penyewa

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.marketplace/get-azmarketplacebillingprivatestoreaccount) untuk informasi terbaru.

## SYNTAX

### Tagihan (Default)
```
Get-AzMarketplaceBillingPrivateStoreAccount -PrivateStoreId <String> [-DefaultProfile <PSObject>] [-Confirm]
 [-WhatIf] [<CommonParameters>]
```

### BillingViaIdentity
```
Get-AzMarketplaceBillingPrivateStoreAccount -InputObject <IMarketplaceIdentity> [-DefaultProfile <PSObject>]
 [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Nama akun tagihan penyewa

## EXAMPLES

### Contoh 1: Mengembalikan akun tagihan dari bursa pribadi 
```powershell
PS C:\> Get-AzMarketplaceBillingPrivateStoreAccount -PrivateStoreId 3ac32d8c-e888-4dc6-b4ff-be4d755af13a


<billing account[string]>

```

Perintah ini mengembalikan akun tagihan bursa pribadi.

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
Parameter Sets: BillingViaIdentity
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
Parameter Sets: Billing
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

### Microsoft.Azure.PowerShell.Cmdlets.Marketplace.Models.IMarketplaceIdentity

## OUTPUTS

### System.String

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IMarketplaceIdentity>: Parameter Identitas
  - `[AdminRequestApprovalId <String>]`: ID persetujuan permintaan admin untuk membuat atau memperbarui
  - `[CollectionId <String>]`: ID koleksi
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[OfferId <String>]`: ID penawaran untuk memperbarui atau menghapus
  - `[PrivateStoreId <String>]`: ID bursa - harus menggunakan ID penyewa
  - `[RequestApprovalId <String>]`: ID persetujuan permintaan untuk membuat atau memperbarui

## RELATED LINKS

