---
external help file: ''
Module Name: Az.ImportExport
online version: https://docs.microsoft.com/powershell/module/az.importexport/update-azimportexport
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ImportExport/help/Update-AzImportExport.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ImportExport/help/Update-AzImportExport.md
ms.openlocfilehash: 08f6590082765a253d8e0e296df62a5fd07c84d5
ms.sourcegitcommit: e109cc5320478db6aa8a52d49996b133007a65b9
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 01/12/2022
ms.locfileid: "136733647"
---
# Update-AzImportExport

## SYNOPSIS
Memperbarui properti pekerjaan tertentu.
Anda dapat menghubungi operasi ini untuk memberi tahu Import/Export perusahaan yang terdiri dari pekerjaan impor atau ekspor telah dikirim ke pusat data Microsoft.
Ini juga bisa digunakan untuk membatalkan pekerjaan yang sudah ada.

## SYNTAX

### UpdateExpanded (Default)
```
Update-AzImportExport -Name <String> -ResourceGroupName <String> [-SubscriptionId <String>]
 [-AcceptLanguage <String>] [-BackupDriveManifest] [-CancelRequested] [-DeliveryPackageCarrierName <String>]
 [-DeliveryPackageDriveCount <Int32>] [-DeliveryPackageShipDate <String>]
 [-DeliveryPackageTrackingNumber <String>] [-DriveList <IDriveStatus[]>] [-LogLevel <String>]
 [-ReturnAddressCity <String>] [-ReturnAddressCountryOrRegion <String>] [-ReturnAddressEmail <String>]
 [-ReturnAddressPhone <String>] [-ReturnAddressPostalCode <String>] [-ReturnAddressRecipientName <String>]
 [-ReturnAddressStateOrProvince <String>] [-ReturnAddressStreetAddress1 <String>]
 [-ReturnAddressStreetAddress2 <String>] [-ReturnShippingCarrierAccountNumber <String>]
 [-ReturnShippingCarrierName <String>] [-State <String>] [-Tag <IUpdateJobParametersTags>]
 [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### UpdateViaIdentityExpanded
```
Update-AzImportExport -InputObject <IImportExportIdentity> [-AcceptLanguage <String>] [-BackupDriveManifest]
 [-CancelRequested] [-DeliveryPackageCarrierName <String>] [-DeliveryPackageDriveCount <Int32>]
 [-DeliveryPackageShipDate <String>] [-DeliveryPackageTrackingNumber <String>] [-DriveList <IDriveStatus[]>]
 [-LogLevel <String>] [-ReturnAddressCity <String>] [-ReturnAddressCountryOrRegion <String>]
 [-ReturnAddressEmail <String>] [-ReturnAddressPhone <String>] [-ReturnAddressPostalCode <String>]
 [-ReturnAddressRecipientName <String>] [-ReturnAddressStateOrProvince <String>]
 [-ReturnAddressStreetAddress1 <String>] [-ReturnAddressStreetAddress2 <String>]
 [-ReturnShippingCarrierAccountNumber <String>] [-ReturnShippingCarrierName <String>] [-State <String>]
 [-Tag <IUpdateJobParametersTags>] [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Memperbarui properti pekerjaan tertentu.
Anda dapat menghubungi operasi ini untuk memberi tahu Import/Export perusahaan yang terdiri dari pekerjaan impor atau ekspor telah dikirim ke pusat data Microsoft.
Ini juga bisa digunakan untuk membatalkan pekerjaan yang sudah ada.

## EXAMPLES

### Contoh 1: Perbarui pekerjaan ImportExport menurut grup sumber daya dan nama server
```powershell
PS C:\> Update-AzImportExport -Name test-job -ResourceGroupName ImportTestRG -DeliveryPackageCarrierName pwsh -DeliveryPackageTrackingNumber pwsh20200000
Location Name     Type
-------- ----     ----
East US  test-job Microsoft.ImportExport/jobs
```

Cmdlet ini memperbarui pekerjaan ImportExport menurut grup sumber daya dan nama server.

### Contoh 2: Perbarui pekerjaan ImportExport berdasarkan identitas.
```powershell
PS C:\> Get-AzImportExport -Name test-job -ResourceGroupName ImportTestRG | Update-AzImportExport -CancelRequested
Location Name     Type
-------- ----     ----
East US  test-job Microsoft.ImportExport/jobs
```

Cmdlet ini memperbarui pekerjaan ImportExport berdasarkan identitas.

## PARAMETERS

### -AcceptLanguage
Menentukan bahasa pilihan untuk respons tersebut.

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

### -BackupDriveFest
Menunjukkan apakah file manifes di drive harus disalin untuk memblokir blob.

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

### -CancelRequested
Jika ditentukan, nilai harus benar.
Layanan akan mencoba membatalkan pekerjaan.

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

### -DeliveryPackageCarrierName
Nama operator yang digunakan untuk mengirimkan drive impor atau ekspor.

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

### -DeliveryPackageDriveCount
Jumlah drive yang disertakan dalam paket.

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

### -DeliveryPackageShipDate
Tanggal saat paket dikirimkan.

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

### -DeliveryPackageTrackingNumber
Nomor pelacakan paket tersebut.

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

### -DriveList
Daftar drive yang terdiri dari pekerjaan.
Untuk membuat, lihat bagian CATATAN untuk properti DRIVELIST dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ImportExport.Models.Api20161101.IDriveStatus[]
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
Type: Microsoft.Azure.PowerShell.Cmdlets.ImportExport.Models.IImportExportIdentity
Parameter Sets: UpdateViaIdentityExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -LogLevel
Menunjukkan apakah pembuatan log atau pembuatan log verbose diaktifkan.

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

### -Nama
Nama pekerjaan impor/ekspor.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases: JobName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya mengidentifikasi grup sumber daya dalam langganan pengguna secara unik.

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

### -ReturnAddressCity
Nama kota yang digunakan saat kembali ke drive.

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

### -ReturnAddressCountryOrRegion
Negara atau kawasan yang akan digunakan saat mengembalikan drive.

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

### -ReturnAddressEmail
Alamat email penerima drive yang dikembalikan.

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

### -ReturnAddressPhone
Telepon nomor penerima drive yang dikembalikan.

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

### -ReturnAddressPostalCode
Kode pos yang akan digunakan ketika kembali ke drive.

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

### -ReturnAddressRecipientName
Nama penerima yang akan menerima hard drive ketika hard drive dikembalikan.

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

### -ReturnAddressStateOrProvince
Negara bagian atau provinsi yang akan digunakan saat mengembalikan drive.

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

### -ReturnAddressAddressAddress1
Baris pertama alamat jalan yang digunakan saat kembali ke drive.

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

### -ReturnAddressAddressAddress2
Baris kedua alamat jalan yang akan digunakan saat kembali ke drive.

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

### -ReturnShippingCarrierAccountNumber
Nomor akun pelanggan dengan operator.

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

### -ReturnShippingCarrierName
Nama operator.

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

### -Negara Bagian
Jika ditentukan, nilai harus Pengiriman, yang memberi tahu Import/Export tersebut bahwa paket untuk pekerjaan telah dikirim.
Properti ReturnAddress dan DeliveryPackage harus sudah diatur di permintaan ini atau permintaan sebelumnya, jika tidak permintaan akan gagal.

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

### -SubscriptionId
ID langganan untuk pengguna Azure.

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
Menentukan tag yang akan ditetapkan untuk pekerjaan

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ImportExport.Models.Api20161101.IUpdateJobParametersTags
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ImportExport.Models.IImportExportIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ImportExport.Models.Api20161101.IJobResponse

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


DRIVELIST <dengan IDriveStatus[]>: Daftar drive yang terdiri dari pekerjaan.
  - `[BitLockerKey <String>]`: Kunci BitLocker digunakan untuk mengenkripsi drive.
  - `[BytesSucceeded <Int64?>]`: Byte berhasil ditransfer untuk drive.
  - `[CopyStatus <String>]`: Status detail tentang proses transfer data. Bidang ini tidak dikembalikan dalam respons hingga drive berada dalam status Transfer.
  - `[DriveHeaderHash <String>]`: Nilai hash header drive.
  - `[DriveId <String>]`: Nomor seri perangkat keras drive, tanpa spasi.
  - `[ErrorLogUri <String>]`: URI yang menunjuk ke blob yang berisi log kesalahan untuk operasi transfer data.
  - `[ManifestFile <String>]`: Jalur relatif dari file manifes pada drive. 
  - `[ManifestHash <String>]`: Hash MD5 berkode basis16 dari file manifes pada drive.
  - `[ManifestUri <String>]`: URI yang menunjuk ke blob yang berisi file manifes drive. 
  - `[PercentComplete <Int32?>]`: Persentase selesai untuk drive. 
  - `[State <DriveState?>]`: Status drive saat ini. 
  - `[VerboseLogUri <String>]`: URI yang menunjuk ke blob yang berisi log verbose untuk operasi transfer data. 

INPUTOBJECT <IImportExportIdentity> : Parameter Identitas
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[JobName <String>]`: Nama pekerjaan impor/ekspor.
  - `[LocationName <String>]`: Nama lokasi. Misalnya, AS Barat atau westus.
  - `[ResourceGroupName <String>]`: Nama grup sumber daya mengidentifikasi grup sumber daya dalam langganan pengguna secara unik.
  - `[SubscriptionId <String>]`: ID langganan untuk pengguna Azure.

## RELATED LINKS

