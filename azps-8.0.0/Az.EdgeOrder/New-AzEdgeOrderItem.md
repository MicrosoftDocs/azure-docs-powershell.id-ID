---
external help file: ''
Module Name: Az.EdgeOrder
online version: https://docs.microsoft.com/powershell/module/az.edgeorder/new-azedgeorderitem
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EdgeOrder/help/New-AzEdgeOrderItem.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EdgeOrder/help/New-AzEdgeOrderItem.md
ms.openlocfilehash: a8aa7bd4564dce57bec223a11793a667b5f15e89
ms.sourcegitcommit: 5df8b100721844736630242c724da453a2168434
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/26/2022
ms.locfileid: "146618644"
---
# New-AzEdgeOrderItem

## SYNOPSIS
Membuat item pesanan.
Item pesanan yang ada tidak dapat diperbarui dengan api ini dan sebaliknya harus diperbarui dengan API Perbarui item pesanan.

## SYNTAX

```
New-AzEdgeOrderItem -Name <String> -ResourceGroupName <String> -ForwardAddressContactDetail <IContactDetails>
 -Location <String> -OrderId <String> -OrderItemDetail <IOrderItemDetails> [-SubscriptionId <String>]
 [-ForwardShippingAddress <IShippingAddress>] [-Tag <Hashtable>] [-DefaultProfile <PSObject>] [-AsJob]
 [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Membuat item pesanan.
Item pesanan yang ada tidak dapat diperbarui dengan api ini dan sebaliknya harus diperbarui dengan API Perbarui item pesanan.

## EXAMPLES

### Contoh 1: Membuat orderItem baru
```powershell
$contactDetail = New-AzEdgeOrderContactDetailsObject -ContactName ContactName -EmailList @("emailId") -Phone Phone
$ShippingDetails = New-AzEdgeOrderShippingAddressObject -StreetAddress1 "101 TOWNSEND ST" -StateOrProvince "CA" -Country "US" -City "San Francisco" -PostalCode "94107" -AddressType "Commercial"
$HierarchyInformation=New-AzEdgeOrderHierarchyInformationObject -ProductFamilyName "azurestackedge" -ProductLineName "azurestackedge" -ProductName "azurestackedgegpu" -ConfigurationName "EdgeP_High"
$details = New-AzEdgeOrderOrderItemDetailsObject -OrderItemType "Purchase"  -ProductDetail  @{"HierarchyInformation"=$HierarchyInformation}
$orderItem = New-AzEdgeOrderItem -Name "examplePowershell" -ResourceGroupName ResourceGroup -ForwardAddressContactDetail $contactDetail -Location "eastus" -OrderId "/subscriptions/SubscriptionId/resourceGroups/resourceGroupName/providers/Microsoft.EdgeOrder/locations/eastus/orders/pwOrderItem11" -OrderItemDetail $details -SubscriptionId SubscriptionId -ForwardShippingAddress $ShippingDetails

