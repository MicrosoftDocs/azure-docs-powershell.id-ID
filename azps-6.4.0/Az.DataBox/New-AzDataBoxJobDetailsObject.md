---
external help file: ''
Module Name: Az.DataBox
online version: https://docs.microsoft.com/powershell/module/az.DataBox/new-AzDataBoxJobDetailsObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataBox/help/New-AzDataBoxJobDetailsObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DataBox/help/New-AzDataBoxJobDetailsObject.md
ms.openlocfilehash: 88af088fbeb8512ceeb77f360e12db66c04efbed
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136173174"
---
# New-AzDataBoxJobDetailsObject

## SYNOPSIS
Membuat objek dalam memori untuk DataBoxJobDetails

## SYNTAX

```
New-AzDataBoxJobDetailsObject -ContactDetail <IContactDetails> -Type <ClassDiscriminator>
 [-DataExportDetail <IDataExportDetails[]>] [-DataImportDetail <IDataImportDetails[]>]
 [-DevicePassword <String>] [-ExpectedDataSizeInTeraByte <Int32>] [-KeyEncryptionKey <IKeyEncryptionKey>]
 [-Preference <IPreferences>] [-ShippingAddress <IShippingAddress>] [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk DataBoxJobDetails

## EXAMPLES

### Contoh 1: {{ Membuat detail pekerjaan kotak data dalam objek memori }}
```powershell
PS C:\> $details = New-AzDataBoxJobDetailsObject -Type "DataBox"  -DataImportDetail  @(@{AccountDetail=$dataAccount; AccountDetailDataAccountType = "StorageAccount"} ) -ContactDetail $contactDetail -ShippingAddress $ShippingDetails
PS C:\> $details

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

{{ Membuat objek dalam memori untuk DataBoxJobDetails }}

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
Detail data yang akan diekspor dari Azure.
Untuk membuat, lihat bagian CATATAN untuk properti DATAEXPORTDETAIL dan membuat tabel hash.

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
Detail data yang akan diimpor ke Azure.
Untuk membuat, lihat bagian CATATAN untuk properti DATAIMPORTDETAIL dan membuat tabel hash.

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
Atur Kata sandi perangkat untuk membuka kotak Data.
Tidak dapat dialihkan untuk pekerjaan TransferType:ExportFromAzure.
Jika ini tidak lolos, layanan akan membuat kata sandi itu sendiri.
Ini tidak akan dikembalikan di Dapatkan Panggilan.
Persyaratan Kata Sandi : Kata sandi harus minimal 12 dan maksimal 64 karakter.
Kata sandi harus memiliki setidaknya satu alfabet huruf besar, satu nomor dan satu karakter khusus.
Password tidak bisa memiliki karakter berikut: IilLoO0 Password hanya bisa memiliki alfabet, angka dan karakter ini: @# \- $%^!+=;:_()]+.

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
Detail tentang tipe enkripsi kunci mana yang digunakan.
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
Preferensi untuk pesanan.
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
Untuk membuat, lihat bagian CATATAN untuk properti SHIPPINGADDRESS dan membuat tabel hash.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DataBox.Models.Api20210301.DataBoxJobDetails

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


CONTACTDETAIL <IContactDetails> : Detail kontak untuk pemberitahuan dan pengiriman.
  - `ContactName <String>`: Nama kontak orang tersebut.
  - `EmailList <String[]>`: Daftar Id Email untuk diberi tahu tentang kemajuan pekerjaan.
  - `Phone <String>`: Telepon nomor kontak.
  - `[Mobile <String>]`: Nomor ponsel orang yang dapat dihubungi.
  - `[NotificationPreference <INotificationPreference[]>]`: Preferensi pemberitahuan untuk tahapan pekerjaan.
    - `SendNotification <Boolean>`: Pemberitahuan diperlukan atau tidak.
    - `StageName <NotificationStageName>`: Nama tahapan.
  - `[PhoneExtension <String>]`: Telepon nomor ekstensi orang yang menghubungi Anda.

DATAEXPORTDETAIL <IDataExportDetails[]>: Detail data yang akan diekspor dari azure.
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
  - `[AccountDetailSharePassword <String>]`: Kata sandi untuk semua berbagi dibuat pada perangkat. Tidak dapat dialihkan untuk pekerjaan TransferType:ExportFromAzure. Jika ini tidak lolos, layanan akan membuat kata sandi itu sendiri. Ini tidak akan dikembalikan di Dapatkan Panggilan. Persyaratan Kata Sandi : Kata sandi harus minimal 12 dan maksimal 64 karakter. Kata sandi harus memiliki setidaknya satu alfabet huruf besar, satu nomor dan satu karakter khusus. Password tidak dapat memiliki karakter berikut: IilLoO0 Password hanya bisa memiliki alfabet, angka dan karakter ini: @# \- $%^!+=;:_()]+
  - `[LogCollectionLevel <LogCollectionLevel?>]`: Tingkat log yang akan dikumpulkan.

DATAIMPORTDETAIL <IDataImportDetails[]>: Detail data yang akan diimpor ke Azure.
  - `AccountDetailDataAccountType <DataAccountType>`: Tipe Akun data yang akan ditransfer.
  - `[AccountDetailSharePassword <String>]`: Kata sandi untuk semua berbagi dibuat pada perangkat. Tidak dapat dialihkan untuk pekerjaan TransferType:ExportFromAzure. Jika ini tidak lolos, layanan akan membuat kata sandi itu sendiri. Ini tidak akan dikembalikan di Dapatkan Panggilan. Persyaratan Kata Sandi : Kata sandi harus minimal 12 dan maksimal 64 karakter. Kata sandi harus memiliki setidaknya satu alfabet huruf besar, satu nomor dan satu karakter khusus. Password tidak dapat memiliki karakter berikut: IilLoO0 Password hanya bisa memiliki alfabet, angka dan karakter ini: @# \- $%^!+=;:_()]+

KEYENCRYPTIONKEY <IKeyEncryptionKey> : Detail tentang tipe enkripsi kunci mana yang sedang digunakan.
  - `KekType <KekType>`: Tipe kunci enkripsi yang digunakan untuk enkripsi kunci.
  - `[IdentityProperty <IIdentityProperties>]`: Properti identitas terkelola digunakan untuk enkripsi kunci.
    - `[Type <String>]`: Tipe identitas layanan terkelola.
    - `[UserAssignedResourceId <String>]`: Id sumber daya arm untuk identitas yang ditetapkan pengguna untuk digunakan untuk mengambil token MSI.
  - `[KekUrl <String>]`: Kunci enkripsi kunci. It is required in case of Customer managed KekType.
  - `[KekVaultResourceId <String>]`: Id sumber daya penyimpanan kek. It is required in case of Customer managed KekType.

PREFERENSI <IPreferences> : Preferensi untuk pesanan.
  - `[EncryptionPreferenceDoubleEncryption <DoubleEncryption?>]`: Menentukan lapisan sekunder terkait enkripsi berbasis perangkat lunak.
  - `[PreferredDataCenterRegion <String[]>]`: Kawasan pusat data pilihan.
  - `[TransportPreferencePreferredShipmentType <TransportShipmentTypes?>]`: Menunjukkan tipe Logistik Pengiriman yang lebih disukai pelanggan.

ALAMAT <IShippingAddress> PENGIRIMAN : Alamat pengiriman pelanggan.
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

