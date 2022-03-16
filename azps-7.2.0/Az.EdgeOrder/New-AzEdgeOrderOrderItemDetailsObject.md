---
external help file: ''
Module Name: Az.EdgeOrder
online version: https://docs.microsoft.com/powershell/module/az.EdgeOrder/new-AzEdgeOrderOrderItemDetailsObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EdgeOrder/help/New-AzEdgeOrderOrderItemDetailsObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EdgeOrder/help/New-AzEdgeOrderOrderItemDetailsObject.md
ms.openlocfilehash: 2f71653bbcb7a4f27458880e3a6a8054a532a315
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140124081"
---
# New-AzEdgeOrderOrderItemDetailsObject

## SYNOPSIS
Buat objek dalam memori untuk OrderItemDetails.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.edgeorder/new-azedgeorderorderitemdetailsobject) untuk informasi terkini.

## SYNTAX

```
New-AzEdgeOrderOrderItemDetailsObject -OrderItemType <OrderItemType> -ProductDetail <IProductDetails>
 [-NotificationEmailList <String[]>] [-Preference <IPreferences>] [<CommonParameters>]
```

## DESCRIPTION
Buat objek dalam memori untuk OrderItemDetails.

## EXAMPLES

### Contoh 1: Membuat objek orderItemDetails.
```powershell
PS C:\> $HierarchyInformation=New-AzEdgeOrderHierarchyInformationObject -ProductFamilyName "azurestackedge" -ProductLineName "azurestackedge" -ProductName "azurestackedgegpu" -ConfigurationName "EdgeP_High"
PS C:\> $details = New-AzEdgeOrderOrderItemDetailsObject -OrderItemType "Purchase"  -ProductDetail  @{"HierarchyInformation"=$HierarchyInformation}
```

Buat objek dalam memori untuk OrderItemDetails.

## PARAMETERS

### -NotificationEmailList
Daftar email pemberitahuan tambahan.

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

### -OrderItemType
Tipe item pesanan.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.EdgeOrder.Support.OrderItemType
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Preferensi
Preferensi pemberitahuan pelanggan.
Untuk membuat, lihat bagian CATATAN untuk properti PREFERENCE dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.EdgeOrder.Models.Api20211201.IPreferences
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProductDetail
Pengidentifikasi unik untuk konfigurasi.
Untuk membuat, lihat bagian CATATAN untuk properti PRODUCTDETAIL dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.EdgeOrder.Models.Api20211201.IProductDetails
Parameter Sets: (All)
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

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.EdgeOrder.Models.Api20211201.OrderItemDetails

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


PREFERENSI <IPreferences>: Preferensi pemberitahuan pelanggan.
  - `[EncryptionPreference <IEncryptionPreferences>]`: Preferensi yang terkait dengan Enkripsi.
    - `[DoubleEncryptionStatus <DoubleEncryptionStatus?>]`: Status enkripsi ganda saat dimasukkan oleh pelanggan. Parameter ini wajib diberikan jika kebijakan 'Tolak' atau 'Dinonaktifkan' dikonfigurasi.
  - `[ManagementResourcePreference <IManagementResourcePreferences>]`: Preferensi terkait dengan sumber daya Manajemen.
    - `[PreferredManagementResourceId <String>]`: ID SUMBER daya manajemen pilihan pelanggan ARM
  - `[NotificationPreference <INotificationPreference[]>]`: Preferensi pemberitahuan.
    - `SendNotification <Boolean>`: Pemberitahuan diperlukan atau tidak.
    - `StageName <NotificationStageName>`: Nama tahapan.
  - `[TransportPreference <ITransportPreferences>]`: Preferensi terkait logistik pengiriman pesanan.
    - `PreferredShipmentType <TransportShipmentTypes>`: Menunjukkan tipe Logistik Pengiriman yang lebih disukai pelanggan.

PRODUCTDETAIL <IProductDetails>: Pengidentifikasi unik untuk konfigurasi.
  - `HierarchyInformation <IHierarchyInformation>`: Hierarki produk yang mengidentifikasi produk secara unik
    - `[ConfigurationName <String>]`: Mewakili nama konfigurasi yang mengidentifikasi konfigurasi secara unik
    - `[ProductFamilyName <String>]`: Mewakili nama produk keluarga yang mengidentifikasi keluarga produk secara unik
    - `[ProductLineName <String>]`: Mewakili nama baris produk yang mengidentifikasi lini produk secara unik
    - `[ProductName <String>]`: Mewakili nama produk yang mengidentifikasi produk secara unik

## RELATED LINKS

