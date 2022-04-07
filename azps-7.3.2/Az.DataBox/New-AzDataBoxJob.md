---
external help file: ''
Module Name: Az.DataBox
online version: https://docs.microsoft.com/powershell/module/az.databox/new-azdataboxjob
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataBox/help/New-AzDataBoxJob.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataBox/help/New-AzDataBoxJob.md
ms.openlocfilehash: 0b7b09b65a1178d91bcbab75a4f08903182a6415
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140394882"
---
# New-AzDataBoxJob

## SYNOPSIS
Membuat pekerjaan baru dengan parameter tertentu.
Pekerjaan yang sudah ada tidak bisa diperbarui dengan API ini dan sebaiknya diperbarui dengan API pekerjaan Perbarui.

## SYNTAX

```
New-AzDataBoxJob -Name <String> -ResourceGroupName <String> -Location <String> -SkuName <SkuName>
 -TransferType <TransferType> [-SubscriptionId <String>] [-DeliveryInfoScheduledDateTime <DateTime>]
 [-DeliveryType <JobDeliveryType>] [-Detail <IJobDetails>] [-IdentityType <String>] [-SkuDisplayName <String>]
 [-SkuFamily <String>] [-Tag <Hashtable>] [-UserAssignedIdentity <Hashtable>] [-DefaultProfile <PSObject>]
 [-AsJob] [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Membuat pekerjaan baru dengan parameter tertentu.
Pekerjaan yang sudah ada tidak bisa diperbarui dengan API ini dan sebaiknya diperbarui dengan API pekerjaan Perbarui.

## EXAMPLES

### Contoh 1: Membuat pekerjaan impor kotak data 
```powershell
$dataAccount = New-AzDataBoxStorageAccountDetailsObject -DataAccountType "StorageAccount" -StorageAccountId "/subscriptions/SubscriptionId/resourceGroups/resourceGroupName/providers/Microsoft.Storage/storageAccounts/storageAccountName"
$contactDetail = New-AzDataBoxContactDetailsObject -ContactName "random" -EmailList @("emailId") -Phone "1234567891"
$ShippingDetails = New-AzDataBoxShippingAddressObject -StreetAddress1 "101 TOWNSEND ST" -StateOrProvince "CA" -Country "US" -City "San Francisco" -PostalCode "94107" -AddressType "Commercial"
$details = New-AzDataBoxJobDetailsObject -Type "DataBox"  -DataImportDetail  @(@{AccountDetail=$dataAccount; AccountDetailDataAccountType = "StorageAccount"} ) -ContactDetail $contactDetail -ShippingAddress $ShippingDetails
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
$resource = New-AzDataBoxJob -Name "ImportTest" -SubscriptionId "SubscriptionId" -ResourceGroupName "resourceGroupName" -TransferType "ImportToAzure" -Detail $details -Location "WestUS" -SkuName "DataBox"
$resource

Name         Location Status        TransferType  SkuName IdentityType DeliveryType Detail
----         -------- ------        ------------  ------- ------------ ------------ ------
ImportTest WestUS   DeviceOrdered ImportToAzure DataBox None         NonScheduled Microsoft.Azure.PowerShell.Cmdlets.DataBox.Models.Api20210301.DataBoxJobDetails

$resource.Detail

Action                     :
ChainOfCustodySasKey       :
ContactDetail              : Microsoft.Azure.PowerShell.Cmdlets.DataBox.Models.Api20210301.ContactDetails
CopyLogDetail              :
CopyProgress               :
DataExportDetail           :
DataImportDetail           : {Microsoft.Azure.PowerShell.Cmdlets.DataBox.Models.Api20210301.DataImportDetails}
DeliveryPackage            : Microsoft.Azure.PowerShell.Cmdlets.DataBox.Models.Api20210301.PackageShippingDetails
DevicePassword             :
ExpectedDataSizeInTeraByte : 0
JobStage                   :
KeyEncryptionKey           : Microsoft.Azure.PowerShell.Cmdlets.DataBox.Models.Api20210301.KeyEncryptionKey
LastMitigationActionOnJob  : Microsoft.Azure.PowerShell.Cmdlets.DataBox.Models.Api20210301.LastMitigationActionOnJob
Preference                 : Microsoft.Azure.PowerShell.Cmdlets.DataBox.Models.Api20210301.Preferences
ReturnPackage              : Microsoft.Azure.PowerShell.Cmdlets.DataBox.Models.Api20210301.PackageShippingDetails
ReverseShipmentLabelSasKey :
ShippingAddress            : Microsoft.Azure.PowerShell.Cmdlets.DataBox.Models.Api20210301.ShippingAddress
Type                       : DataBox

