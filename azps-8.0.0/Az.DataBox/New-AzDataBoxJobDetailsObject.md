---
external help file: ''
Module Name: Az.DataBox
online version: https://docs.microsoft.com/powershell/module/az.DataBox/new-AzDataBoxJobDetailsObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataBox/help/New-AzDataBoxJobDetailsObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataBox/help/New-AzDataBoxJobDetailsObject.md
ms.openlocfilehash: cc44bfaa1430f2e03d11f8d80d19722c5427c195
ms.sourcegitcommit: 5df8b100721844736630242c724da453a2168434
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/26/2022
ms.locfileid: "146611156"
---
# New-AzDataBoxJobDetailsObject

## SYNOPSIS
Buat objek dalam memori untuk DataBoxJobDetails.

## SYNTAX

```
New-AzDataBoxJobDetailsObject -ContactDetail <IContactDetails> -Type <ClassDiscriminator>
 [-DataExportDetail <IDataExportDetails[]>] [-DataImportDetail <IDataImportDetails[]>]
 [-DevicePassword <String>] [-ExpectedDataSizeInTeraByte <Int32>] [-KeyEncryptionKey <IKeyEncryptionKey>]
 [-Preference <IPreferences>] [-ShippingAddress <IShippingAddress>] [<CommonParameters>]
```

## DESCRIPTION
Buat objek dalam memori untuk DataBoxJobDetails.

## EXAMPLES

### Contoh 1: Membuat detail pekerjaan kotak data dalam objek memori 
```powershell
$contactDetail = New-AzDataBoxContactDetailsObject -ContactName "random" -EmailList @("emailId") -Phone "1234567891"
$ShippingDetails = New-AzDataBoxShippingAddressObject -StreetAddress1 "101 TOWNSEND ST" -StateOrProvince "CA" -Country "US" -City "San Francisco" -PostalCode "94107" -AddressType "Commercial"

New-AzDataBoxJobDetailsObject -Type "DataBox"  -DataImportDetail  @(@{AccountDetail=$dataAccount; AccountDetailDataAccountType = "StorageAccount"} ) -ContactDetail $contactDetail -ShippingAddress $ShippingDetails
```

```output
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
```

Membuat objek dalam memori untuk DataBoxJobDetails

## PARAMETERS

