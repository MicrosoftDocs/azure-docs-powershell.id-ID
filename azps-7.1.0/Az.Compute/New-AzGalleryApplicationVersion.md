---
external help file: ''
Module Name: Az.Compute
online version: https://docs.microsoft.com/powershell/module/az.compute/new-azgalleryapplicationversion
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/New-AzGalleryApplicationVersion.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/New-AzGalleryApplicationVersion.md
ms.openlocfilehash: 108430731ee2082a540653928a6fb6b60622e51b
ms.sourcegitcommit: e109cc5320478db6aa8a52d49996b133007a65b9
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 01/12/2022
ms.locfileid: "136729839"
---
# New-AzGalleryApplicationVersion

## SYNOPSIS
Buat atau perbarui galeri Versi Aplikasi.

## SYNTAX

```
New-AzGalleryApplicationVersion -GalleryApplicationName <String> -GalleryName <String> -Name <String>
 -ResourceGroupName <String> -Install <String> -Location <String> -Remove <String> [-SubscriptionId <String>]
 [-DefaultConfigFileLink <String>] [-PackageFileLink <String>] [-PublishingProfileEndOfLifeDate <DateTime>]
 [-PublishingProfileExcludeFromLatest] [-ReplicaCount <Int32>] [-Tag <Hashtable>]
 [-TargetRegion <ITargetRegion[]>] [-Update <String>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait]
 [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Buat atau perbarui galeri Versi Aplikasi.

## EXAMPLES

### Contoh 1: Buat versi aplikasi galeri.
```powershell
PS C:\> $ctx = New-AzStorageContext -StorageAccountName $storAccName
PS C:\> $SASToken = new-azstorageblobsastoken -Context $ctx -Container $containerName -blob $blobName -Permission r
PS C:\> $storAcc = Get-AzStorageAccount -ResourceGroupName $rgName -Name $storAccName
PS C:\> $blob = Get-AzStorageBlob -Container $containerName -Blob $blobName -Context $storAcc.Context
PS C:\> $SASToken = New-AzStorageBlobSASToken -Container $containerName -Blob $blobName -Permission rwd -Context $storAcc.Context
PS C:\> $SASUri = $blob.ICloudBlob.Uri.AbsoluteUri + "?" +$SASToken 
PS C:\> New-AzGalleryApplicationVersion -ResourceGroupName $rgname -Location EastUS -GalleryName $galleryName -GalleryApplicationName $galleryApplicationName -name "0.1.0" -PackageFileLink $SASUri -Install "powershell -command 'Expand-Archive -Path package.zip -DestinationPath C:\\package\'" -Remove "del C:\\package" 

```

Membuat Versi Aplikasi Galeri.
Menggunakan SAS Uri untuk blob untuk PackageFileLink.

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

### -DefaultConfigFileLink
Opsional.
DefaultConfigurationLink artifak, harus blob halaman penyimpanan yang dapat dibaca.

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

### -GalleryApplicationName
Nama definisi Aplikasi galeri tempat Versi Aplikasi akan dibuat.

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

### -GalleryName
Nama Galeri Aplikasi Bersama di mana Definisi Aplikasi berada.

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

### -Install
Diperlukan.
Jalur dan argumen untuk menginstal aplikasi galeri.
Jumlah ini dibatasi hingga 4096 karakter.

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

### -Lokasi
Lokasi sumber daya

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
Nama galeri Versi Aplikasi yang akan dibuat.
Harus mengikuti pola nama versi semantik: Karakter yang diperbolehkan adalah digit dan titik.
Digit harus berada di dalam rentang bilangan bulat 32-bit.
Format: \<MajorVersion\> . \<MinorVersion\> .\<Patch\>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: GalleryApplicationVersionName

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

### -PackageFileLink
Diperlukan.
MediaLink artifak, harus blob halaman penyimpanan yang dapat dibaca.

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

### -PublishingProfileEndOfLifeDate
Tanggal berakhir dari versi gambar galeri.
Properti ini dapat digunakan untuk tujuan pencocokan.
Properti ini dapat diketahui.

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

### -PublishingProfileExcludeFromLatest
Jika diatur ke benar, Mesin Virtual yang digunakan dari versi terbaru Definisi Gambar tidak akan menggunakan Versi Gambar ini.

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

### -Remove
Diperlukan.
Jalur dan argumen untuk menghapus aplikasi galeri.
Jumlah ini dibatasi hingga 4096 karakter.

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

### -ReplicaCount
Jumlah replika Versi Gambar yang akan dibuat per kawasan.
Properti ini akan berlaku untuk kawasan ketikaReplicaCount kawasan tidak ditentukan.
Properti ini dapat diketahui.

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

### -ResourceGroupName
Nama grup sumber daya.

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
Kredensial langganan yang secara unik mengidentifikasi Microsoft Azure langganan tersebut.
ID langganan membentuk bagian dari URI untuk setiap panggilan layanan.

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
Tag sumber daya

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

### -TargetRegion
Wilayah target tempat Versi Gambar akan direplikasi.
Properti ini dapat diketahui.
Untuk membuat, lihat bagian CATATAN untuk properti TARGETREGION dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Compute.Models.Api20210701.ITargetRegion[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Update
Opsional.
Jalur dan argumen untuk memperbarui aplikasi galeri.
Jika tidak ada, operasi pembaruan akan meminta perintah hapus pada versi sebelumnya dan perintah instal di versi aplikasi galeri saat ini.
Jumlah ini dibatasi hingga 4096 karakter.

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

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Compute.Models.Api20210701.IGalleryApplicationVersion

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


TARGETREGION <ITargetRegion[]>: Wilayah target tempat Versi Gambar akan direplikasi. Properti ini dapat diketahui.
  - `Name <String>`: Nama kawasan.
  - `[EncryptionDataDiskImage <IDataDiskImageEncryption[]>]`: Daftar spesifikasi enkripsi untuk gambar disk data.
    - `Lun <Int32>`: Properti ini menentukan nomor unit logika disk data. Nilai ini digunakan untuk mengidentifikasi disk data di dalam Komputer Virtual, dan oleh karena itu harus unik untuk setiap disk data yang terhubung ke Komputer Virtual.
    - `[DiskEncryptionSetId <String>]`: URI relatif berisi ID sumber daya dari kumpulan enkripsi disk.
  - `[OSDiskImageDiskEncryptionSetId <String>]`: URI relatif berisi ID sumber daya dari kumpulan enkripsi disk.
  - `[RegionalReplicaCount <Int32?>]`: Jumlah replika Versi Gambar yang akan dibuat per kawasan. Properti ini dapat diketahui.
  - `[StorageAccountType <StorageAccountType?>]`: Menentukan tipe akun penyimpanan yang akan digunakan untuk menyimpan gambar. Properti ini tidak dapat updatable.

## RELATED LINKS