$orderItem = New-AzEdgeOrderItem -Name "examplePowershell" -ResourceGroupName "resourceGroupName" -ForwardAddressContactDetail $contactDetail -Location "eastus" -OrderId "/subscriptions/SubscriptionId/resourceGroups/resourceGroupName/providers/Microsoft.EdgeOrder/locations/eastus/orders/pwOrderItem11" -OrderItemDetail $details -SubscriptionId SubscriptionId -ForwardShippingAddress $ShippingDetails
$DebugPreference = "Continue"
# You can use `$DebugPreference = "Continue"`, with any example/usecase to get exact details of error in below format when creation command fails.
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
$orderItem = New-AzEdgeOrderItem -Name "examplePowershell" -ResourceGroupName "resourceGroupName" -ForwardAddressContactDetail $contactDetail -Location "eastus" -OrderId "/subscriptions/SubscriptionId/resourceGroups/resourceGroupName/providers/Microsoft.EdgeOrder/locations/eastus/orders/pwOrderItem11" -OrderItemDetail $details -SubscriptionId SubscriptionId -ForwardShippingAddress $ShippingDetails
$orderItem | Format-List
```

```output
ForwardAddressContactDetail    : Microsoft.Azure.PowerShell.Cmdlets.EdgeOrder.Models.Api20211201.ContactDetails
ForwardAddressShippingAddress  : Microsoft.Azure.PowerShell.Cmdlets.EdgeOrder.Models.Api20211201.ShippingAddress
ForwardAddressValidationStatus : Valid
Id                             : /subscriptions/SubscriptionId/resourceGroups/resourceGroupName/providers/Microsoft.EdgeOrder/orderItems/examplePowershell
Location                       : eastus
Name                           : examplePowershell
OrderId                        : /subscriptions/SubscriptionId/resourceGroups/resourceGroupName/providers/Microsoft.EdgeOrder/locations/eastus/orders/pwOrderItem11
OrderItemDetail                : Microsoft.Azure.PowerShell.Cmdlets.EdgeOrder.Models.Api20211201.OrderItemDetails
ReturnAddressContactDetail     : Microsoft.Azure.PowerShell.Cmdlets.EdgeOrder.Models.Api20211201.ContactDetails
ReturnAddressShippingAddress   : Microsoft.Azure.PowerShell.Cmdlets.EdgeOrder.Models.Api20211201.ShippingAddress
ReturnAddressValidationStatus  :
StartTime                      : 11/16/2021 10:34:51 AM
SystemData                     : Microsoft.Azure.PowerShell.Cmdlets.EdgeOrder.Models.Api20.SystemData
Tag                            : Microsoft.Azure.PowerShell.Cmdlets.EdgeOrder.Models.Api20.TrackedResourceTags
Type                           : Microsoft.EdgeOrder/orderItems

```

Membuat orderItem baru.

### Contoh 2: Membuat orderItem baru dengan preferensi yang diatur untuk sumber daya transportasi, enkripsi, dan manajemen
```powershell
$contactDetail = New-AzEdgeOrderContactDetailsObject -ContactName "ContactName2" -EmailList $env.EmailList -Phone $env.Phone
$ShippingDetails = New-AzEdgeOrderShippingAddressObject -StreetAddress1 $env.StreetAddress1 -StateOrProvince $env.StateOrProvince -Country $env.Country -City $env.City -PostalCode $env.PostalCode -AddressType $env.AddressType
$HierarchyInformation=New-AzEdgeOrderHierarchyInformationObject -ProductFamilyName "azurestackedge" -ProductLineName "azurestackedge" -ProductName "azurestackedgegpu" -ConfigurationName "EdgeP_High"
$preference = New-AzEdgeOrderPreferencesObject -EncryptionPreference @{DoubleEncryptionStatus = "Disabled"} -TransportPreference @{PreferredShipmentType = "MicrosoftManaged"} -ManagementResourcePreference @{PreferredManagementResourceId = "/subscriptions/managementSubscriptionId/resourceGroups/resourceGroupName/providers/Microsoft.DataBoxEdge/DataBoxEdgeDevices/1GPUtest"}
$details = New-AzEdgeOrderOrderItemDetailsObject -OrderItemType "Purchase"  -ProductDetail  @{"HierarchyInformation"=$HierarchyInformation} -Preference $preference
New-AzEdgeOrderItem -Name "OrderItemNameWithPref" -ResourceGroupName "resourceGroupName" -ForwardAddressContactDetail $contactDetail -Location "eastus" -OrderId "/subscriptions/SubscriptionId/resourceGroups/resourceGroupName/providers/Microsoft.EdgeOrder/locations/eastus/orders/pwPrefOrder" -OrderItemDetail $details -SubscriptionId $env.SubscriptionId -ForwardShippingAddress $ShippingDetails
```

```output
Location Name                  Type
-------- ----                  ----
eastus   OrderItemNameWithPref Microsoft.EdgeOrder/orderItems
```

Membuat orderItem baru dengan preferensi yang ditetapkan untuk transportasi, enkripsi, dan sumber daya manajemen

## PARAMETERS

### -AsJob
Jalankan perintah sebagai pekerjaan

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
Detail kontak untuk alamat Untuk membangun, lihat bagian CATATAN untuk properti FORWARDADDRESSCONTACTDETAIL dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.EdgeOrder.Models.Api20211201.IContactDetails
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ForwardShippingAddress
Detail pengiriman untuk alamat Untuk dibangun, lihat bagian CATATAN untuk properti FORWARDSHIPPINGADDRESS dan buat tabel hash.

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

### -Lokasi
Lokasi geografis tempat sumber daya berada

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Nama item pesanan

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: OrderItemName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoWait
Jalankan perintah secara asinkron

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

### -OrderId
Id pesanan tempat item pesanan berada

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OrderItemDetail
Mewakili detail item pesanan.
Untuk membuat, lihat bagian CATATAN untuk properti ORDERITEMDETAIL dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.EdgeOrder.Models.Api20211201.IOrderItemDetails
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.
Nama tidak peka huruf besar/kecil.

```yaml
Type: System.String
Parameter Sets: (All)
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
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tag
Tag sumber daya.

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

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

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
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.EdgeOrder.Models.Api20211201.IOrderItemResource

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


