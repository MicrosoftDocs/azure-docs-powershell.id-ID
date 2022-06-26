---
external help file: ''
Module Name: Az.Marketplace
online version: https://docs.microsoft.com/powershell/module/az.marketplace/get-azmarketplaceprivatestorev1
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Marketplace/Marketplace/help/Get-AzMarketplacePrivateStoreV1.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Marketplace/Marketplace/help/Get-AzMarketplacePrivateStoreV1.md
ms.openlocfilehash: fe3092bff472935731a1e13b63de8c8eafc23e08
ms.sourcegitcommit: 5df8b100721844736630242c724da453a2168434
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/26/2022
ms.locfileid: "146619724"
---
# Get-AzMarketplacePrivateStoreV1

## SYNOPSIS
Mendapatkan informasi tentang penyimpanan privat

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.marketplace/get-azmarketplaceprivatestorev1) untuk informasi terbaru.

## SYNTAX

### Daftar (Default)
```
Get-AzMarketplacePrivateStoreV1 [-UseCache <String>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Dapatkan
```
Get-AzMarketplacePrivateStoreV1 -Id <String> [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzMarketplacePrivateStoreV1 -InputObject <IMarketplaceIdentity> [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan informasi tentang penyimpanan privat

## EXAMPLES

### Contoh 1: Mendapatkan detail Penyimpanan Privat
```powershell
Get-AzMarketplacePrivateStoreV1
```

```output
Name                                 SystemDataCreatedAt SystemDataCreatedBy SystemDataCreatedByType SystemDataLastModifiedAt SystemDataLastModifiedBy SystemDataLastModifiedByType
----                                 ------------------- ------------------- ----------------------- ------------------------ ------------------------ ----------------------------
a260d38c-96cf-492d-a340-404d0c4b3ad6                                         User                    12/1/2021 9:01:33 PM                              User
```

Perintah ini Mendapatkan detail penyimpanan privat


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

### -Id
ID penyimpanan - harus menggunakan ID penyewa

```yaml
Type: System.String
Parameter Sets: Get
Aliases: PrivateStoreId

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

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

### -UseCache
Menentukan apakah akan menggunakan cache atau DB untuk melayani permintaan ini

```yaml
Type: System.String
Parameter Sets: List
Aliases:

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

### Microsoft.Azure.PowerShell.Cmdlets.Marketplace.Models.Api20210601.IPrivateStore

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT `<IMarketplaceIdentity>`: Parameter Identitas
  - `[AdminRequestApprovalId <String>]`: ID persetujuan permintaan admin untuk membuat atau memperbarui
  - `[CollectionId <String>]`: ID koleksi
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[OfferId <String>]`: ID penawaran yang akan diperbarui atau dihapus
  - `[PrivateStoreId <String>]`: ID penyimpanan - harus menggunakan ID penyewa
  - `[RequestApprovalId <String>]`: ID persetujuan permintaan untuk membuat atau memperbarui

## RELATED LINKS

