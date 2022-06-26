---
external help file: ''
Module Name: Az.DataBox
online version: https://docs.microsoft.com/powershell/module/az.databox/update-azdataboxjob
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataBox/help/Update-AzDataBoxJob.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataBox/help/Update-AzDataBoxJob.md
ms.openlocfilehash: b6651bd7990638d0ddf131b9d754c7364e6b0b11
ms.sourcegitcommit: 5df8b100721844736630242c724da453a2168434
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/26/2022
ms.locfileid: "146607054"
---
# Update-AzDataBoxJob

## SYNOPSIS
Updates properti pekerjaan yang ada.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.databox/update-azdataboxjob) untuk informasi terbaru.

## SYNTAX

```
Update-AzDataBoxJob -Name <String> -ResourceGroupName <String> [-SubscriptionId <String>] [-IfMatch <String>]
 [-ContactDetail <IContactDetails>] [-IdentityType <String>] [-KeyEncryptionKey <IKeyEncryptionKey>]
 [-ShippingAddress <IShippingAddress>] [-Tag <Hashtable>] [-UserAssignedIdentity <Hashtable>]
 [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Updates properti pekerjaan yang ada.

## EXAMPLES

### Contoh 1: Memperbarui enkripsi pekerjaan kotak data dari microsoft yang dikelola ke dikelola pelanggan dengan identitas yang ditetapkan pengguna 
```powershell
$keyEncryptionDetails = New-AzDataBoxKeyEncryptionKeyObject -KekType "CustomerManaged" -IdentityProperty @{Type = "UserAssigned"; UserAssignedResourceId = "/subscriptions/SubscriptionId/resourceGroups/resourceGroupName/providers/Microsoft.ManagedIdentity/userAssignedIdentities/identityName"} -KekUrl "keyIdentifier" -KekVaultResourceId "/subscriptions/SubscriptionId/resourceGroups/resourceGroupName/providers/Microsoft.KeyVault/vaults/keyVaultName"

$keyEncryptionDetails

KekType         KekUrl                                           KekVaultResourceId
-------         ------                                           ------------------
CustomerManaged keyIdentifier /subscriptions/SubscriptionId/resourceGroups/resourceGroupName/providers/Microsoft.KeyVault/vaults/keyVaultName
$DebugPreference = "Continue"
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
Update-AzDataBoxJob -Name "powershell10" -ResourceGroupName "resourceGroupName" -KeyEncryptionKey $keyEncryptionDetails -ContactDetail $contactDetail -ShippingAddress $ShippingDetails  -IdentityType "UserAssigned" -UserAssignedIdentity @{"/subscriptions/SubscriptionId/resourceGroups/resourceGroupName/providers/Microsoft.ManagedIdentity/userAssignedIdentities/identityName" = @{}}

Name         Location Status        TransferType  SkuName IdentityType DeliveryType Detail
----         -------- ------        ------------  ------- ------------ ------------ ------
Powershell10 WestUS   DeviceOrdered ImportToAzure DataBox UserAssigned NonScheduled Microsoft.Azure.PowerShell.Cmdlets.DataBox.Models.Api20210301.DataBoxJobDetails
```

Perbarui enkripsi pekerjaan kotak data dari microsoft yang dikelola ke dikelola pelanggan dengan identitas yang ditetapkan pengguna.

### Contoh 2: Memperbarui enkripsi pekerjaan kotak data dari microsoft yang dikelola ke pelanggan yang dikelola dengan identitas sistem dalam 2 pembaruan
```powershell
$databoxUpdate = Update-AzDataBoxJob -Name "pwshTestSAssigned" -ResourceGroupName "resourceGroupName" -ContactDetail $contactDetail -ShippingAddress $ShippingDetails  -IdentityType "SystemAssigned"

$databoxUpdate.Identity

PrincipalId                          TenantId                             Type
-----------                          --------                             ----
920850f5-9b6b-4017-a81a-3dcafe348be7 72f988bf-86f1-41af-91ab-2d7cd011db47 SystemAssigned

$keyEncryptionDetails = New-AzDataBoxKeyEncryptionKeyObject -KekType "CustomerManaged" -IdentityProperty @{Type = "SystemAssigned"} -KekUrl "keyIdentifier" -KekVaultResourceId "/subscriptions/SubscriptionId/resourceGroups/resourceGroupName/providers/Microsoft.KeyVault/vaults/keyVaultName"

$databoxUpdateWithCMK = Update-AzDataBoxJob -Name "pwshTestSAssigned" -ResourceGroupName "resourceGroupName" -ContactDetail $contactDetail -ShippingAddress $ShippingDetails  -KeyEncryptionKey $keyEncryptionDetails

$databoxUpdateWithCMK.Identity

PrincipalId                          TenantId                             Type
-----------                          --------                             ----
920850f5-9b6b-4017-a81a-3dcafe348be7 72f988bf-86f1-41af-91ab-2d7cd011db47 SystemAssigned

$databoxUpdateWithCMK.Detail.KeyEncryptionKey

