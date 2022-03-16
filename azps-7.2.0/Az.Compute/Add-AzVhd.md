---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
ms.assetid: D08DAA8B-B7BF-4167-AB16-F2723985A0B7
online version: https://docs.microsoft.com/powershell/module/az.compute/add-azvhd
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Add-AzVhd.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Add-AzVhd.md
ms.openlocfilehash: b31d25e22a1e50c871849eba7d9a5ce8580d8c39
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140273333"
---
# Add-AzVhd

## SYNOPSIS
Mengunggah hard disk virtual dari komputer lokal ke Azure (disk terkelola atau blob).

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.compute/add-azvhd) untuk informasi terkini.

## SYNTAX

### DefaultParameterSet (Default)
```
Add-AzVhd [[-ResourceGroupName] <String>] [-Destination] <Uri> [-LocalFilePath] <FileInfo>
 [[-NumberOfUploaderThreads] <Int32>] [[-BaseImageUriToPatch] <Uri>] [-OverWrite] [-skipResizing] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### DirectUploadToManagedDiskSet
```
Add-AzVhd [-ResourceGroupName] <String> [-LocalFilePath] <FileInfo> -DiskName <String> [-Location] <String>
 [-DiskSku <String>] [-Zone <String[]>] [[-NumberOfUploaderThreads] <Int32>] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Add-AzVhd** mengunggah hard disk virtual lokal ke disk terkelola atau akun penyimpanan blob.<br/><br/>

Hard disk virtual yang sedang diunggah haruslah file .vhd dan ukurannya N * Mib + 512 byte. Dengan fungsionalitas Hyper-V, **Add-AzVhd** akan mengonversi file .vhdx menjadi file .vhd sebelum diunggah. Cara ini akan mengonversi file .vhd yang berukuran dinamis menjadi ukuran tetap .vhd dan mengubah ukurannya. Jika Hyper-V tidak ditemukan, kesalahan akan terjadi pada pesan termasuk link ke petunjuk tentang cara mengaktifkan Hyper-V dan langkah-langkah manual untuk mengubah ukuran dan mengonversi. <br/><br/>

Untuk kumpulan Parameter Default (unggah ke blob), yang juga didukung adalah kemampuan untuk mengunggah versi patch file .vhd lokal.
Saat hard disk virtual dasar telah diunggah, Anda bisa mengunggah disk berbeda yang menggunakan gambar dasar sebagai induk.
URI akses bersama (Sas) juga didukung. <br/>
Untuk mengatur Upload Parameter Disk Terkelola, parameter: ResourceGroupName, DiskName, Lokasi, DiskSku, dan Zona akan digunakan untuk membuat disk baru, kemudian hard disk virtual akan diunggah ke dalamnya.

## EXAMPLES

### Contoh 1: Menambahkan file VHD ke blob
```
PS C:\> Add-AzVhd -Destination "http://contosoaccount.blob.core.windows.net/vhdstore/win7baseimage.vhd" -LocalFilePath "C:\vhd\Win7Image.vhd"
```

Perintah ini menambahkan file .vhd ke akun penyimpanan.

### Contoh 2: Tambahkan file VHD ke blob dan timpa tujuan
```
PS C:\> Add-AzVhd -Destination "http://contosoaccount.blob.core.windows.net/vhdstore/win7baseimage.vhd" -LocalFilePath "C:\vhd\Win7Image.vhd" -Overwrite
```

Perintah ini menambahkan file .vhd ke akun penyimpanan.
Perintah akan menimpa file yang sudah ada.

### Contoh 3: Menambahkan file VHD ke blob dengan jumlah utas yang ditentukan
```
PS C:\> Add-AzVhd -Destination "http://contosoaccount.blob.core.windows.net/vhdstore/win7baseimage.vhd" -LocalFilePath "C:\vhd\Win7Image.vhd" -NumberOfUploaderThreads 32
```

Perintah ini menambahkan file .vhd ke akun penyimpanan.
Perintah menentukan jumlah utas yang akan digunakan untuk mengunggah file.

