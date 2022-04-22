---
external help file: ''
Module Name: Az.DataBox
online version: https://docs.microsoft.com/powershell/module/az.DataBox/new-AzDataBoxJobDetailsObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataBox/help/New-AzDataBoxJobDetailsObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataBox/help/New-AzDataBoxJobDetailsObject.md
ms.openlocfilehash: 6a8cb44854f83e5720f8b197dcc5d56e2bf2c22b
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142875466"
---
# New-AzDataBoxJobDetailsObject

## SYNOPSIS
Membuat objek dalam memori untuk DataBoxJobDetails.

## SYNTAX

```
New-AzDataBoxJobDetailsObject -ContactDetail <IContactDetails> -Type <ClassDiscriminator>
 [-DataExportDetail <IDataExportDetails[]>] [-DataImportDetail <IDataImportDetails[]>]
 [-DevicePassword <String>] [-ExpectedDataSizeInTeraByte <Int32>] [-KeyEncryptionKey <IKeyEncryptionKey>]
 [-Preference <IPreferences>] [-ShippingAddress <IShippingAddress>] [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk DataBoxJobDetails.

## EXAMPLES

### Contoh 1: Membuat detail pekerjaan kotak data dalam objek memori 
```powershell
$details = New-AzDataBoxJobDetailsObject -Type "DataBox"  -DataImportDetail  @(@{AccountDetail=$dataAccount; AccountDetailDataAccountType = "StorageAccount"} ) -ContactDetail $contactDetail -ShippingAddress $ShippingDetails
$details
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
Untuk membuat, lihat bagian CATATAN untuk properti CONTACTDETAIL dan membuat tabel hash.

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
Untuk membangun, lihat bagian CATATAN untuk properti DATAEXPORTDETAIL dan membuat tabel hash.

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
Untuk membangun, lihat bagian CATATAN untuk properti DATAIMPORTDETAIL dan membuat tabel hash.

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
Atur Kata sandi perangkat untuk membuka kunci Kotak Data.
Tidak boleh dilewati untuk pekerjaan TransferType:ExportFromAzure.
Jika tidak lolos, layanan akan menghasilkan kata sandi itu sendiri.
Ini tidak akan dikembalikan di Dapatkan Panggilan.
Persyaratan Kata Sandi : Kata sandi harus minimal 12 dan maksimal 64 karakter.
Kata sandi harus memiliki setidaknya satu alfabet huruf besar, satu angka dan satu karakter khusus.
Kata sandi tidak dapat memiliki karakter berikut: Kata sandi IilLoO0 hanya dapat memiliki alfabet, angka, dan karakter berikut : @#\-$%^!+=;:_()]+.

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
Detail tentang tipe enkripsi kunci mana yang sedang digunakan.
Untuk membuat, lihat bagian CATATAN untuk properti KEYENCRYPTIONKEY dan membuat tabel hash.

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
Preferensi untuk urutan.
Untuk membuat, lihat bagian CATATAN untuk properti PREFERENCE dan membuat tabel hash.

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
Untuk membangun, lihat bagian CATATAN untuk properti SHIPPINGADDRESS dan membuat tabel hash.

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

### -Tipe
Menunjukkan tipe detail pekerjaan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DataBox.Models.Api20210301.DataBoxJobDetails

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


CONTACTDETAIL <IContactDetails>: Detail kontak untuk pemberitahuan dan pengiriman.
  - `ContactName <String>`: Nama kontak orang tersebut.
  - `EmailList <String[]>`: Daftar Email-id yang akan diberi tahu tentang kemajuan pekerjaan.
  - `Phone <String>`: Telepon nomor kontak.
  - `[Mobile <String>]`: Nomor ponsel orang yang dihubungi.
  - `[NotificationPreference <INotificationPreference[]>]`: Preferensi pemberitahuan untuk tahap pekerjaan.
    - `SendNotification <Boolean>`: Pemberitahuan diperlukan atau tidak.
    - `StageName <NotificationStageName>`: Nama panggung.
  - `[PhoneExtension <String>]`: Telepon nomor ekstensi kontak.

