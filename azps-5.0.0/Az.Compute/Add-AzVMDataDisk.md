---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
ms.assetid: 169E6694-82CD-4FCB-AB3D-E8A74001B8DB
online version: https://docs.microsoft.com/en-us/powershell/module/az.compute/add-azvmdatadisk
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Compute/Compute/help/Add-AzVMDataDisk.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Compute/Compute/help/Add-AzVMDataDisk.md
ms.openlocfilehash: 29233b0bdce273205acffcb87dbf3a8adb1d4a52
ms.sourcegitcommit: b4a38bcb0501a9016a4998efd377aa75d3ef9ce8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/27/2020
ms.locfileid: "132412218"
---
# Add-AzVMDataDisk

## SYNOPSIS
Menambahkan disk data ke mesin virtual.

## SINTAKS

### VmNormalDiskParameterSetName (Default)
```
Add-AzVMDataDisk [-VM] <PSVirtualMachine> [[-Name] <String>] [[-VhdUri] <String>] [[-Caching] <CachingTypes>]
 [[-DiskSizeInGB] <Int32>] [-Lun] <Int32> [-CreateOption] <String> [[-SourceImageUri] <String>]
 [-DiskEncryptionSetId <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### VmManagedDiskParameterSetName
```
Add-AzVMDataDisk [-VM] <PSVirtualMachine> [[-Name] <String>] [[-Caching] <CachingTypes>]
 [[-DiskSizeInGB] <Int32>] [-Lun] <Int32> [-CreateOption] <String> [[-ManagedDiskId] <String>]
 [[-StorageAccountType] <String>] [-DiskEncryptionSetId <String>] [-WriteAccelerator]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESKRIPSI
Cmdlet **Add-AzVMDataDisk** menambahkan disk data ke mesin virtual.
Anda bisa menambahkan disk data saat membuat mesin virtual, atau Anda bisa menambahkan disk data ke mesin virtual yang sudah ada.

## CONTOH

### Contoh 1: Menambahkan disk data ke mesin virtual baru
```
PS C:\> $VirtualMachine = New-AzVMConfig -VMName "VirtualMachine07" -VMSize "Standard_A1"
PS C:\> $DataDiskVhdUri01 = "https://contoso.blob.core.windows.net/test/data1.vhd"
PS C:\> $DataDiskVhdUri02 = "https://contoso.blob.core.windows.net/test/data2.vhd"
PS C:\> $DataDiskVhdUri03 = "https://contoso.blob.core.windows.net/test/data3.vhd"
PS C:\> $VirtualMachine = Add-AzVMDataDisk -VM $VirtualMachine -Name 'DataDisk1' -Caching 'ReadOnly' -DiskSizeInGB 10 -Lun 0 -VhdUri $DataDiskVhdUri01 -CreateOption Empty
PS C:\> $VirtualMachine = Add-AzVMDataDisk -VM $VirtualMachine -Name 'DataDisk2' -Caching 'ReadOnly' -DiskSizeInGB 11 -Lun 1 -VhdUri $DataDiskVhdUri02 -CreateOption Empty
PS C:\> $VirtualMachine = Add-AzVMDataDisk -VM $VirtualMachine -Name 'DataDisk3' -Caching 'ReadOnly' -DiskSizeInGB 12 -Lun 2 -VhdUri $DataDiskVhdUri03 -CreateOption Empty
```

Perintah pertama membuat objek mesin virtual, lalu menyimpannya di $VirtualMachine variabel.
Perintah menetapkan nama dan ukuran ke komputer virtual.
Tiga perintah berikutnya menetapkan jalur tiga disk data ke variabel $DataDiskVhdUri 01, $DataDiskVhdUri 02, dan $DataDiskVhdUri 03.
Pendekatan ini hanya untuk keterbacaan perintah berikut.
Tiga perintah terakhir masing-masing menambahkan disk data ke mesin virtual yang disimpan di $VirtualMachine.
Perintah menentukan nama dan lokasi untuk disk, dan properti disk lainnya.
URI setiap disk disimpan di $DataDiskVhdUri 01, $DataDiskVhdUri 02, dan $DataDiskVhdUri 03.

