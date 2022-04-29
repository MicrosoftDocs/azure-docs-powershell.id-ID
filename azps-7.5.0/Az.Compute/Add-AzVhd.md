---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
ms.assetid: D08DAA8B-B7BF-4167-AB16-F2723985A0B7
online version: https://docs.microsoft.com/powershell/module/az.compute/add-azvhd
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Add-AzVhd.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Add-AzVhd.md
ms.openlocfilehash: 30948bc610cda894735cb3cba726b9f120a5a276
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144230055"
---
# Add-AzVhd

## SYNOPSIS
Mengunggah hard disk virtual dari komputer lokal ke Azure (disk terkelola atau blob).

## SYNTAX

### DefaultParameterSet (Default)
```
Add-AzVhd [-ResourceGroupName] <String> [-Destination] <Uri> [-LocalFilePath] <FileInfo>
 [[-NumberOfUploaderThreads] <Int32>] [[-BaseImageUriToPatch] <Uri>] [-OverWrite] [-SkipResizing]
 [-AsJob] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### DirectUploadToManagedDiskSet
```
Add-AzVhd [-ResourceGroupName] <String> [-LocalFilePath] <FileInfo> -DiskName <String> [-Location] <String>
 [-DiskSku <String>] [-DiskZone <String[]>] [-DiskHyperVGeneration <String>]
 [-DiskOsType <OperatingSystemTypes>] [[-NumberOfUploaderThreads] <Int32>] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Add-AzVhd** mengunggah hard disk virtual lokal ke disk terkelola atau akun penyimpanan blob.<br/>

Hard disk virtual yang sedang diunggah harus berupa file .vhd dan berukuran N * Mib + 512 byte. Dengan menggunakan [fungsionalitas Hyper-V](https://docs.microsoft.com/en-us/windows-server/virtualization/hyper-v/hyper-v-technology-overview) , **Add-AzVhd** akan mengonversi file .vhdx apa pun ke file .vhd dan mengubah ukuran sebelum mengunggah. Untuk mengizinkan fungsionalitas ini, Anda harus [mengaktifkan Hyper-V](https://docs.microsoft.com/en-us/windows-server/virtualization/hyper-v/get-started/install-the-hyper-v-role-on-windows-server). Jika Anda menggunakan komputer Linux atau memilih untuk tidak menggunakan fungsionalitas ini, Anda harus [mengubah ukuran file VHD secara manual](https://docs.microsoft.com/en-us/azure/virtual-machines/linux/create-upload-generic?branch=pr-en-us-185925#resizing-vhds). Selain itu, **Add-AzVhd** akan mengonversi file VHD berukuran dinamis ke ukuran tetap selama unggahan. Gunakan `-Verbose` untuk mengikuti semua proses. 

Untuk Set Parameter Default (unggah ke blob), juga didukung adalah kemampuan untuk mengunggah versi patch file .vhd lokal.
Ketika hard disk virtual dasar telah diunggah, Anda dapat mengunggah disk berbeda yang menggunakan gambar dasar sebagai induk.
URI tanda tangan akses bersama (SAS) juga didukung. <br/>

Untuk Upload Langsung ke set Parameter Disk Terkelola, parameter: ResourceGroupName, DiskName, Location, DiskSku, dan Zone akan digunakan untuk membuat disk baru, maka hard disk virtual akan diunggah ke dalamnya. <br/>

Informasi selengkapnya tentang [menggunakan Add-AzVhd untuk langsung mengunggah ke disk terkelola](https://docs.microsoft.com/en-us/azure/virtual-machines/windows/disks-upload-vhd-to-managed-disk-powershell#use-add-azvhd).

Untuk file VHD yang lebih besar dari 50 GB, sebaiknya gunakan [AzCopy](https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy-v10?toc=/azure/storage/blobs/toc.json) untuk unggahan yang lebih cepat.

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
Perintah menimpa file yang ada.

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

### Contoh 5: Tambahkan file VHD langsung ke disk terkelola.
```powershell
Add-AzVhd -LocalFilePath C:\data.vhd -ResourceGroupName rgname -Location eastus -DiskName newDisk
```

Perintah ini membuat disk terkelola dengan ResourceGroupName, Location, dan DiskName yang diberikan; dan mengunggah file VHD ke dalamnya.

### Contoh 6: Tambahkan file VHD langsung ke disk yang lebih dikonfigurasi.
```powershell
Add-AzVhd -LocalFilePath C:\Data.vhdx -ResourceGroupName rgname -Location eastus -DiskName newDisk -Zone 1 -DiskSku Premium_LRS
```

Perintah ini akan mencoba mengonversi file vhdx ke file vhd terlebih dahulu menggunakan Hyper-V. Jika Hyper-V tidak ditemukan, hyper-V akan mengembalikan kesalahan yang meminta untuk menggunakan file vhd. Setelah konversi berhasil, ia akan membuat disk terkelola dengan parameter yang disediakan, lalu mengunggah file vhd. 

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

### -Destination
Menentukan URI blob dalam Storage Blob.
Parameter mendukung SAS URI, meskipun tujuan skenario patching tidak dapat menjadi URI SAS.

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

### -DiskHyperVGeneration
Generasi hypervisor Komputer Virtual. Hanya berlaku untuk disk OS. Nilai yang mungkin adalah: 'V1', 'V2'.

```yaml
Type: System.String
Parameter Sets: DirectUploadToManagedDiskSet
Aliases: HyperVGeneration

Required: False
Position: Named
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

### -DiskOsType
Jenis Sistem Operasi dari disk terkelola. Nilai yang mungkin adalah: 'Windows', 'Linux'.

```yaml
Type: Microsoft.Azure.Management.Compute.Models.OperatingSystemTypes
Parameter Sets: DirectUploadToManagedDiskSet
Aliases: OsType
Accepted values: Windows, Linux

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Disksku
Sku untuk disk terkelola. Opsi: Standard_LRS, Premium_LRS, StandardSSD_LRS, UltraSSD_LRS

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

### -DiskZone
Daftar Zona logika untuk Disk.

```yaml
Type: System.String[]
Parameter Sets: DirectUploadToManagedDiskSet
Aliases: Zone

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
Menunjukkan bahwa cmdlet ini menimpa blob yang ada di URI tujuan yang ditentukan, jika ada.

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

### -SkipResizing
Melewati pengubahan ukuran file VHD. Pengguna yang ingin mengunggah file VHD yang ukurannya tidak sejajar (bukan N * Mib + 512 byte) ke blob dapat menggunakan parameter sakelar ini.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

### System.Uri

### System.IO.FileInfo

### System.Nullable'1[[System.Int32, System.Private.CoreLib, Version=4.0.0.0, Culture=netral, PublicKeyToken=7cec85d7bea7798e]]

### System.Management.Automation.SwitchParameter

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Models.VhdUploadContext

## NOTES

## RELATED LINKS

[Save-AzVhd](./Save-AzVhd.md)