$resource.Detail.ShippingAddress

AddressType City          CompanyName Country PostalCode StateOrProvince StreetAddress1  StreetAddress2 StreetAddress3 ZipExtendedCode
----------- ----          ----------- ------- ---------- --------------- --------------  -------------- -------------- ---------------
Commercial  San Francisco             US      94107      CA              101 TOWNSEND ST
```

Anda dapat memperluas dan memvisualisasikan objek lainnya dengan cara yang sama seperti bagaimana detail dan alamat pengiriman diperluas.

### Contoh 2: Membuat pekerjaan ekspor kotak data
```powershell
$dataAccount = New-AzDataBoxStorageAccountDetailsObject -DataAccountType "StorageAccount" -StorageAccountId "/subscriptions/SubscriptionId/resourceGroups/resourceGroupName/providers/Microsoft.Storage/storageAccounts/storageAccountName"
$contactDetail = New-AzDataBoxContactDetailsObject -ContactName "random" -EmailList @("emailId") -Phone "1234567891"
$ShippingDetails = New-AzDataBoxShippingAddressObject -StreetAddress1 "101 TOWNSEND ST" -StateOrProvince "CA" -Country "US" -City "San Francisco" -PostalCode "94107" -AddressType "Commercial"
$transferConfigurationType = New-AzDataBoxTransferConfigurationObject -Type "TransferAll" -TransferAllDetail @{"IncludeDataAccountType"="StorageAccount";"IncludeTransferAllBlob"= "True"; "IncludeTransferAllFile"="True"}
$details = New-AzDataBoxJobDetailsObject -Type "DataBox" -DataExportDetail  @(@{AccountDetail=$dataAccount; AccountDetailDataAccountType = "StorageAccount"; "TransferConfiguration"= $transferConfigurationType} ) -ContactDetail $contactDetail -ShippingAddress $ShippingDetails
$resource = New-AzDataBoxJob -Name "ExportTest" -SubscriptionId "SubscriptionId" -ResourceGroupName "resourceGroupName" -TransferType "ExportFromAzure" -Detail $details -Location "WestUS" -SkuName "DataBox"
```

```output
Name      Location Status        TransferType    SkuName IdentityType DeliveryType Detail
----      -------- ------        ------------    ------- ------------ ------------ ------
ExportTest WestUS   DeviceOrdered ExportFromAzure DataBox None         NonScheduled Microsoft.Azure.PowerShell.Cmdlets.DataBox.Models.Api20210301.DataBoxJobDetails
```

Membuat pekerjaan ekspor kotak data.
Untuk kegagalan yang dijalankan kembali dengan $DebugPreference = "Lanjutkan" seperti yang disebutkan dalam contoh 1

### Contoh 3: Membuat pekerjaan impor kotak data dengan akun disk terkelola
```powershell
$managedDiskAccount=New-AzDataBoxManagedDiskDetailsObject -ResourceGroupId "/subscriptions/SubscriptionId/resourceGroups/resourceGroupName" -StagingStorageAccountId "/subscriptions/SubscriptionId/resourceGroups/resourceGroupName/providers/Microsoft.Storage/storageAccounts/stagingAccountName" -DataAccountType "ManagedDisk"
$contactDetail = New-AzDataBoxContactDetailsObject -ContactName "random" -EmailList @("emailId") -Phone "1234567891"
$ShippingDetails = New-AzDataBoxShippingAddressObject -StreetAddress1 "101 TOWNSEND ST" -StateOrProvince "CA" -Country "US" -City "San Francisco" -PostalCode "94107" -AddressType "Commercial"
$details = New-AzDataBoxJobDetailsObject -Type "DataBox"  -DataImportDetail  @(@{AccountDetail=$managedDiskAccount; AccountDetailDataAccountType = "ManagedDisk"} ) -ContactDetail $contactDetail -ShippingAddress $ShippingDetails
New-AzDataBoxJob -Name "PwshManagedDisk" -SubscriptionId "SubscriptionId" -ResourceGroupName "resourceGroupName" -TransferType "ImportToAzure" -Detail $details -Location "WestUS" -SkuName "DataBox"
```

```output
Name            Location Status        TransferType  SkuName IdentityType DeliveryType Detail
----            -------- ------        ------------  ------- ------------ ------------ ------
PwshManagedDisk WestUS   DeviceOrdered ImportToAzure DataBox None         NonScheduled Microsoft.Azure.PowerShell.Cmdlets.DataBox.Models.Api20210301.DataBoxJobDetails
```

Membuat pekerjaan impor kotak data dengan akun disk terkelola.
Untuk kegagalan yang dijalankan kembali dengan $DebugPreference = "Lanjutkan" seperti yang disebutkan dalam contoh 1

### Contoh 4: Membuat pekerjaan impor kotak data dengan identitas yang ditetapkan pengguna
```powershell
$dataAccount = New-AzDataBoxStorageAccountDetailsObject -DataAccountType "StorageAccount" -StorageAccountId "/subscriptions/SubscriptionId/resourceGroups/resourceGroupName/providers/Microsoft.Storage/storageAccounts/storageAccountName"
$contactDetail = New-AzDataBoxContactDetailsObject -ContactName "random" -EmailList @("emailId") -Phone "1234567891"
$ShippingDetails = New-AzDataBoxShippingAddressObject -StreetAddress1 "101 TOWNSEND ST" -StateOrProvince "CA" -Country "US" -City "San Francisco" -PostalCode "94107" -AddressType "Commercial"
$keyEncryptionDetails = New-AzDataBoxKeyEncryptionKeyObject -KekType "CustomerManaged" -IdentityProperty @{Type = "UserAssigned"; UserAssignedResourceId = "/subscriptions/SubscriptionId/resourceGroups/resourceGroupName/providers/Microsoft.ManagedIdentity/userAssignedIdentities/identityName"} -KekUrl "keyIdentifier" -KekVaultResourceId "/subscriptions/SubscriptionId/resourceGroups/resourceGroupName/providers/Microsoft.KeyVault/vaults/keyVaultName"
$details = New-AzDataBoxJobDetailsObject -Type "DataBox"  -DataImportDetail  @(@{AccountDetail=$dataAccount; AccountDetailDataAccountType = "StorageAccount"} ) -ContactDetail $contactDetail -ShippingAddress $ShippingDetails -KeyEncryptionKey $keyEncryptionDetails
New-AzDataBoxJob -Name "PowershellMSI" -SubscriptionId "SubscriptionId" -ResourceGroupName "resourceGroupName" -TransferType "ImportToAzure" -Detail $details -Location "WestUS" -SkuName "DataBox"  -IdentityType "UserAssigned" -UserAssignedIdentity @{"/subscriptions/SubscriptionId/resourceGroups/resourceGroupName/providers/Microsoft.ManagedIdentity/userAssignedIdentities/identityName" = @{}}
```

```output
Name          Location Status        TransferType  SkuName IdentityType DeliveryType Detail
----          -------- ------        ------------  ------- ------------ ------------ ------
PowershellMSI WestUS   DeviceOrdered ImportToAzure DataBox UserAssigned NonScheduled Microsoft.Azure.PowerShell.Cmdlets.DataBox.Models.Api20210301.DataBoxJobDetails
```

Membuat pekerjaan impor kotak data dengan identitas yang ditetapkan pengguna.
Untuk kegagalan yang dijalankan kembali dengan $DebugPreference = "Lanjutkan" seperti yang disebutkan dalam contoh 1

### Contoh 5: Membuat pekerjaan kotak data dengan kunci Anda sendiri
```powershell
$dataAccount = New-AzDataBoxStorageAccountDetailsObject -DataAccountType "StorageAccount" -StorageAccountId "/subscriptions/SubscriptionId/resourceGroups/resourceGroupName/providers/Microsoft.Storage/storageAccounts/storageAccountName"
$contactDetail = New-AzDataBoxContactDetailsObject -ContactName "random" -EmailList @("emailId") -Phone "1234567891"
$ShippingDetails = New-AzDataBoxShippingAddressObject -StreetAddress1 "101 TOWNSEND ST" -StateOrProvince "CA" -Country "US" -City "San Francisco" -PostalCode "94107" -AddressType "Commercial"
$details = New-AzDataBoxJobDetailsObject -Type "DataBox"  -DataImportDetail  @(@{AccountDetail=$dataAccount; AccountDetailDataAccountType = "StorageAccount"} ) -ContactDetail $contactDetail -ShippingAddress $ShippingDetails -DevicePassword "randmPass@12345"
$resource = New-AzDataBoxJob -Name "PowershellBYOK" -SubscriptionId "SubscriptionId" -ResourceGroupName "resourceGroupName" -TransferType "ImportToAzure" -Detail $details -Location "WestUS" -SkuName "DataBox"
```

```output
Name           Location Status        TransferType  SkuName IdentityType DeliveryType Detail
----           -------- ------        ------------  ------- ------------ ------------ ------
PowershellBYOK WestUS   DeviceOrdered ImportToAzure DataBox None         NonScheduled Microsoft.Azure.PowerShell.Cmdlets.DataBox.Models.Api20210301.DataBoxJobDetails
```

Membuat pekerjaan kotak data dengan kunci Anda sendiri.
Untuk kegagalan yang dijalankan kembali dengan $DebugPreference = "Lanjutkan" seperti yang disebutkan dalam contoh 1

### Contoh 6: Membuat kotak dataHeavy pekerjaan dengan kunci Anda sendiri
```powershell
$dataAccount = New-AzDataBoxStorageAccountDetailsObject -DataAccountType "StorageAccount" -StorageAccountId "/subscriptions/SubscriptionId/resourceGroups/resourceGroupName/providers/Microsoft.Storage/storageAccounts/storageAccountName"
$contactDetail = New-AzDataBoxContactDetailsObject -ContactName "random" -EmailList @("emailId") -Phone "1234567891"
$ShippingDetails = New-AzDataBoxShippingAddressObject -StreetAddress1 "101 TOWNSEND ST" -StateOrProvince "CA" -Country "US" -City "San Francisco" -PostalCode "94107" -AddressType "Commercial"
$details = New-AzDataBoxHeavyJobDetailsObject -Type "DataBoxHeavy"  -DataImportDetail  @(@{AccountDetail=$dataAccount; AccountDetailDataAccountType = "StorageAccount"} ) -ContactDetail $contactDetail -ShippingAddress $ShippingDetails -DevicePassword "randm@423jarABC" -ExpectedDataSizeInTeraByte 10
$resource = New-AzDataBoxJob -Name "DbxHeavy" -SubscriptionId "SubscriptionId" -ResourceGroupName "resourceGroupName" -TransferType "ImportToAzure" -Detail $details -Location "WestUS" -SkuName "DataBoxHeavy"
```

```output
Name    Location Status        TransferType  SkuName      IdentityType DeliveryType Detail
----    -------- ------        ------------  -------      ------------ ------------ ------
DbxHeavy WestUS  DeviceOrdered ImportToAzure DataBoxHeavy  None        NonScheduled Microsoft.Azure.PowerShell.Cmdlets.DataBox.Models.Api20210301.DataBoxHeavyJobDetails
```

Membuat kotak dataHeavy pekerjaan dengan kunci Anda sendiri.
Untuk kegagalan yang dijalankan kembali dengan $DebugPreference = "Lanjutkan" seperti yang disebutkan dalam contoh 1

### Contoh 7: Membuat kotak data Jobdisk dengan Passkey Anda sendiri
```powershell
$dataAccount = New-AzDataBoxStorageAccountDetailsObject -DataAccountType "StorageAccount" -StorageAccountId "/subscriptions/SubscriptionId/resourceGroups/resourceGroupName/providers/Microsoft.Storage/storageAccounts/storageAccountName"
$contactDetail = New-AzDataBoxContactDetailsObject -ContactName "random" -EmailList @("emailId") -Phone "1234567891"
$ShippingDetails = New-AzDataBoxShippingAddressObject -StreetAddress1 "101 TOWNSEND ST" -StateOrProvince "CA" -Country "US" -City "San Francisco" -PostalCode "94107" -AddressType "Commercial"
$details = New-AzDataBoxDiskJobDetailsObject -Type "DataBoxDisk"  -DataImportDetail  @(@{AccountDetail=$dataAccount; AccountDetailDataAccountType = "StorageAccount"} ) -ContactDetail $contactDetail -ShippingAddress $ShippingDetails -Passkey "randm@423jarABC" -PreferredDisk @{"8" = 8; "4" = 2} -ExpectedDataSizeInTeraByte 18
New-AzDataBoxJob -Name "pwshDisk" -SubscriptionId "SubscriptionId" -ResourceGroupName "resourceGroupName" -TransferType "ImportToAzure" -Detail $details -Location "WestUS" -SkuName "DataBoxDisk"
```

```output
Name     Location Status        TransferType  SkuName     IdentityType DeliveryType Detail
----     -------- ------        ------------  -------     ------------ ------------ ------
pwshDisk WestUS   DeviceOrdered ImportToAzure DataBoxDisk None         NonScheduled Microsoft.Azure.PowerShell.Cmdlets.DataBox.Models.Api20210301.DataBoxDiskJobDetails
```

Membuat pekerjaan kotak dataDisky dengan tombol Passkey Anda sendiri.
Untuk kegagalan yang dijalankan kembali dengan $DebugPreference = "Lanjutkan" seperti yang disebutkan dalam contoh 1

### Contoh 8: Membuat pekerjaan kotak data dengan enkripsi ganda diaktifkan
```powershell
$dataAccount = New-AzDataBoxStorageAccountDetailsObject -DataAccountType "StorageAccount" -StorageAccountId "/subscriptions/SubscriptionId/resourceGroups/resourceGroupName/providers/Microsoft.Storage/storageAccounts/storageAccountName"
$contactDetail = New-AzDataBoxContactDetailsObject -ContactName "random" -EmailList @("emailId") -Phone "1234567891"
$ShippingDetails = New-AzDataBoxShippingAddressObject -StreetAddress1 "101 TOWNSEND ST" -StateOrProvince "CA" -Country "US" -City "San Francisco" -PostalCode "94107" -AddressType "Commercial"
$details = New-AzDataBoxJobDetailsObject -Type "DataBox"  -DataImportDetail  @(@{AccountDetail=$dataAccount; AccountDetailDataAccountType = "StorageAccount"} ) -ContactDetail $contactDetail -ShippingAddress $ShippingDetails -Preference @{EncryptionPreferenceDoubleEncryption="Enabled"}
New-AzDataBoxJob -Name "pwshDoubEncy" -SubscriptionId "SubscriptionId" -ResourceGroupName "resourceGroupName" -TransferType "ImportToAzure" -Detail $details -Location "WestUS" -SkuName "DataBox"
```

```output
Name        Location Status        TransferType  SkuName     IdentityType DeliveryType Detail
----        -------- ------        ------------  -------     ------------ ------------ ------
pwshDoubEncy WestUS   DeviceOrdered ImportToAzure DataBox None         NonScheduled Microsoft.Azure.PowerShell.Cmdlets.DataBox.Models.Api20210301.DataBoxDiskJobDetails
```

Membuat pekerjaan kotak data dengan enkripsi ganda diaktifkan.
Untuk kegagalan yang dijalankan kembali dengan $DebugPreference = "Lanjutkan" seperti yang disebutkan dalam contoh 1

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

### -DeliveryInfoScheduledDateTime
Tanggal waktu terjadwal.

```yaml
Type: System.DateTime
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DeliveryType
Tipe pengiriman Pekerjaan.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DataBox.Support.JobDeliveryType
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Detail
Detail pekerjaan yang dijalankan.
Bidang ini hanya akan dikirim untuk filter perluas detail.
Untuk membuat, lihat bagian CATATAN untuk properti DETAIL dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DataBox.Models.Api20210301.IJobDetails
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IdentityType
Tipe identitas

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

