---
external help file: ''
Module Name: Az.EdgeOrder
online version: https://docs.microsoft.com/powershell/module/az.EdgeOrder/new-AzEdgeOrderPreferencesObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EdgeOrder/help/New-AzEdgeOrderPreferencesObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EdgeOrder/help/New-AzEdgeOrderPreferencesObject.md
ms.openlocfilehash: 80b1ecaea5077e7a0a331287db920296d82f69cf
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141837507"
---
# New-AzEdgeOrderPreferencesObject

## SYNOPSIS
Membuat objek dalam memori untuk Preferensi.

## SYNTAX

```
New-AzEdgeOrderPreferencesObject [-EncryptionPreference <IEncryptionPreferences>]
 [-ManagementResourcePreference <IManagementResourcePreferences>]
 [-NotificationPreference <INotificationPreference[]>] [-TransportPreference <ITransportPreferences>]
 [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk Preferensi.

## EXAMPLES

### Contoh 1: Membuat objek preferensi
```powershell
$preference = New-AzEdgeOrderPreferencesObject -EncryptionPreference @{DoubleEncryptionStatus = "Disabled"} -TransportPreference @{PreferredShipmentType = "MicrosoftManaged"} -ManagementResourcePreference @{PreferredManagementResourceId = "/subscriptions/managementSubscriptionId/resourceGroups/resourceGroupName/providers/Microsoft.DataBoxEdge/DataBoxEdgeDevices/1GPUtest"}
```

Membuat objek preferensi dalam memori untuk mengatur preferensi sumber daya transportasi, enkripsi, dan manajemen.

## PARAMETERS

### -EncryptionPreference
Preferensi yang terkait dengan Enkripsi.
Untuk membangun, lihat bagian CATATAN untuk properti ENCRYPTIONPREFERENCE dan membuat tabel hash.

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
Untuk membangun, lihat bagian CATATAN untuk properti MANAGEMENTRESOURCEPREFERENCE dan membuat tabel hash.

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
Untuk membangun, lihat bagian CATATAN untuk properti NOTIFICATIONPREFERENCE dan membuat tabel hash.

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
Untuk membangun, lihat bagian CATATAN untuk properti TRANSPORTPREFERENCE dan membuat tabel hash.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.EdgeOrder.Models.Api20211201.Preferences

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


ENCRYPTIONPREFERENCE <IEncryptionPreferences>: Preferensi yang terkait dengan Enkripsi.
  - `[DoubleEncryptionStatus <DoubleEncryptionStatus?>]`: Status enkripsi ganda seperti yang dimasukkan oleh pelanggan. Diwajibkan untuk memberikan parameter ini jika kebijakan 'Tolak' atau 'Dinonaktifkan' dikonfigurasi.

MANAGEMENTRESOURCEPREFERENCE <IManagementResourcePreferences>: Preferensi yang terkait dengan sumber daya Manajemen.
  - `[PreferredManagementResourceId <String>]`: ID ARM sumber daya Manajemen pilihan pelanggan

NOTIFICATIONPREFERENCE <INotificationPreference[]>: Preferensi pemberitahuan.
  - `SendNotification <Boolean>`: Pemberitahuan diperlukan atau tidak.
  - `StageName <NotificationStageName>`: Nama panggung.

TRANSPORTPREFERENCE <ITransportPreferences>: Preferensi yang terkait dengan logistik pengiriman pesanan.
  - `PreferredShipmentType <TransportShipmentTypes>`: Menunjukkan jenis Logistik Pengiriman yang lebih disukai pelanggan.

## RELATED LINKS

