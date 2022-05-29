---
external help file: ''
Module Name: Az.EdgeOrder
online version: https://docs.microsoft.com/powershell/module/az.EdgeOrder/new-AzEdgeOrderPreferencesObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EdgeOrder/help/New-AzEdgeOrderPreferencesObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EdgeOrder/help/New-AzEdgeOrderPreferencesObject.md
ms.openlocfilehash: ed4b86d6cd70e26402ca6c9ce4ef260c97d49548
ms.sourcegitcommit: 321c644cf2161807a71e1af318fc5c5311d22e25
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/25/2022
ms.locfileid: "145769952"
---
# New-AzEdgeOrderPreferencesObject

## SYNOPSIS
Buat objek dalam memori untuk Preferensi.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.edgeorder/new-azedgeorderpreferencesobject) untuk informasi terbaru.

## SYNTAX

```
New-AzEdgeOrderPreferencesObject [-EncryptionPreference <IEncryptionPreferences>]
 [-ManagementResourcePreference <IManagementResourcePreferences>]
 [-NotificationPreference <INotificationPreference[]>] [-TransportPreference <ITransportPreferences>]
 [<CommonParameters>]
```

## DESCRIPTION
Buat objek dalam memori untuk Preferensi.

## EXAMPLES

### Contoh 1: Membuat objek preferensi
```powershell
$preference = New-AzEdgeOrderPreferencesObject -EncryptionPreference @{DoubleEncryptionStatus = "Disabled"} -TransportPreference @{PreferredShipmentType = "MicrosoftManaged"} -ManagementResourcePreference @{PreferredManagementResourceId = "/subscriptions/managementSubscriptionId/resourceGroups/resourceGroupName/providers/Microsoft.DataBoxEdge/DataBoxEdgeDevices/1GPUtest"}
```

Membuat objek preferensi dalam memori untuk mengatur preferensi sumber daya transportasi, enkripsi, dan manajemen.

## PARAMETERS

### -EncryptionPreference
Preferensi yang terkait dengan Enkripsi.
Untuk membuat, lihat bagian CATATAN untuk properti ENCRYPTIONPREFERENCE dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.EdgeOrder.Models.Api20211201.IEncryptionPreferences
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagementResourcePreference
Preferensi yang terkait dengan sumber daya Manajemen.
Untuk membuat, lihat bagian CATATAN untuk properti MANAGEMENTRESOURCEPREFERENCE dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.EdgeOrder.Models.Api20211201.IManagementResourcePreferences
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NotificationPreference
Preferensi pemberitahuan.
Untuk membuat, lihat bagian CATATAN untuk properti NOTIFICATIONPREFERENCE dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.EdgeOrder.Models.Api20211201.INotificationPreference[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TransportPreference
Preferensi yang terkait dengan logistik pengiriman pesanan.
Untuk membuat, lihat bagian CATATAN untuk properti TRANSPORTPREFERENCE dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.EdgeOrder.Models.Api20211201.ITransportPreferences
Parameter Sets: (All)
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

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.EdgeOrder.Models.Api20211201.Preferences

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


ENCRYPTIONPREFERENCE <IEncryptionPreferences>: Preferensi yang terkait dengan Enkripsi.
  - `[DoubleEncryptionStatus <DoubleEncryptionStatus?>]`: Status enkripsi ganda seperti yang dimasukkan oleh pelanggan. Wajib untuk memberikan parameter ini jika kebijakan 'Tolak' atau 'Dinonaktifkan' dikonfigurasi.

MANAGEMENTRESOURCEPREFERENCE <IManagementResourcePreferences>: Preferensi yang terkait dengan sumber daya Manajemen.
  - `[PreferredManagementResourceId <String>]`: ID ARM sumber daya Manajemen pilihan pelanggan

NOTIFICATIONPREFERENCE <INotificationPreference[]>: Preferensi pemberitahuan.
  - `SendNotification <Boolean>`: Pemberitahuan diperlukan atau tidak.
  - `StageName <NotificationStageName>`: Nama panggung.

TRANSPORTPREFERENCE <ITransportPreferences>: Preferensi yang terkait dengan logistik pengiriman pesanan.
  - `PreferredShipmentType <TransportShipmentTypes>`: Menunjukkan jenis Logistik Pengiriman yang disukai pelanggan.

## RELATED LINKS