### Contoh 2: Menambahkan disk data ke komputer virtual yang sudah ada
```
PS C:\> $VirtualMachine = Get-AzVM -ResourceGroupName "ResourceGroup11" -Name "VirtualMachine07"
PS C:\> Add-AzVMDataDisk -VM $VirtualMachine -Name "disk1" -VhdUri "https://contoso.blob.core.windows.net/vhds/diskstandard03.vhd" -LUN 0 -Caching ReadOnly -DiskSizeinGB 1 -CreateOption Empty
PS C:\> Update-AzVM -ResourceGroupName "ResourceGroup11" -VM $VirtualMachine
```

Perintah pertama mendapatkan mesin virtual bernama VirtualMachine07 menggunakan cmdlet [Get-AzVM.](./Get-AzVM.md)
Perintah menyimpan mesin virtual di $VirtualMachine variabel.
Perintah kedua menambahkan disk data ke mesin virtual yang disimpan di $VirtualMachine.
Perintah terakhir memperbarui status mesin virtual yang disimpan di $VirtualMachine dalam ResourceGroup11.

### Contoh 3: Menambahkan disk data ke komputer virtual baru dari gambar pengguna umum
```
PS C:\> $VirtualMachine = New-AzVMConfig -VMName "VirtualMachine07" -VMSize "Standard_A1"
PS C:\> $DataImageUri = "https://contoso.blob.core.windows.net/system/Microsoft.Compute/Images/captured/dataimage.vhd"
PS C:\> $DataDiskUri = "https://contoso.blob.core.windows.net/test/datadisk.vhd"
PS C:\> $VirtualMachine = Add-AzVMDataDisk -VM $VirtualMachine -Name "disk1" -SourceImageUri $DataImageUri -VhdUri $DataDiskUri -Lun 0 -DiskSizeinGB 10 -CreateOption FromImage
```

Perintah pertama membuat objek mesin virtual dan menyimpannya dalam $VirtualMachine variabel.
Perintah menetapkan nama dan ukuran ke komputer virtual.
Dua perintah berikutnya menetapkan jalur untuk disk data gambar dan data ke $DataImageUri dan $DataDiskUri berikutnya.
Pendekatan ini digunakan untuk meningkatkan keterbacaan perintah berikut.
Perintah terakhir menambahkan disk data ke mesin virtual yang disimpan di $VirtualMachine.
Perintah menentukan nama dan lokasi untuk disk dan properti disk lainnya.

### Contoh 4: Menambahkan disk data ke mesin virtual baru dari gambar pengguna khusus
```
PS C:\> $VirtualMachine = New-AzVMConfig -VMName "VirtualMachine07" -VMSize "Standard_A1"
PS C:\> $DataDiskUri = "https://contoso.blob.core.windows.net/test/datadisk.vhd"
PS C:\> $VirtualMachine = Add-AzVMDataDisk -VM $VirtualMachine -Name "dd1" -VhdUri $DataDiskUri -Lun 0 -DiskSizeinGB 10 -CreateOption Attach
```

Perintah pertama membuat objek mesin virtual dan menyimpannya dalam $VirtualMachine variabel.
Perintah menetapkan nama dan ukuran ke komputer virtual.
Perintah berikutnya menetapkan jalur disk data ke $DataDiskUri variabel.
Pendekatan ini digunakan untuk meningkatkan keterbacaan perintah berikut.
Perintah terakhir menambahkan disk data ke mesin virtual yang disimpan di $VirtualMachine.
Perintah menentukan nama dan lokasi untuk disk, dan properti disk lainnya.

## PARAMETERS

### -Caching
Menentukan mode cache disk.
Nilai yang dapat diterima untuk parameter ini adalah:
- ReadOnly
- ReadWrite
- Tidak ada Nilai default adalah ReadWrite.
Mengubah nilai ini menyebabkan mesin virtual memulai ulang.
Pengaturan ini mempengaruhi konsistensi dan kinerja disk.

