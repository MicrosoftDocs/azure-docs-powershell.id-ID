---
external help file: ''
Module Name: Az.Compute
online version: https://docs.microsoft.com/powershell/module/az.compute/new-azgalleryapplicationversion
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/New-AzGalleryApplicationVersion.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/New-AzGalleryApplicationVersion.md
ms.openlocfilehash: 558c81a391a19a3e11fdf849a1d983285c2ab82e
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145522543"
---
# New-AzGalleryApplicationVersion

## SYNOPSIS
Membuat atau memperbarui Versi Aplikasi galeri.

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
Membuat atau memperbarui Versi Aplikasi galeri.

## EXAMPLES

### Contoh 1: Membuat versi aplikasi galeri.
```powershell
$ctx = New-AzStorageContext -StorageAccountName $storAccName
$SASToken = New-AzStorageBlobSASToken -Context $ctx -Container $containerName -blob $blobName -Permission r
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

### -DefaultConfigFileLink
Opsional.
defaultConfigurationLink artefak, harus berupa blob halaman penyimpanan yang dapat dibaca.

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
Nama Shared Application Gallery tempat Definisi Aplikasi berada.

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
Wajib diisi.
Jalur dan argumen untuk menginstal aplikasi galeri.
Ini dibatasi hingga 4096 karakter.

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

### -Name
Nama Galeri Versi Aplikasi yang akan dibuat.
Perlu mengikuti pola nama versi semantik: Karakter yang diizinkan adalah digit dan titik.
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
Wajib diisi.
MediaLink artefak, harus berupa blob halaman penyimpanan yang dapat dibaca.

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
Tanggal akhir masa pakai versi gambar galeri.
Properti ini dapat digunakan untuk tujuan penonaktifan.
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

### -Remove
Wajib diisi.
Jalur dan argumen untuk menghapus aplikasi galeri.
Ini dibatasi hingga 4096 karakter.

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
Jumlah replika Versi Gambar yang akan dibuat per wilayah.
Properti ini akan berlaku untuk wilayah ketika regionalReplicaCount tidak ditentukan.
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
Info masuk langganan yang secara unik mengidentifikasi langganan Microsoft Azure.
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
Properti ini dapat diperbarui.
Untuk membuat, lihat bagian CATATAN untuk properti TARGETREGION dan buat tabel hash.

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
Jika tidak ada, maka operasi pembaruan akan memanggil perintah hapus pada versi sebelumnya dan menginstal perintah pada versi aplikasi galeri saat ini.
Ini dibatasi hingga 4096 karakter.

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

### Microsoft.Azure.PowerShell.Cmdlets.Compute.Models.Api20210701.IGalleryApplicationVersion

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


TARGETREGION <ITargetRegion[]>: Wilayah target tempat Versi Gambar akan direplikasi. Properti ini dapat diperbarui.
  - `Name <String>`: Nama wilayah.
  - `[EncryptionDataDiskImage <IDataDiskImageEncryption[]>]`: Daftar spesifikasi enkripsi untuk gambar disk data.
    - `Lun <Int32>`: Properti ini menentukan nomor unit logis disk data. Nilai ini digunakan untuk mengidentifikasi disk data dalam Komputer Virtual dan oleh karena itu harus unik untuk setiap disk data yang terpasang pada Komputer Virtual.
    - `[DiskEncryptionSetId <String>]`: URI relatif yang berisi ID sumber daya set enkripsi disk.
  - `[OSDiskImageDiskEncryptionSetId <String>]`: URI relatif yang berisi ID sumber daya set enkripsi disk.
  - `[RegionalReplicaCount <Int32?>]`: Jumlah replika Versi Gambar yang akan dibuat per wilayah. Properti ini dapat diperbarui.
  - `[StorageAccountType <StorageAccountType?>]`: Menentukan jenis akun penyimpanan yang akan digunakan untuk menyimpan gambar. Properti ini tidak dapat diperbarui.

## RELATED LINKS