DATAEXPORTDETAIL <IDataExportDetails[]>: Detail data yang akan diekspor dari azure.
  - `AccountDetailDataAccountType <DataAccountType>`: Tipe Akun data yang akan ditransfer.
  - `TransferConfiguration <ITransferConfiguration>`: Konfigurasi untuk transfer data.
    - `Type <TransferConfigurationType>`: Tipe konfigurasi untuk transfer.
    - `[TransferAllDetail <ITransferConfigurationTransferAllDetails>]`: Peta tipe filter dan detail untuk mentransfer semua data. Bidang ini diperlukan hanya jika TransferConfigurationType diberikan sebagai TransferAll
      - `[IncludeDataAccountType <DataAccountType?>]`: Tipe akun data
      - `[IncludeTransferAllBlob <Boolean?>]`: Untuk menunjukkan apakah semua blob Azure harus ditransfer
      - `[IncludeTransferAllFile <Boolean?>]`: Untuk menunjukkan apakah semua Azure Files harus ditransfer
    - `[TransferFilterDetail <ITransferConfigurationTransferFilterDetails>]`: Peta tipe filter dan detail untuk memfilter. Bidang ini diperlukan hanya jika TransferConfigurationType diberikan sebagai TransferUsingFilter.
      - `[AzureFileFilterDetailFilePathList <String[]>]`: Daftar jalur lengkap file yang akan ditransfer.
      - `[AzureFileFilterDetailFilePrefixList <String[]>]`: Daftar prefiks file Azure yang akan ditransfer.
      - `[AzureFileFilterDetailFileShareList <String[]>]`: Daftar pembagian file yang akan ditransfer.
      - `[BlobFilterDetailBlobPathList <String[]>]`: Daftar jalur lengkap dari blob yang akan ditransfer.
      - `[BlobFilterDetailBlobPrefixList <String[]>]`: Daftar prefiks blob Azure yang akan ditransfer.
      - `[BlobFilterDetailContainerList <String[]>]`: Daftar wadah blob yang akan ditransfer.
      - `[IncludeDataAccountType <DataAccountType?>]`: Tipe akun data.
      - `[IncludeFilterFileDetail <IFilterFileDetails[]>]`: Detail file filter yang akan digunakan untuk transfer data.
        - `FilterFilePath <String>`: Jalur file yang berisi detail semua item untuk ditransfer.
        - `FilterFileType <FilterFileType>`: Tipe file filter.
  - `[AccountDetailSharePassword <String>]`: Kata sandi untuk semua pembagian yang akan dibuat di perangkat. Tidak boleh dilewati untuk pekerjaan TransferType:ExportFromAzure. Jika tidak lolos, layanan akan menghasilkan kata sandi itu sendiri. Ini tidak akan dikembalikan di Dapatkan Panggilan. Persyaratan Kata Sandi : Kata sandi harus minimal 12 dan maksimal 64 karakter. Kata sandi harus memiliki setidaknya satu alfabet huruf besar, satu angka dan satu karakter khusus. Kata sandi tidak dapat memiliki karakter berikut: Kata Sandi IilLoO0 hanya dapat memiliki alfabet, angka, dan karakter berikut : @#\-$%^!+=;:_()]+
  - `[LogCollectionLevel <LogCollectionLevel?>]`: Tingkat log yang akan dikumpulkan.

DATAIMPORTDETAIL <IDataImportDetails[]>: Detail data yang akan diimpor ke azure.
  - `AccountDetailDataAccountType <DataAccountType>`: Tipe Akun data yang akan ditransfer.
  - `[AccountDetailSharePassword <String>]`: Kata sandi untuk semua pembagian yang akan dibuat di perangkat. Tidak boleh dilewati untuk pekerjaan TransferType:ExportFromAzure. Jika tidak lolos, layanan akan menghasilkan kata sandi itu sendiri. Ini tidak akan dikembalikan di Dapatkan Panggilan. Persyaratan Kata Sandi : Kata sandi harus minimal 12 dan maksimal 64 karakter. Kata sandi harus memiliki setidaknya satu alfabet huruf besar, satu angka dan satu karakter khusus. Kata sandi tidak dapat memiliki karakter berikut: Kata Sandi IilLoO0 hanya dapat memiliki alfabet, angka, dan karakter berikut : @#\-$%^!+=;:_()]+

KEYENCRYPTIONKEY <IKeyEncryptionKey>: Detail tentang tipe enkripsi kunci mana yang sedang digunakan.
  - `KekType <KekType>`: Tipe kunci enkripsi yang digunakan untuk enkripsi kunci.
  - `[IdentityProperty <IIdentityProperties>]`: Properti identitas terkelola yang digunakan untuk enkripsi kunci.
    - `[Type <String>]`: Jenis identitas layanan terkelola.
    - `[UserAssignedResourceId <String>]`: Id sumber daya arm untuk identitas yang ditetapkan pengguna yang akan digunakan untuk mengambil token MSI.
  - `[KekUrl <String>]`: Kunci enkripsi kunci. Diperlukan jika Pelanggan mengelola KekType.
  - `[KekVaultResourceId <String>]`: Id sumber daya kek vault. Diperlukan jika Pelanggan mengelola KekType.

PREFERENSI <IPreferences>: Preferensi untuk urutan.
  - `[EncryptionPreferenceDoubleEncryption <DoubleEncryption?>]`: Menentukan lapisan sekunder dari pemberkasan enkripsi berbasis perangkat lunak.
  - `[PreferredDataCenterRegion <String[]>]`: Kawasan pusat data pilihan.
  - `[TransportPreferencePreferredShipmentType <TransportShipmentTypes?>]`: Menunjukkan jenis Logistik Pengiriman yang lebih disukai pelanggan.

SHIPPINGADDRESS <IShippingAddress>: Alamat pengiriman pelanggan.
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

