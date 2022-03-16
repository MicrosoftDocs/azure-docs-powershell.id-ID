---
external help file: ''
Module Name: Az.Marketplace
online version: https://docs.microsoft.com/powershell/module/az.marketplace/get-azmarketplaceprivatestorecollection
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Marketplace/Marketplace/help/Get-AzMarketplacePrivateStoreCollection.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Marketplace/Marketplace/help/Get-AzMarketplacePrivateStoreCollection.md
ms.openlocfilehash: 6ae17f27f5a4473d629b22fb5fd4dd9b2e53113b
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140234059"
---
# Get-AzMarketplacePrivateStoreCollection

## SYNOPSIS
Dapatkan koleksi bursa pribadi

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.marketplace/get-azmarketplaceprivatestorecollection) untuk informasi terkini.

## SYNTAX

### Daftar (Default)
```
Get-AzMarketplacePrivateStoreCollection -PrivateStoreId <String> [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### Dapatkan
```
Get-AzMarketplacePrivateStoreCollection -CollectionId <String> -PrivateStoreId <String>
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzMarketplacePrivateStoreCollection -InputObject <IMarketplaceIdentity> [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Dapatkan koleksi bursa pribadi

## EXAMPLES

### Contoh 1: Dapatkan daftar koleksi bursa pribadi
```powershell
PS C:\> Get-AzMarketplacePrivateStoreCollection -PrivateStoreId 53425a7b-4ac1-4729-8340-e1da5046212c

Name                                 SystemDataCreatedAt  SystemDataCreatedBy SystemDataCreatedByType SystemDataLastModifiedAt SystemDataLastModifiedBy SystemDataLastModifiedByType
----                                 -------------------  ------------------- ----------------------- ------------------------ ------------------------ ----------------------------
53425a7b-4ac1-4729-8340-e1da5046212c                                          User                    8/23/2021 6:06:52 AM                              User
23455a7b-4ac1-4729-8340-e1da5046212c 12/1/2021 9:01:33 PM                     User                    12/1/2021 9:01:33 PM                              User

```

Perintah ini berisi daftar koleksi bursa pribadi

## PARAMETERS

### -CollectionId
ID koleksi

```yaml
Type: System.String
Parameter Sets: Get
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
Parameter Sets: GetViaIdentity
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
Parameter Sets: Get, List
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Marketplace.Models.IMarketplaceIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Marketplace.Models.Api20210601.ICollection

### Microsoft.Azure.PowerShell.Cmdlets.Marketplace.Models.Api20210601.ICollectionsList

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

## RELATED LINKS

