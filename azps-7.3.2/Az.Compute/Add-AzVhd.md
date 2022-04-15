---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
ms.assetid: D08DAA8B-B7BF-4167-AB16-F2723985A0B7
online version: https://docs.microsoft.com/powershell/module/az.compute/add-azvhd
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Add-AzVhd.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Add-AzVhd.md
ms.openlocfilehash: 8068892b19e083ebc5689fd6aa79c960f305ae52
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142036775"
---
# Add-AzVhd

## SYNOPSIS
Mengunggah hard disk virtual dari mesin lokal ke Azure (disk terkelola atau blob).

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.compute/add-azvhd) untuk informasi terbaru.

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
**Cmdlet Add-AzVhd** mengunggah hard disk virtual lokal ke disk yang dikelola atau akun penyimpanan blob.<br/>

Hard disk virtual yang sedang diunggah harus berupa file .vhd dan dalam ukuran N * Mib + 512 byte. Menggunakan [fungsiOnalitas Hyper-V](https://docs.microsoft.com/en-us/windows-server/virtualization/hyper-v/hyper-v-technology-overview) , **Add-AzVhd** akan mengonversi file .vhdx apa pun menjadi file .vhd, mengonversi file .vhd berukuran dinamis menjadi ukuran tetap .vhd, dan mengubah ukuran sebelum mengunggah. Untuk mengizinkan fungsionalitas ini, Anda perlu [mengaktifkan Hyper-V](https://docs.microsoft.com/en-us/windows-server/virtualization/hyper-v/get-started/install-the-hyper-v-role-on-windows-server). Jika Anda menggunakan mesin Linux atau memilih untuk tidak menggunakan fungsionalitas ini, Anda perlu [mengubah ukuran file Vhd secara manual](https://docs.microsoft.com/en-us/azure/virtual-machines/linux/create-upload-generic?branch=pr-en-us-185925#resizing-vhds). <br/>

Untuk Kumpulan Parameter Default (unggahan ke blob), juga didukung adalah kemampuan untuk mengunggah versi patch file .vhd lokal.
Ketika hard disk virtual dasar telah diunggah, Anda dapat mengunggah disk berbeda yang menggunakan gambar dasar sebagai induknya.
URI tanda tangan akses bersama (SAS) juga didukung. <br/>

Untuk Upload Langsung ke kumpulan Parameter Disk Terkelola, parameter: ResourceGroupName, DiskName, Location, DiskSku, dan Zone akan digunakan untuk membuat disk baru, lalu hard disk virtual akan diunggah ke disk tersebut. <br/>

Informasi selengkapnya tentang [menggunakan Add-AzVhd untuk mengunggah secara langsung ke disk terkelola](https://docs.microsoft.com/en-us/azure/virtual-machines/windows/disks-upload-vhd-to-managed-disk-powershell#use-add-azvhd).

Untuk file VHD yang lebih besar dari 50 GB, sebaiknya gunakan [AzCopy](https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy-v10?toc=/azure/storage/blobs/toc.json) untuk mengunggah lebih cepat.

## EXAMPLES

### Contoh 1: Menambahkan file VHD ke blob
```powershell
Add-AzVhd -Destination "http://contosoaccount.blob.core.windows.net/vhdstore/win7baseimage.vhd" -LocalFilePath "C:\vhd\Win7Image.vhd"
```

Perintah ini menambahkan file .vhd ke akun penyimpanan.

### Contoh 2: Menambahkan file VHD ke blob dan menimpa tujuan
```powershell
Add-AzVhd -Destination "http://contosoaccount.blob.core.windows.net/vhdstore/win7baseimage.vhd" -LocalFilePath "C:\vhd\Win7Image.vhd" -Overwrite
```

Perintah ini menambahkan file .vhd ke akun penyimpanan.
Perintah menimpa file yang sudah ada.

### Contoh 3: Menambahkan file VHD ke blob dengan jumlah utas yang ditentukan
```powershell
Add-AzVhd -Destination "http://contosoaccount.blob.core.windows.net/vhdstore/win7baseimage.vhd" -LocalFilePath "C:\vhd\Win7Image.vhd" -NumberOfUploaderThreads 32
```

Perintah ini menambahkan file .vhd ke akun penyimpanan.
Perintah menentukan jumlah utas yang akan digunakan untuk mengunggah file.

### Contoh 4: Menambahkan file VHD ke blob dan menentukan SAS URI
```powershell
Add-AzVhd -Destination "http://contosoaccount.blob.core.windows.net/vhdstore/win7baseimage.vhd?st=2013-01 -09T22%3A15%3A49Z&amp;se=2013-01-09T23%3A10%3A49Z&amp;sr=b&amp;sp=w&amp;sig=13T9Ow%2FRJAMmhfO%2FaP3HhKKJ6AY093SmveO SIV4%2FR7w%3D" -LocalFilePath "C:\vhd\win7baseimage.vhd"
```

Perintah ini menambahkan file .vhd ke akun penyimpanan dan menentukan SAS URI.

### Contoh 5: Menambahkan file VHD secara langsung ke disk terkelola.
```powershell
Add-AzVhd -LocalFilePath C:\data.vhd -ResourceGroupName rgname -Location eastus -DiskName newDisk
```

Perintah ini membuat disk yang dikelola dengan ResourceGroupName, Location, dan DiskName yang diberikan; dan mengunggah file VHD ke file tersebut.

### Contoh 6: Menambahkan file VHD secara langsung ke disk yang lebih dikonfigurasi.
```powershell
Add-AzVhd -LocalFilePath C:\Data.vhdx -ResourceGroupName rgname -Location eastus -DiskName newDisk -Zone 1 -DiskSku Premium_LRS
```

Perintah ini akan mencoba mengonversi file vhdx menjadi file vhd terlebih dahulu menggunakan Hyper-V. Jika Hyper-V tidak ditemukan, hyper-V akan mengembalikan kesalahan yang meminta untuk menggunakan file vhd. Setelah berhasil dikonversi, disk tersebut akan membuat disk terkelola dengan parameter yang disediakan, lalu mengunggah file vhd. 

## PARAMETERS

### -AsJob
Jalankan cmdlet di latar belakang dan kembalikan Job untuk melacak kemajuan.

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
Menentukan URI ke blob gambar dasar dalam Azure Blob Storage.
SAS dapat ditentukan sebagai nilai untuk parameter ini.

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
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

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
Menentukan URI blob dalam blob Storage.
Parameter mendukung SAS URI, meskipun tujuan skenario patch tidak dapat berupa SAS URI.

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
Nama Disk yang dikelola baru

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

### -Disksku
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

### -Timpa
Menunjukkan bahwa cmdlet ini menimpa blob yang sudah ada dalam URI tujuan yang ditentukan, jika ada.

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
Menentukan nama grup sumber daya mesin virtual.

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
Lewati perubahan ukuran file VHD. Pengguna yang ingin mengunggah file VHD yang ukurannya tidak sejajar (bukan N * Mib + 512 byte) ke blob dapat menggunakan parameter sakelar ini.

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

### -Zona
Menentukan daftar zona logika untuk Disk. Untuk melampirkan Disk ke VM, haruslah zona yang sama dengan VM.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.Uri

### System.IO.FileInfo

### System.Nullable'1[[System.Int32, System.Private.CoreLib, Version=4.0.0.0, Culture=netral, PublicKeyToken=7cec85d7bea7798e]]

### System.Management.Automation.SwitchParameter

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Models.VhdUploadContext

## CATATAN

## RELATED LINKS

[Save-AzVhd](./Save-AzVhd.md)