KekType         KekUrl                                           KekVaultResourceId
-------         ------                                           ------------------
CustomerManaged keyIdentifier /subscriptions/SubscriptionId/resourceGroups/resourceGroupName/providers/Microsoft.KeyVault/vaults/keyVaultName
```

Perbarui enkripsi pekerjaan kotak data dari microsoft yang dikelola ke pelanggan yang dikelola pelanggan dengan identitas yang ditetapkan sytem.
Untuk kegagalan apa pun, jalankan kembali dengan $DebugPreference = "Lanjutkan" seperti yang disebutkan dalam contoh 1

### Contoh 3: Memperbarui pekerjaan kotak data dari sistem yang ditetapkan untuk pengguna yang ditetapkan dengan enkripsi kunci yang dikelola pelanggan
```powershell
$keyEncryptionDetails = New-AzDataBoxKeyEncryptionKeyObject -KekType "CustomerManaged" -IdentityProperty @{Type = "UserAssigned"; UserAssignedResourceId = "/subscriptions/SubscriptionId/resourceGroups/resourceGroupName/providers/Microsoft.ManagedIdentity/userAssignedIdentities/identityName"} -KekUrl "keyIdentifier" -KekVaultResourceId "/subscriptions/SubscriptionId/resourceGroups/resourceGroupName/providers/Microsoft.KeyVault/vaults/keyVaultName"
$updateSystemToUserAssigned = Update-AzDataBoxJob -Name "pwshTestSAssigned" -ResourceGroupName "resourceGroupName" -KeyEncryptionKey $keyEncryptionDetails -ContactDetail $contactDetail -ShippingAddress $ShippingDetails  -IdentityType "SystemAssigned,UserAssigned" -UserAssignedIdentity @{"/subscriptions/SubscriptionId/resourceGroups/resourceGroupName/providers/Microsoft.ManagedIdentity/userAssignedIdentities/identityName" = @{}}
```

Perbarui pekerjaan kotak data dari sistem yang ditetapkan untuk pengguna yang ditetapkan dengan enkripsi kunci yang dikelola pelanggan.
Untuk kegagalan apa pun, jalankan kembali dengan $DebugPreference = "Lanjutkan" seperti yang disebutkan dalam contoh 1

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

### -ContactDetail
Detail kontak untuk pemberitahuan dan pengiriman.
Untuk membuat, lihat bagian CATATAN untuk properti CONTACTDETAIL dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DataBox.Models.Api20210301.IContactDetails
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

### -IdentityType
Jenis identitas

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

### -IfMatch
Menentukan kondisi If-Match.
Patch akan dilakukan hanya jika ETag pekerjaan di server cocok dengan nilai ini.

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

### -KeyEncryptionKey
Kunci enkripsi kunci untuk pekerjaan tersebut.
Untuk membuat, lihat bagian CATATAN untuk properti KEYENCRYPTIONKEY dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DataBox.Models.Api20210301.IKeyEncryptionKey
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Nama sumber daya pekerjaan dalam grup sumber daya yang ditentukan.
panjang nama pekerjaan harus antara 3 dan 24 karakter dan hanya menggunakan alfanumerik dan garis bawah

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: JobName

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

### -ResourceGroupName
Nama Grup Sumber Daya

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

### -ShippingAddress
Alamat pengiriman pelanggan.
Untuk membuat, lihat bagian CATATAN untuk properti SHIPPINGADDRESS dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DataBox.Models.Api20210301.IShippingAddress
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
Id Langganan

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
Daftar pasangan nilai kunci yang menjelaskan sumber daya.
Tag ini dapat digunakan dalam melihat dan mengelompokkan sumber daya ini (di seluruh grup sumber daya).

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

### -UserAssignedIdentity
Identitas yang Ditetapkan Pengguna

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

### Microsoft.Azure.PowerShell.Cmdlets.DataBox.Models.Api20210301.IJobResource

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


CONTACTDETAIL `<IContactDetails>`: Detail kontak untuk pemberitahuan dan pengiriman.
  - `ContactName <String>`: Nama kontak orang tersebut.
  - `EmailList <String[]>`: Daftar Email-id yang akan diberi tahu tentang kemajuan pekerjaan.
  - `Phone <String>`: Telepon nomor kontak.
  - `[Mobile <String>]`: Nomor ponsel kontak.
  - `[NotificationPreference <INotificationPreference[]>]`: Preferensi pemberitahuan untuk tahap pekerjaan.
    - `SendNotification <Boolean>`: Pemberitahuan diperlukan atau tidak.
    - `StageName <NotificationStageName>`: Nama panggung.
  - `[PhoneExtension <String>]`: Telepon nomor ekstensi kontak.

KEYENCRYPTIONKEY `<IKeyEncryptionKey>`: Kunci enkripsi kunci untuk pekerjaan tersebut.
  - `KekType <KekType>`: Jenis kunci enkripsi yang digunakan untuk enkripsi kunci.
  - `[IdentityProperty <IIdentityProperties>]`: Properti identitas terkelola yang digunakan untuk enkripsi kunci.
    - `[Type <String>]`: Jenis identitas layanan terkelola.
    - `[UserAssignedResourceId <String>]`: Id sumber daya arm untuk identitas yang ditetapkan pengguna yang akan digunakan untuk mengambil token MSI.
  - `[KekUrl <String>]`: Kunci enkripsi kunci. Hal ini diperlukan dalam kasus KekType yang dikelola pelanggan.
  - `[KekVaultResourceId <String>]`: Id sumber daya kek vault. Hal ini diperlukan dalam kasus KekType yang dikelola pelanggan.

SHIPPINGADDRESS `<IShippingAddress>`: Alamat pengiriman pelanggan.
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

## RELATED LINKS

