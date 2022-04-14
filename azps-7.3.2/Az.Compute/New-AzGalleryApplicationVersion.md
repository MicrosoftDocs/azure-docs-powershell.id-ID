---
external help file: ''
Module Name: Az.Compute
online version: https://docs.microsoft.com/powershell/module/az.compute/new-azgalleryapplicationversion
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/New-AzGalleryApplicationVersion.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/New-AzGalleryApplicationVersion.md
ms.openlocfilehash: 7345b444749366fec5c6f05016cb45d192c69f08
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142072291"
---
# New-AzGalleryApplicationVersion

## SYNOPSIS
Membuat atau memperbarui Galeri Versi Aplikasi.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.compute/new-azgalleryapplicationversion) untuk informasi terbaru.

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
Membuat atau memperbarui Galeri Versi Aplikasi.

## EXAMPLES

### Contoh 1: Membuat versi aplikasi galeri.
```powershell
$ctx = New-AzStorageContext -StorageAccountName $storAccName
$SASToken = new-azstorageblobsastoken -Context $ctx -Container $containerName -blob $blobName -Permission r
$storAcc = Get-AzStorageAccount -ResourceGroupName $rgName -Name $storAccName
$blob = Get-AzStorageBlob -Container $containerName -Blob $blobName -Context $storAcc.Context
$SASToken = New-AzStorageBlobSASToken -Container $containerName -Blob $blobName -Permission rwd -Context $storAcc.Context
$SASUri = $blob.ICloudBlob.Uri.AbsoluteUri + "?" +$SASToken 
New-AzGalleryApplicationVersion -ResourceGroupName $rgname -Location EastUS -GalleryName $galleryName -GalleryApplicationName $galleryApplicationName -name "0.1.0" -PackageFileLink $SASUri -Install "powershell -command 'Expand-Archive -Path package.zip -DestinationPath C:\\package\'" -Remove "del C:\\package" 

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
DefaultConfigurationLink dari artefak, harus berupa gumpalan halaman penyimpanan yang dapat dibaca.

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
Nama Definisi Aplikasi galeri tempat Versi Aplikasi akan dibuat.

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
Nama Galeri Aplikasi Bersama tempat Definisi Aplikasi berada.

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

### -Instal
Diperlukan.
Jalur dan argumen untuk menginstal aplikasi galeri.
Ini terbatas hingga 4096 karakter.

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
Nama Galeri Versi Aplikasi yang akan dibuat.
Perlu mengikuti pola nama versi semantik: Karakter yang diperbolehkan adalah digit dan titik.
Digit harus berada dalam rentang bilangan bulat 32-bit.
Format: \<MajorVersion\>.\<MinorVersion\>.\<Patch\>

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

### -PackageFileLink
Diperlukan.
MediaLink dari artefak, harus berupa gumpakan halaman penyimpanan yang dapat dibaca.

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
Tanggal berakhirnya versi gambar galeri.
Properti ini dapat digunakan untuk tujuan penolakan.
Properti ini dapat diperbarui.

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
Jika diatur ke true, Virtual Machines yang disebarkan dari versi terbaru Definisi Gambar tidak akan menggunakan Versi Gambar ini.

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

### -Hapus
Diperlukan.
Jalur dan argumen untuk menghapus aplikasi galeri.
Ini terbatas hingga 4096 karakter.

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
Properti ini akan berlaku untuk kawasan ketika regionalReplicaCount tidak ditentukan.
Properti ini dapat diperbarui.

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
Kredensial langganan yang mengidentifikasi langganan Microsoft Azure secara unik.
ID langganan merupakan bagian dari URI untuk setiap panggilan layanan.

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
Properti ini dapat diperbarui.
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

### -Perbarui
Opsional.
Jalur dan argumen untuk memperbarui aplikasi galeri.
Jika tidak ada, operasi pembaruan akan memanggil perintah hapus pada versi sebelumnya dan perintah instal pada versi aplikasi galeri saat ini.
Ini terbatas hingga 4096 karakter.

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

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Compute.Models.Api20210701.IGalleryApplicationVersion

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


TARGETREGION <ITargetRegion[]>: Wilayah target tempat Versi Gambar akan direplikasi. Properti ini dapat diperbarui.
  - `Name <String>`: Nama kawasan.
  - `[EncryptionDataDiskImage <IDataDiskImageEncryption[]>]`: Daftar spesifikasi enkripsi untuk gambar disk data.
    - `Lun <Int32>`: Properti ini menentukan nomor unit logika disk data. Nilai ini digunakan untuk mengidentifikasi disk data di dalam Mesin Virtual dan oleh karena itu harus unik untuk setiap disk data yang dilampirkan ke Mesin Virtual.
    - `[DiskEncryptionSetId <String>]`: URI relatif yang berisi ID sumber daya kumpulan enkripsi disk.
  - `[OSDiskImageDiskEncryptionSetId <String>]`: URI relatif yang berisi ID sumber daya kumpulan enkripsi disk.
  - `[RegionalReplicaCount <Int32?>]`: Jumlah replika Versi Gambar yang akan dibuat per kawasan. Properti ini dapat diperbarui.
  - `[StorageAccountType <StorageAccountType?>]`: Menentukan tipe akun penyimpanan yang akan digunakan untuk menyimpan gambar. Properti ini tidak dapat diperbarui.

## RELATED LINKS

