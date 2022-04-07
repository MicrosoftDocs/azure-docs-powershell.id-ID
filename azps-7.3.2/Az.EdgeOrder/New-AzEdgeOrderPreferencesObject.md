---
external help file: ''
Module Name: Az.EdgeOrder
online version: https://docs.microsoft.com/powershell/module/az.EdgeOrder/new-AzEdgeOrderPreferencesObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EdgeOrder/help/New-AzEdgeOrderPreferencesObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EdgeOrder/help/New-AzEdgeOrderPreferencesObject.md
ms.openlocfilehash: 9854a5b65a8dde6b85c7df454e25d74d04004fc6
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140402843"
---
# New-AzEdgeOrderPreferencesObject

## SYNOPSIS
Buat objek dalam memori untuk Preferensi.

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
PS C:\> $preference = New-AzEdgeOrderPreferencesObject -EncryptionPreference @{DoubleEncryptionStatus = "Disabled"} -TransportPreference @{PreferredShipmentType = "MicrosoftManaged"} -ManagementResourcePreference @{PreferredManagementResourceId = "/subscriptions/managementSubscriptionId/resourceGroups/resourceGroupName/providers/Microsoft.DataBoxEdge/DataBoxEdgeDevices/1GPUtest"}
```

Membuat objek preferensi dalam memori untuk mengatur preferensi sumber daya transpor, enkripsi, dan manajemen.

## PARAMETERS

### -EncryptionPreference
Preferensi yang terkait dengan Enkripsi.
Untuk membuat, lihat bagian CATATAN untuk properti ENCRYPTIONPREFERENCE dan membuat tabel hash.

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
Preferensi terkait dengan sumber daya Manajemen.
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
Untuk membuat, lihat bagian CATATAN untuk properti NOTIFICATIONPREFERENCE dan membuat tabel hash.

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
Untuk membuat, lihat bagian CATATAN untuk properti TRANSPORTPREFERENCE dan membuat tabel hash.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.EdgeOrder.Models.Api20211201.Preferences

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


ENCRYPTIONPREFERENCE <IEncryptionPreferences>: Preferensi yang terkait dengan Enkripsi.
  - `[DoubleEncryptionStatus <DoubleEncryptionStatus?>]`: Status enkripsi ganda saat dimasukkan oleh pelanggan. Parameter ini wajib diberikan jika kebijakan 'Tolak' atau 'Dinonaktifkan' dikonfigurasi.

MANAGEMENTRESOURCEPREFERENCE <IManagementResourcePreferences>: Preferensi yang terkait dengan sumber daya Manajemen.
  - `[PreferredManagementResourceId <String>]`: ID SUMBER daya manajemen pilihan pelanggan ARM

NOTIFICATIONPREFERENCE <INotificationPreference[]>: Preferensi pemberitahuan.
  - `SendNotification <Boolean>`: Pemberitahuan diperlukan atau tidak.
  - `StageName <NotificationStageName>`: Nama tahapan.

TRANSPORTPREFERENCE <ITransportPreferences>: Preferensi terkait dengan logistik pengiriman pesanan.
  - `PreferredShipmentType <TransportShipmentTypes>`: Menunjukkan tipe Logistik Pengiriman yang lebih disukai pelanggan.

## RELATED LINKS