FORWARDADDRESSCONTACTDETAIL `<IContactDetails>`: Detail kontak untuk alamat
  - `ContactName <String>`: Nama kontak orang tersebut.
  - `EmailList <String[]>`: Daftar Email-id yang akan diberi tahu tentang kemajuan pekerjaan.
  - `Phone <String>`: Telepon nomor kontak.
  - `[Mobile <String>]`: Nomor ponsel kontak.
  - `[PhoneExtension <String>]`: Telepon nomor ekstensi kontak.

FORWARDSHIPPINGADDRESS `<IShippingAddress>`: Detail pengiriman untuk alamat
  - `Country <String>`: Nama Negara.
  - `StreetAddress1 <String>`: Alamat Jalan baris 1.
  - `[AddressType <AddressType?>]`: Jenis alamat.
  - `[City <String>]`: Nama Kota.
  - `[CompanyName <String>]`: Nama perusahaan.
  - `[PostalCode <String>]`: Kode pos.
  - `[StateOrProvince <String>]`: Nama Negara Bagian atau Provinsi.
  - `[StreetAddress2 <String>]`: Alamat Jalan baris 2.
  - `[StreetAddress3 <String>]`: Alamat Jalan baris 3.
  - `[ZipExtendedCode <String>]`: Kode Pos yang diperluas.

ORDERITEMDETAIL `<IOrderItemDetails>`: Mewakili detail item pesanan.
  - `OrderItemType <OrderItemType>`: Jenis item pesanan.
  - `ProductDetail <IProductDetails>`: Pengidentifikasi unik untuk konfigurasi.
    - `HierarchyInformation <IHierarchyInformation>`: Hierarki produk yang secara unik mengidentifikasi produk
      - `[ConfigurationName <String>]`: Mewakili nama konfigurasi yang secara unik mengidentifikasi konfigurasi
      - `[ProductFamilyName <String>]`: Mewakili nama keluarga produk yang secara unik mengidentifikasi keluarga produk
      - `[ProductLineName <String>]`: Mewakili nama baris produk yang secara unik mengidentifikasi lini produk
      - `[ProductName <String>]`: Mewakili nama produk yang secara unik mengidentifikasi produk
  - `[NotificationEmailList <String[]>]`: Daftar email pemberitahuan tambahan
  - `[Preference <IPreferences>]`: Preferensi pemberitahuan pelanggan
    - `[EncryptionPreference <IEncryptionPreferences>]`: Preferensi yang terkait dengan Enkripsi.
      - `[DoubleEncryptionStatus <DoubleEncryptionStatus?>]`: Status enkripsi ganda seperti yang dimasukkan oleh pelanggan. Wajib untuk memberikan parameter ini jika kebijakan 'Tolak' atau 'Dinonaktifkan' dikonfigurasi.
    - `[ManagementResourcePreference <IManagementResourcePreferences>]`: Preferensi yang terkait dengan sumber daya Manajemen.
      - `[PreferredManagementResourceId <String>]`: ID ARM sumber daya Manajemen pilihan pelanggan
    - `[NotificationPreference <INotificationPreference[]>]`: Preferensi pemberitahuan.
      - `SendNotification <Boolean>`: Pemberitahuan diperlukan atau tidak.
      - `StageName <NotificationStageName>`: Nama panggung.
    - `[TransportPreference <ITransportPreferences>]`: Preferensi yang terkait dengan logistik pengiriman pesanan.
      - `PreferredShipmentType <TransportShipmentTypes>`: Menunjukkan jenis Logistik Pengiriman yang disukai pelanggan.

## RELATED LINKS