### Contoh 4: Tambahkan file VHD ke blob dan tentukan URI SAS
```
PS C:\> Add-AzVhd -Destination "http://contosoaccount.blob.core.windows.net/vhdstore/win7baseimage.vhd?st=2013-01 -09T22%3A15%3A49Z&amp;se=2013-01-09T23%3A10%3A49Z&amp;sr=b&amp;sp=w&amp;sig=13T9Ow%2FRJAMmhfO%2FaP3HhKKJ6AY093SmveO SIV4%2FR7w%3D" -LocalFilePath "C:\vhd\win7baseimage.vhd"
```

Perintah ini menambahkan file .vhd ke akun penyimpanan dan menentukan URI SAS.

### Contoh 5: Tambahkan file VHD langsung ke disk terkelola.
```
PS C:\> Add-AzVhd -LocalFilePath C:\data.vhd -ResourceGroupName rgname -Location eastus -DiskName newDisk
```

Perintah ini membuat disk terkelola dengan ResourceGroupName, Lokasi, dan DiskName yang diberikan; dan mengunggah file VHD ke dalamnya.

### Contoh 6: Tambahkan file VHD langsung ke disk yang lebih banyak dikonfigurasi.
```
PS C:\> Add-AzVhd -LocalFilePath C:\Data.vhdx -ResourceGroupName rgname -Location eastus -DiskName newDisk -Zone 1 -DiskSku Premium_LRS
```

Perintah ini akan mencoba mengonversi file vhdx menjadi file vhd terlebih dahulu menggunakan Hyper-V. Jika Hyper-V tidak ditemukan, hyper-vhd akan mengembalikan kesalahan saat meminta untuk menggunakan file vhd. Setelah konversi berhasil, file akan membuat disk terkelola dengan parameter yang disediakan, lalu mengunggah file vhd. 

## PARAMETERS

### -AsJob
Jalankan cmdlet di latar belakang dan kembalikan Pekerjaan untuk melacak kemajuan.

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

### -BaseImageUriToPatch
Menentukan URI ke blob gambar dasar di Azure Blob Storage.
Sas dapat ditentukan sebagai nilai untuk parameter ini.

```yaml
Type: System.Uri
Parameter Sets: DefaultParameterSet
Aliases: bs

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tujuan
Menentukan URI dari blob di Storage.
Parameter mendukung SAS URI, meskipun tujuan skenario patching tidak bisa menjadi SAS URI.

```yaml
Type: System.Uri
Parameter Sets: DefaultParameterSet
Aliases: dst

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DiskName
Nama Disk terkelola baru

```yaml
Type: System.String
Parameter Sets: DirectUploadToManagedDiskSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DiskSku
Sku untuk disk yang dikelola. Opsi: Standard_LRS, Premium_LRS, StandardSSD_LRS, UltraSSD_LRS

```yaml
Type: System.String
Parameter Sets: DirectUploadToManagedDiskSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LocalFilePath
Menentukan jalur file .vhd lokal.

```yaml
Type: System.IO.FileInfo
Parameter Sets: (All)
Aliases: lf

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Lokasi
Lokasi Disk Terkelola baru

```yaml
Type: System.String
Parameter Sets: DirectUploadToManagedDiskSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NumberOfUploaderThreads
Menentukan jumlah utas pengunggah yang akan digunakan saat mengunggah file .vhd.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases: th

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -OverWrite
Menunjukkan bahwa cmdlet ini menimpa blob yang sudah ada di URI tujuan yang ditentukan, jika ada.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DefaultParameterSet
Aliases: o

Required: False
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya komputer virtual.

```yaml
Type: System.String
Parameter Sets: DefaultParameterSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: System.String
Parameter Sets: DirectUploadToManagedDiskSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -skipResizing
Melewati ukuran ulang file VHD. Pengguna yang ingin mengunggah file VHD yang ukurannya tidak sejajar (bukan N * Mib + 512 byte) ke blob dapat menggunakan parameter sakelar ini.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DefaultParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Zone
Menentukan daftar zona logika untuk Disk. Untuk melampirkan Disk ke VM, harus zona yang sama dengan VM.

```yaml
Type: System.String[]
Parameter Sets: DirectUploadToManagedDiskSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.Uri

### System.IO.FileInfo

### System.Nullable'1[[System.Int32, System.Private.CoreLib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]

### System.Management.Automation.SwitchParameter

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Models.VhdUploadContext

## CATATAN

## RELATED LINKS

[Simpan-Azvhd](./Save-AzVhd.md)
