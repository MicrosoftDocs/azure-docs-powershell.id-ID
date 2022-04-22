---
external help file: ''
Module Name: Az.Marketplace
online version: https://docs.microsoft.com/powershell/module/az.marketplace/get-azmarketplacequeryprivatestoreoffer
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Marketplace/Marketplace/help/Get-AzMarketplaceQueryPrivateStoreOffer.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Marketplace/Marketplace/help/Get-AzMarketplaceQueryPrivateStoreOffer.md
ms.openlocfilehash: 323426c4e4c41388f313af22f92ea93bb553e0e5
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142951697"
---
# Get-AzMarketplaceQueryPrivateStoreOffer

## SYNOPSIS
Daftar penawaran, terlepas dari koleksinya

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.marketplace/get-azmarketplacequeryprivatestoreoffer) untuk informasi terbaru.

## SYNTAX

### Kueri (Default)
```
Get-AzMarketplaceQueryPrivateStoreOffer -PrivateStoreId <String> [-DefaultProfile <PSObject>] [-Confirm]
 [-WhatIf] [<CommonParameters>]
```

### KueriIdentitas
```
Get-AzMarketplaceQueryPrivateStoreOffer -InputObject <IMarketplaceIdentity> [-DefaultProfile <PSObject>]
 [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Daftar penawaran, terlepas dari koleksinya

## EXAMPLES

### Contoh 1: Mengembalikan penawaran bursa pribadi terlepas dari koleksi
```powershell
PS C:\> Get-AzMarketplaceQueryPrivateStoreOffer -PrivateStoreId 3ac32d8c-e888-4dc6-b4ff-be4d755af13a

CreatedAt ETag                                   ModifiedAt OfferDisplayName PrivateStoreId                       PublisherDisplayName SpecificPlanIdLimitation                                                     UniqueOfferId
--------- ----                                   ---------- ---------------- --------------                       -------------------- -------------------------                                                     -------------
          "ed0093ae-0000-0100-0000-61a4dab30000"                             3ac32d8c-e888-4dc6-b4ff-be4d755af13a                      {d3-azure-health-check, data3-azure-optimiser-plan, data3-managed-azure-plan} data3-limite…
          "750547d8-0000-0100-0000-61b752010000"                             3ac32d8c-e888-4dc6-b4ff-be4d755af13a                      {mgmt-limited-free, mgmt-assessment}                                          viacode_cons…
          "ef00ab05-0000-0100-0000-61a5f12f0000"                             3ac32d8c-e888-4dc6-b4ff-be4d755af13a                      {RedHatEnterpriseLinux72-ARM}                                                 RedHat.RHEL_7
          "f300276b-0000-0100-0000-61a7e1af0000"                             3ac32d8c-e888-4dc6-b4ff-be4d755af13a                      {128technology_conductor_hourly_427, 128technology_conductor_hourly_452}      128technolog…
          "f300296b-0000-0100-0000-61a7e1af0000"                             3ac32d8c-e888-4dc6-b4ff-be4d755af13a                      {128technology_router_100_hourly_427, 128technology_router_100_hourly_452}    128technolog…

```

Perintah ini mengembalikan penawaran bursa pribadi terlepas dari koleksinya

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
Parameter Sets: QueryViaIdentity
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
Parameter Sets: Query
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

### Microsoft.Azure.PowerShell.Cmdlets.Marketplace.Models.Api20210601.IQueryOffers

## NOTES

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