### -ContactDetail
Detail kontak untuk pemberitahuan dan pengiriman.
Untuk membuat, lihat bagian CATATAN untuk properti CONTACTDETAIL dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DataBox.Models.Api20210301.IContactDetails
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DataExportDetail
Detail data yang akan diekspor dari azure.
Untuk membuat, lihat bagian CATATAN untuk properti DATAEXPORTDETAIL dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DataBox.Models.Api20210301.IDataExportDetails[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DataImportDetail
Detail data yang akan diimpor ke azure.
Untuk membuat, lihat bagian CATATAN untuk properti DATAIMPORTDETAIL dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DataBox.Models.Api20210301.IDataImportDetails[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DevicePassword
Atur Kata sandi perangkat untuk membuka kunci Databox.
Tidak boleh diteruskan untuk pekerjaan TransferType:ExportFromAzure.
Jika ini tidak diteruskan, layanan akan menghasilkan kata sandi itu sendiri.
Ini tidak akan dikembalikan di Dapatkan Panggilan.
Persyaratan Kata Sandi : Kata sandi harus minimal 12 dan maksimum 64 karakter.
Kata sandi harus memiliki setidaknya satu alfabet huruf besar, satu angka dan satu karakter khusus.
Kata sandi tidak boleh memiliki karakter berikut: Kata Sandi IilLoO0 hanya boleh memiliki alfabet, angka, dan karakter ini : @#\-$%^!+=;:_()]+.

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

### -ExpectedDataSizeInTeraByte
Ukuran data yang diharapkan, yang perlu ditransfer dalam pekerjaan ini, dalam terabyte.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyEncryptionKey
Detail tentang jenis enkripsi kunci mana yang sedang digunakan.
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

### -Preferensi
Preferensi untuk pesanan.
Untuk membuat, lihat bagian CATATAN untuk properti PREFERENSI dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DataBox.Models.Api20210301.IPreferences
Parameter Sets: (All)
Aliases:

Required: False
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

### -Type
Menunjukkan jenis detail pekerjaan.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DataBox.Support.ClassDiscriminator
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

### Microsoft.Azure.PowerShell.Cmdlets.DataBox.Models.Api20210301.DataBoxJobDetails

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

DATAEXPORTDETAIL <IDataExportDetails[]>: Detail data yang akan diekspor dari azure.
  - `AccountDetailDataAccountType <DataAccountType>`: Jenis akun data yang akan ditransfer.
  - `TransferConfiguration <ITransferConfiguration>`: Konfigurasi untuk transfer data.
    - `Type <TransferConfigurationType>`: Jenis konfigurasi untuk transfer.
    - `[TransferAllDetail <ITransferConfigurationTransferAllDetails>]`: Peta jenis filter dan detail untuk mentransfer semua data. Bidang ini diperlukan hanya jika TransferConfigurationType diberikan sebagai TransferAll
      - `[IncludeDataAccountType <DataAccountType?>]`: Jenis akun data
      - `[IncludeTransferAllBlob <Boolean?>]`: Untuk menunjukkan apakah semua blob Azure harus ditransfer
      - `[IncludeTransferAllFile <Boolean?>]`: Untuk menunjukkan apakah semua Azure Files harus ditransfer
    - `[TransferFilterDetail <ITransferConfigurationTransferFilterDetails>]`: Peta jenis filter dan detail untuk difilter. Bidang ini diperlukan hanya jika TransferConfigurationType diberikan sebagai TransferUsingFilter.
      - `[AzureFileFilterDetailFilePathList <String[]>]`: Daftar jalur lengkap file yang akan ditransfer.
      - `[AzureFileFilterDetailFilePrefixList <String[]>]`: Daftar awalan file Azure yang akan ditransfer.
      - `[AzureFileFilterDetailFileShareList <String[]>]`: Daftar berbagi file yang akan ditransfer.
      - `[BlobFilterDetailBlobPathList <String[]>]`: Daftar jalur lengkap blob yang akan ditransfer.
      - `[BlobFilterDetailBlobPrefixList <String[]>]`: Daftar awalan blob Azure yang akan ditransfer.
      - `[BlobFilterDetailContainerList <String[]>]`: Daftar kontainer blob yang akan ditransfer.
      - `[IncludeDataAccountType <DataAccountType?>]`: Jenis akun data.
      - `[IncludeFilterFileDetail <IFilterFileDetails[]>]`: Detail file filter yang akan digunakan untuk transfer data.
        - `FilterFilePath <String>`: Jalur file yang berisi detail semua item yang akan ditransfer.
        - `FilterFileType <FilterFileType>`: Jenis file filter.
  - `[AccountDetailSharePassword <String>]`: Kata sandi untuk semua berbagi yang akan dibuat pada perangkat. Tidak boleh diteruskan untuk pekerjaan TransferType:ExportFromAzure. Jika ini tidak diteruskan, layanan akan menghasilkan kata sandi itu sendiri. Ini tidak akan dikembalikan di Dapatkan Panggilan. Persyaratan Kata Sandi : Kata sandi harus minimal 12 dan maksimum 64 karakter. Kata sandi harus memiliki setidaknya satu alfabet huruf besar, satu angka dan satu karakter khusus. Kata sandi tidak boleh memiliki karakter berikut: Kata Sandi IilLoO0 hanya boleh memiliki alfabet, angka dan karakter ini : @#\-$%^!+=;:_()]+
  - `[LogCollectionLevel <LogCollectionLevel?>]`: Tingkat log yang akan dikumpulkan.

DATAIMPORTDETAIL <IDataImportDetails[]>: Detail data yang akan diimpor ke azure.
  - `AccountDetailDataAccountType <DataAccountType>`: Jenis akun data yang akan ditransfer.
  - `[AccountDetailSharePassword <String>]`: Kata sandi untuk semua berbagi yang akan dibuat pada perangkat. Tidak boleh diteruskan untuk pekerjaan TransferType:ExportFromAzure. Jika ini tidak diteruskan, layanan akan menghasilkan kata sandi itu sendiri. Ini tidak akan dikembalikan di Dapatkan Panggilan. Persyaratan Kata Sandi : Kata sandi harus minimal 12 dan maksimum 64 karakter. Kata sandi harus memiliki setidaknya satu alfabet huruf besar, satu angka dan satu karakter khusus. Kata sandi tidak boleh memiliki karakter berikut: Kata Sandi IilLoO0 hanya boleh memiliki alfabet, angka dan karakter ini : @#\-$%^!+=;:_()]+

KEYENCRYPTIONKEY `<IKeyEncryptionKey>`: Detail tentang jenis enkripsi kunci mana yang sedang digunakan.
  - `KekType <KekType>`: Jenis kunci enkripsi yang digunakan untuk enkripsi kunci.
  - `[IdentityProperty <IIdentityProperties>]`: Properti identitas terkelola yang digunakan untuk enkripsi kunci.
    - `[Type <String>]`: Jenis identitas layanan terkelola.
    - `[UserAssignedResourceId <String>]`: Id sumber daya arm untuk identitas yang ditetapkan pengguna yang akan digunakan untuk mengambil token MSI.
  - `[KekUrl <String>]`: Kunci enkripsi kunci. Hal ini diperlukan dalam kasus KekType yang dikelola pelanggan.
  - `[KekVaultResourceId <String>]`: Id sumber daya kek vault. Hal ini diperlukan dalam kasus KekType yang dikelola pelanggan.

PREFERENSI `<IPreferences>`: Preferensi untuk pesanan.
  - `[EncryptionPreferenceDoubleEncryption <DoubleEncryption?>]`: Menentukan lapisan sekunder pengaktifan enkripsi berbasis perangkat lunak.
  - `[PreferredDataCenterRegion <String[]>]`: Wilayah pusat data pilihan.
  - `[TransportPreferencePreferredShipmentType <TransportShipmentTypes?>]`: Menunjukkan jenis Logistik Pengiriman yang disukai pelanggan.

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

