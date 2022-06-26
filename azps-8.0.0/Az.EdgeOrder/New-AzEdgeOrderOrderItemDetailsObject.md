---
external help file: ''
Module Name: Az.EdgeOrder
online version: https://docs.microsoft.com/powershell/module/az.EdgeOrder/new-AzEdgeOrderOrderItemDetailsObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EdgeOrder/help/New-AzEdgeOrderOrderItemDetailsObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EdgeOrder/help/New-AzEdgeOrderOrderItemDetailsObject.md
ms.openlocfilehash: e15f8a09b35c056f4f8a5fcfa69c25db725271ae
ms.sourcegitcommit: 5df8b100721844736630242c724da453a2168434
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/26/2022
ms.locfileid: "146641504"
---
# New-AzEdgeOrderOrderItemDetailsObject

## SYNOPSIS
Buat objek dalam memori untuk OrderItemDetails.

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
$HierarchyInformation=New-AzEdgeOrderHierarchyInformationObject -ProductFamilyName "azurestackedge" -ProductLineName "azurestackedge" -ProductName "azurestackedgegpu" -ConfigurationName "EdgeP_High"
$details = New-AzEdgeOrderOrderItemDetailsObject -OrderItemType "Purchase"  -ProductDetail  @{"HierarchyInformation"=$HierarchyInformation}
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
Jenis item pesanan.

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
Untuk membuat, lihat bagian CATATAN untuk properti PREFERENSI dan membuat tabel hash.

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
Untuk membuat, lihat bagian CATATAN untuk properti PRODUCTDETAIL dan buat tabel hash.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.EdgeOrder.Models.Api20211201.OrderItemDetails

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


PREFERENSI `<IPreferences>`: Preferensi pemberitahuan pelanggan.
  - `[EncryptionPreference <IEncryptionPreferences>]`: Preferensi yang terkait dengan Enkripsi.
    - `[DoubleEncryptionStatus <DoubleEncryptionStatus?>]`: Status enkripsi ganda seperti yang dimasukkan oleh pelanggan. Wajib untuk memberikan parameter ini jika kebijakan 'Tolak' atau 'Dinonaktifkan' dikonfigurasi.
  - `[ManagementResourcePreference <IManagementResourcePreferences>]`: Preferensi yang terkait dengan sumber daya Manajemen.
    - `[PreferredManagementResourceId <String>]`: ID ARM sumber daya Manajemen pilihan pelanggan
  - `[NotificationPreference <INotificationPreference[]>]`: Preferensi pemberitahuan.
    - `SendNotification <Boolean>`: Pemberitahuan diperlukan atau tidak.
    - `StageName <NotificationStageName>`: Nama panggung.
  - `[TransportPreference <ITransportPreferences>]`: Preferensi yang terkait dengan logistik pengiriman pesanan.
    - `PreferredShipmentType <TransportShipmentTypes>`: Menunjukkan jenis Logistik Pengiriman yang disukai pelanggan.

PRODUCTDETAIL `<IProductDetails>`: Pengidentifikasi unik untuk konfigurasi.
  - `HierarchyInformation <IHierarchyInformation>`: Hierarki produk yang secara unik mengidentifikasi produk
    - `[ConfigurationName <String>]`: Mewakili nama konfigurasi yang secara unik mengidentifikasi konfigurasi
    - `[ProductFamilyName <String>]`: Mewakili nama keluarga produk yang secara unik mengidentifikasi keluarga produk
    - `[ProductLineName <String>]`: Mewakili nama baris produk yang secara unik mengidentifikasi lini produk
    - `[ProductName <String>]`: Mewakili nama produk yang secara unik mengidentifikasi produk

## RELATED LINKS

