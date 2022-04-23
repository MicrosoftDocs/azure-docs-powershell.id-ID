---
external help file: ''
Module Name: Az.EdgeOrder
online version: https://docs.microsoft.com/powershell/module/az.edgeorder/invoke-azedgeorderreturnorderitem
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EdgeOrder/help/Invoke-AzEdgeOrderReturnOrderItem.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/EdgeOrder/help/Invoke-AzEdgeOrderReturnOrderItem.md
ms.openlocfilehash: 4ddaeaec12c26c2e1e9da956d6e5cd0b4e043769
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143287109"
---
# Invoke-AzEdgeOrderReturnOrderItem

## SYNOPSIS
Mengembalikan item pesanan.

## SYNTAX

### ReturnExpanded (Default)
```
Invoke-AzEdgeOrderReturnOrderItem -OrderItemName <String> -ResourceGroupName <String> -ReturnReason <String>
 [-SubscriptionId <String>] [-ReturnAddressContactDetail <IContactDetails>]
 [-ReturnAddressShippingAddress <IShippingAddress>] [-ServiceTag <String>] [-ShippingBoxRequired]
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-PassThru] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### ReturnViaIdentityExpanded
```
Invoke-AzEdgeOrderReturnOrderItem -InputObject <IEdgeOrderIdentity> -ReturnReason <String>
 [-ReturnAddressContactDetail <IContactDetails>] [-ReturnAddressShippingAddress <IShippingAddress>]
 [-ServiceTag <String>] [-ShippingBoxRequired] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-PassThru]
 [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Mengembalikan item pesanan.

## EXAMPLES

### Contoh 1: Command untuk memulai orderItem return
```powershell
Invoke-AzEdgeOrderReturnOrderItem -OrderItemName "OrderItem-211115074927900249117427" -ResourceGroupName "resourceGroupName" -ReturnReason "Test Order Return" -SubscriptionId "SubscriptionId"
```

Memanggil pengembalian orderItem

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

### -InputObject
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.EdgeOrder.Models.IEdgeOrderIdentity
Parameter Sets: ReturnViaIdentityExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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

### -OrderItemName
Nama item pesanan

```yaml
Type: System.String
Parameter Sets: ReturnExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Mengembalikan true ketika perintah berhasil

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

### -ResourceGroupName
Nama grup sumber daya.
Nama ini tidak peka huruf besar kecil.

```yaml
Type: System.String
Parameter Sets: ReturnExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReturnAddressContactDetail
Detail kontak untuk alamat Untuk membangun, lihat bagian CATATAN untuk properti RETURNADDRESSCONTACTDETAIL dan membuat tabel hash.

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

### -ReturnAddressShippingAddress
Detail pengiriman untuk alamat Untuk membangun, lihat bagian CATATAN untuk properti RETURNADDRESSSHIPPINGADDRESS dan membuat tabel hash.

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

### -ReturnReason
Kembalikan Alasan.

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

### -ServiceTag
Tag layanan (terletak di sudut kanan bawah perangkat)

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ShippingBoxRequired
Kotak Pengiriman diperlukan

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

### -SubscriptionId
ID langganan target.

```yaml
Type: System.String
Parameter Sets: ReturnExpanded
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
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

### Microsoft.Azure.PowerShell.Cmdlets.EdgeOrder.Models.IEdgeOrderIdentity

## OUTPUTS

### System.Boolean

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IEdgeOrderIdentity>: Parameter Identitas
  - `[AddressName <String>]`: Nama alamat Sumber Daya dalam grup sumber daya yang ditentukan. panjang nama alamat harus antara 3 dan 24 karakter dan hanya menggunakan alfanumerik dan garis bawah
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[Location <String>]`: Nama kawasan Azure.
  - `[OrderItemName <String>]`: Nama item pesanan
  - `[OrderName <String>]`: Nama pesanan
  - `[ResourceGroupName <String>]`: Nama grup sumber daya. Nama ini tidak peka huruf besar kecil.
  - `[SubscriptionId <String>]`: ID langganan target.

RETURNADDRESSCONTACTDETAIL <IContactDetails>: Detail kontak untuk alamat
  - `ContactName <String>`: Nama kontak orang tersebut.
  - `EmailList <String[]>`: Daftar Email-id yang akan diberi tahu tentang kemajuan pekerjaan.
  - `Phone <String>`: Telepon nomor kontak.
  - `[Mobile <String>]`: Nomor ponsel orang yang dihubungi.
  - `[PhoneExtension <String>]`: Telepon nomor ekstensi kontak.

RETURNADDRESSSHIPPINGADDRESS <IShippingAddress>: Detail pengiriman untuk alamat
  - `Country <String>`: Nama Negara.
  - `StreetAddress1 <String>`: Baris Alamat Jalan 1.
  - `[AddressType <AddressType?>]`: Jenis alamat.
  - `[City <String>]`: Nama Kota.
  - `[CompanyName <String>]`: Nama perusahaan.
  - `[PostalCode <String>]`: Kode pos.
  - `[StateOrProvince <String>]`: Nama Negara Bagian atau Provinsi.
  - `[StreetAddress2 <String>]`: Baris Alamat Jalan 2.
  - `[StreetAddress3 <String>]`: Baris Alamat Jalan 3.
  - `[ZipExtendedCode <String>]`: Kode Pos Diperpanjang.

## RELATED LINKS

