---
external help file: ''
Module Name: Az.EdgeOrder
online version: https://docs.microsoft.com/powershell/module/az.edgeorder/update-azedgeorderitem
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EdgeOrder/help/Update-AzEdgeOrderItem.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EdgeOrder/help/Update-AzEdgeOrderItem.md
ms.openlocfilehash: 1b65cddde1db788aff54240243f79bd5ef18d8ed
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138278364"
---
# Update-AzEdgeOrderItem

## SYNOPSIS
Memperbarui properti item pesanan yang sudah ada.

## SYNTAX

### UpdateExpanded (Default)
```
Update-AzEdgeOrderItem -Name <String> -ResourceGroupName <String> [-SubscriptionId <String>]
 [-ForwardAddressContactDetail <IContactDetails>] [-ForwardAddressShippingAddress <IShippingAddress>]
 [-NotificationEmailList <String[]>] [-Preference <IPreferences>] [-Tag <Hashtable>]
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### UpdateViaIdentityExpanded
```
Update-AzEdgeOrderItem -InputObject <IEdgeOrderIdentity> [-ForwardAddressContactDetail <IContactDetails>]
 [-ForwardAddressShippingAddress <IShippingAddress>] [-NotificationEmailList <String[]>]
 [-Preference <IPreferences>] [-Tag <Hashtable>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm]
 [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Memperbarui properti item pesanan yang sudah ada.

## EXAMPLES

### Contoh 1: Update orderItem
```powershell
PS C:\> $contactDetail = New-AzEdgeOrderContactDetailsObject -ContactName "ContactName2" -EmailList @("emailId") -Phone Phone
PS C:\> $DebugPreference = "Continue"
# You can use `$DebugPreference = "Continue"`, with any example/usecase to get exact details of error in below format when update command fails.
# {
#   "Error": {
#     "Code": "StaticValidationGenericCountryCodeHasInvalidLength",
#     "Message": "The attribute country code does not meet length constraints.\r\nEnter a value with 2 characters for country code.",
#     "Details": [
#       null
#     ],
#     "Target": null
#   }
# } 
PS C:\> $updatedOrderItem = Update-AzEdgeOrderItem -Name "examplePowershell" -ResourceGroupName "resourceGroupName" -SubscriptionId SubscriptionId -ForwardAddressContactDetail $contactDetail

PS C:\> $updatedOrderItem.ForwardAddressContactDetail | fl

ContactName    : ContactName2
EmailList      : {useremailId}
Mobile         :
Phone          : 1234567891
PhoneExtension :
```

Perbarui detail orderItem.

## PARAMETERS

### -AsJob
Menjalankan perintah sebagai pekerjaan

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

### -ForwardAddressContactDetail
Detail kontak untuk konstruksi alamat Kepada, lihat bagian CATATAN untuk properti FORWARDADDRESSCONTACTDETAIL dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.EdgeOrder.Models.Api20211201.IContactDetails
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ForwardAddressShippingAddress
Detail pengiriman untuk alamat Untuk dibuat, lihat bagian CATATAN untuk properti FORWARDADDRESSSHIPPINGADDRESS dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.EdgeOrder.Models.Api20211201.IShippingAddress
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Parameter Identitas Untuk membuat, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.EdgeOrder.Models.IEdgeOrderIdentity
Parameter Sets: UpdateViaIdentityExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nama
Nama item pesanan

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases: OrderItemName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -NoWait
Menjalankan perintah secara asinkron

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

### -Preferensi
Preferensi pelanggan.
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

### -ResourceGroupName
Nama grup sumber daya.
Namanya peka huruf besar/huruf.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
ID langganan target.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tag
Daftar pasangan nilai kunci yang menjelaskan sumber daya.
Tag ini bisa digunakan dalam menampilkan dan mengelompokkan sumber daya ini (di seluruh grup sumber daya).

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

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
Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.EdgeOrder.Models.IEdgeOrderIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.EdgeOrder.Models.Api20211201.IOrderItemResource

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


FORWARDADDRESSCONTACTDETAIL <IContactDetails>: Detail kontak untuk alamat
  - `ContactName <String>`: Nama kontak orang tersebut.
  - `EmailList <String[]>`: Daftar Id Email untuk diberi tahu tentang kemajuan pekerjaan.
  - `Phone <String>`: Telepon nomor kontak.
  - `[Mobile <String>]`: Nomor ponsel orang yang dapat dihubungi.
  - `[PhoneExtension <String>]`: Telepon nomor ekstensi orang kontak.

FORWARDADDRESSSHIPPINGADDRESS <IShippingAddress>: Detail pengiriman alamat
  - `Country <String>`: Nama Negara.
  - `StreetAddress1 <String>`: Alamat Jalan baris 1.
  - `[AddressType <AddressType?>]`: Tipe alamat.
  - `[City <String>]`: Nama Kota.
  - `[CompanyName <String>]`: Nama perusahaan.
  - `[PostalCode <String>]`: Kode pos.
  - `[StateOrProvince <String>]`: Nama Negara Bagian atau Provinsi.
  - `[StreetAddress2 <String>]`: Alamat Jalan baris 2.
  - `[StreetAddress3 <String>]`: Baris Alamat Jalan 3.
  - `[ZipExtendedCode <String>]`: Kode pos diperluas.

INPUTOBJECT <IEdgeOrderIdentity>: Parameter Identitas
  - `[AddressName <String>]`: Nama Sumber Daya alamat dalam grup sumber daya yang ditentukan. nama alamat harus panjang antara 3 dan 24 karakter dan gunakan alfanumerik dan garis bawah saja
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[Location <String>]`: Nama kawasan Azure.
  - `[OrderItemName <String>]`: Nama item pesanan
  - `[OrderName <String>]`: Nama pesanan
  - `[ResourceGroupName <String>]`: Nama grup sumber daya. Namanya peka huruf besar/huruf.
  - `[SubscriptionId <String>]`: ID langganan target.

PREFERENSI <IPreferences>: Preferensi pelanggan.
  - `[EncryptionPreference <IEncryptionPreferences>]`: Preferensi yang terkait dengan Enkripsi.
    - `[DoubleEncryptionStatus <DoubleEncryptionStatus?>]`: Status enkripsi ganda saat dimasukkan oleh pelanggan. Parameter ini wajib diberikan jika kebijakan 'Tolak' atau 'Dinonaktifkan' dikonfigurasi.
  - `[ManagementResourcePreference <IManagementResourcePreferences>]`: Preferensi terkait dengan sumber daya Manajemen.
    - `[PreferredManagementResourceId <String>]`: ID SUMBER daya manajemen pilihan pelanggan ARM
  - `[NotificationPreference <INotificationPreference[]>]`: Preferensi pemberitahuan.
    - `SendNotification <Boolean>`: Pemberitahuan diperlukan atau tidak.
    - `StageName <NotificationStageName>`: Nama tahapan.
  - `[TransportPreference <ITransportPreferences>]`: Preferensi terkait logistik pengiriman pesanan.
    - `PreferredShipmentType <TransportShipmentTypes>`: Menunjukkan tipe Logistik Pengiriman yang lebih disukai pelanggan.

## RELATED LINKS