```yaml
Type: Microsoft.Azure.Management.Compute.Models.CachingTypes
Parameter Sets: (All)
Aliases:
Accepted values: None, ReadOnly, ReadWrite

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CreateOption
Menentukan apakah cmdlet ini membuat disk di komputer virtual dari platform atau gambar pengguna, membuat disk kosong, atau melampirkan disk yang sudah ada.
Nilai yang dapat diterima untuk parameter ini adalah:
- Lampirkan.
Tentukan opsi ini untuk membuat mesin virtual dari disk khusus.
Ketika Anda menentukan opsi ini, jangan tentukan parameter *SourceImageUri.*
*VhdUri* hanya dibutuhkan untuk memberi tahu platform Azure tentang lokasi hard disk virtual (VHD) untuk melampirkan sebagai disk data ke mesin virtual.
- Kosong.
Tentukan ini untuk membuat disk data kosong.
- FromImage.
Tentukan opsi ini untuk membuat mesin virtual dari gambar atau disk umum.
Ketika menentukan opsi ini, Anda harus menentukan parameter *SourceImageUri* juga untuk memberi tahu lokasi VHD platform Azure untuk dilampirkan sebagai disk data.
Parameter *VhdUri* digunakan sebagai lokasi yang mengidentifikasi tempat VHD disk data akan disimpan ketika digunakan oleh mesin virtual.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 6
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

### -DiskEncryptionSetId
Menentukan Id sumber daya dari kumpulan enkripsi disk yang dikelola pelanggan.  This can only be specified for managed disk.

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

### -DiskSizeInGB
Menentukan ukuran, dalam gigabyte, dari disk kosong untuk dilampirkan ke mesin virtual.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Lun
Menentukan nomor unit logika (LUN) untuk disk data.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: True
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ManagedDiskId
Menentukan ID dari disk yang dikelola.

```yaml
Type: System.String
Parameter Sets: VmManagedDiskParameterSetName
Aliases:

Required: False
Position: 8
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nama
Menentukan nama disk data untuk ditambahkan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SourceImageUri
Menentukan URI sumber dari disk yang dilampirkan cmdlet ini.

```yaml
Type: System.String
Parameter Sets: VmNormalDiskParameterSetName
Aliases: SourceImage

Required: False
Position: 7
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageAccountType
Menentukan tipe akun penyimpanan dari disk terkelola.

```yaml
Type: System.String
Parameter Sets: VmManagedDiskParameterSetName
Aliases:

Required: False
Position: 9
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VhdUri
Menentukan Uniform Resource Identifier (URI) untuk file hard disk virtual (VHD) untuk dibuat ketika gambar platform atau gambar pengguna digunakan.
Cmdlet ini menyalin objek besar biner (blob) gambar ke lokasi ini.
Ini adalah lokasi untuk memulai mesin virtual.

```yaml
Type: System.String
Parameter Sets: VmNormalDiskParameterSetName
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VM
Menentukan objek mesin virtual lokal untuk menambahkan disk data.
Anda dapat menggunakan cmdlet **Get-AzVM** untuk mendapatkan objek mesin virtual.
Anda dapat menggunakan cmdlet **New-AzVMConfig** untuk membuat objek mesin virtual.

```yaml
Type: Microsoft.Azure.Commands.Compute.Models.PSVirtualMachine
Parameter Sets: (All)
Aliases: VMProfile

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -WriteAccelerator
Menentukan apakah WriteAccelerator harus diaktifkan atau dinonaktifkan di disk data yang dikelola.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: VmManagedDiskParameterSetName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUT

### Microsoft.Azure.Commands.Compute.Models.PSVirtualMachine

### System.String

### Microsoft.Azure.Management.Compute.Models.CachingTypes

### System.Nullable'1[[System.Int32, System.Private.CoreLib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]

## OUTPUT

### Microsoft.Azure.Commands.Compute.Models.PSVirtualMachine

### Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachinescaleSetVM

## CATATAN

## LINK TERKAIT

[Remove-AzvMDataDisk](./Remove-AzVMDataDisk.md)

[Get-azvm](./Get-AzVM.md)

[New-azvmConfig](./New-AzVMConfig.md)