### -Lokasi
Lokasi sumber daya.
Ini akan menjadi salah satu Kawasan Azure yang didukung dan terdaftar (misalnya AS Barat, AS Timur, Asia Tenggara, dll.).
Wilayah sumber daya tidak dapat diubah setelah dibuat, tetapi jika kawasan yang sama ditentukan pada pembaruan permintaan akan berhasil.

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

### -Nama
Nama Sumber Daya pekerjaan di dalam grup sumber daya yang ditentukan.
nama kerja harus panjang antara 3 dan 24 karakter dan gunakan alfanumerik dan garis bawah saja

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

### -SkuDisplayName
Nama tampilan sku.

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

### -SkuFamily
Keluarga sku.

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

### -SkuName
Nama sku.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DataBox.Support.SkuName
Parameter Sets: (All)
Aliases:

Required: True
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

### -TransferType
Tipe transfer data.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DataBox.Support.TransferType
Parameter Sets: (All)
Aliases:

Required: True
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

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DataBox.Models.Api20210301.IJobResource

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


DETAIL <IJobDetails>: Detail pekerjaan yang dijalankan. Bidang ini hanya akan dikirim untuk filter perluas detail.
  - `ContactDetail <IContactDetails>`: Detail kontak untuk pemberitahuan dan pengiriman.
    - `ContactName <String>`: Nama kontak orang tersebut.
    - `EmailList <String[]>`: Daftar Id Email untuk diberi tahu tentang kemajuan pekerjaan.
    - `Phone <String>`: Telepon nomor kontak.
    - `[Mobile <String>]`: Nomor ponsel orang yang dapat dihubungi.
    - `[NotificationPreference <INotificationPreference[]>]`: Preferensi pemberitahuan untuk tahapan pekerjaan.
      - `SendNotification <Boolean>`: Pemberitahuan diperlukan atau tidak.
      - `StageName <NotificationStageName>`: Nama tahapan.
    - `[PhoneExtension <String>]`: Telepon nomor ekstensi orang kontak.
  - `Type <ClassDiscriminator>`: Menunjukkan tipe detail pekerjaan.
  - `[DataExportDetail <IDataExportDetails[]>]`: Detail data yang akan diekspor dari Azure.
    - `AccountDetailDataAccountType <DataAccountType>`: Tipe Akun data yang akan ditransfer.
    - `TransferConfiguration <ITransferConfiguration>`: Konfigurasi untuk transfer data.
      - `Type <TransferConfigurationType>`: Tipe konfigurasi untuk transfer.
      - `[TransferAllDetail <ITransferConfigurationTransferAllDetails>]`: Peta tipe filter dan detail untuk mentransfer semua data. Bidang ini hanya diperlukan jika TransferConfigurationType diberikan sebagai TransferAll
        - `[IncludeDataAccountType <DataAccountType?>]`: Tipe akun data
        - `[IncludeTransferAllBlob <Boolean?>]`: Untuk menunjukkan apakah semua blob Azure harus ditransfer
        - `[IncludeTransferAllFile <Boolean?>]`: Untuk menunjukkan apakah semua File Azure harus ditransfer
      - `[TransferFilterDetail <ITransferConfigurationTransferFilterDetails>]`: Peta tipe filter dan detail untuk memfilter. Bidang ini hanya diperlukan jika TransferConfigurationType diberikan sebagai TransferUsingFilter.
        - `[AzureFileFilterDetailFilePathList <String[]>]`: Daftar jalur lengkap file yang akan ditransfer.
        - `[AzureFileFilterDetailFilePrefixList <String[]>]`: Daftar prefiks file Azure yang akan ditransfer.
        - `[AzureFileFilterDetailFileShareList <String[]>]`: Daftar berbagi file yang akan ditransfer.
        - `[BlobFilterDetailBlobPathList <String[]>]`: Daftar jalur lengkap blob yang akan ditransfer.
        - `[BlobFilterDetailBlobPrefixList <String[]>]`: Daftar prefiks Azure blob yang akan ditransfer.
        - `[BlobFilterDetailContainerList <String[]>]`: Daftar wadah blob yang akan ditransfer.
        - `[IncludeDataAccountType <DataAccountType?>]`: Tipe akun data.
        - `[IncludeFilterFileDetail <IFilterFileDetails[]>]`: Detail file filter yang akan digunakan untuk transfer data.
          - `FilterFilePath <String>`: Jalur file yang berisi detail semua item yang akan ditransfer.
          - `FilterFileType <FilterFileType>`: Tipe file filter.
    - `[AccountDetailSharePassword <String>]`: Kata sandi untuk semua berbagi dibuat pada perangkat. Tidak dapat dialihkan untuk pekerjaan TransferType:ExportFromAzure. Jika ini tidak lolos, layanan akan membuat kata sandi itu sendiri. Ini tidak akan dikembalikan di Dapatkan Panggilan. Persyaratan Kata Sandi : Kata sandi harus minimal 12 dan maksimal 64 karakter. Kata sandi harus memiliki setidaknya satu alfabet huruf besar, satu nomor dan satu karakter khusus. Password tidak dapat memiliki karakter berikut: IilLoO0 Password hanya bisa memiliki alfabet, angka dan karakter ini : @#\-$%^!+=;:_()]+
    - `[LogCollectionLevel <LogCollectionLevel?>]`: Tingkat log yang akan dikumpulkan.
  - `[DataImportDetail <IDataImportDetails[]>]`: Detail data yang akan diimpor ke Azure.
    - `AccountDetailDataAccountType <DataAccountType>`: Tipe Akun data yang akan ditransfer.
    - `[AccountDetailSharePassword <String>]`: Kata sandi untuk semua berbagi dibuat pada perangkat. Tidak dapat dialihkan untuk pekerjaan TransferType:ExportFromAzure. Jika ini tidak lolos, layanan akan membuat kata sandi itu sendiri. Ini tidak akan dikembalikan di Dapatkan Panggilan. Persyaratan Kata Sandi : Kata sandi harus minimal 12 dan maksimal 64 karakter. Kata sandi harus memiliki setidaknya satu alfabet huruf besar, satu nomor dan satu karakter khusus. Password tidak dapat memiliki karakter berikut: IilLoO0 Password hanya bisa memiliki alfabet, angka dan karakter ini : @#\-$%^!+=;:_()]+
  - `[ExpectedDataSizeInTeraByte <Int32?>]`: Ukuran data yang diharapkan, yang perlu ditransfer dalam pekerjaan ini, dalam terabyte.
  - `[KeyEncryptionKey <IKeyEncryptionKey>]`: Detail tentang tipe enkripsi kunci yang digunakan.
    - `KekType <KekType>`: Tipe kunci enkripsi yang digunakan untuk enkripsi kunci.
    - `[IdentityProperty <IIdentityProperties>]`: Properti identitas terkelola digunakan untuk enkripsi kunci.
      - `[Type <String>]`: Tipe identitas layanan terkelola.
      - `[UserAssignedResourceId <String>]`: Id sumber daya arm untuk identitas yang ditetapkan pengguna untuk digunakan untuk mengambil token MSI.
    - `[KekUrl <String>]`: Kunci enkripsi kunci. It is required in case of Customer managed KekType.
    - `[KekVaultResourceId <String>]`: Id sumber daya penyimpanan kek. It is required in case of Customer managed KekType.
  - `[Preference <IPreferences>]`: Preferensi untuk pesanan.
    - `[EncryptionPreferenceDoubleEncryption <DoubleEncryption?>]`: Menentukan lapisan sekunder terkait enkripsi berbasis perangkat lunak.
    - `[PreferredDataCenterRegion <String[]>]`: Kawasan pusat data pilihan.
    - `[TransportPreferencePreferredShipmentType <TransportShipmentTypes?>]`: Menunjukkan tipe Logistik Pengiriman yang lebih disukai pelanggan.
  - `[ShippingAddress <IShippingAddress>]`: Alamat pengiriman pelanggan.
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

## RELATED LINKS

