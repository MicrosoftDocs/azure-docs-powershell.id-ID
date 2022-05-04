---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
ms.assetid: 169E6694-82CD-4FCB-AB3D-E8A74001B8DB
online version: https://docs.microsoft.com/powershell/module/az.compute/add-azvmdatadisk
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Add-AzVMDataDisk.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Add-AzVMDataDisk.md
ms.openlocfilehash: eee16c4d7624120cc1071bbb0f590fc6c405cbcb
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144633788"
---
# Add-AzVMDataDisk

## SYNOPSIS
Menambahkan disk data ke komputer virtual.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.compute/add-azvmdatadisk) untuk informasi terbaru.

## SYNTAX

### VmNormalDiskParameterSetName (Default)
```
Add-AzVMDataDisk [-VM] <PSVirtualMachine> [[-Name] <String>] [[-VhdUri] <String>] [[-Caching] <CachingTypes>]
 [[-DiskSizeInGB] <Int32>] [-Lun] <Int32> [-CreateOption] <String> [[-SourceImageUri] <String>]
 [-DiskEncryptionSetId <String>] [-DeleteOption <String>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### VmManagedDiskParameterSetName
```
Add-AzVMDataDisk [-VM] <PSVirtualMachine> [[-Name] <String>] [[-Caching] <CachingTypes>]
 [[-DiskSizeInGB] <Int32>] [-Lun] <Int32> [-CreateOption] <String> [[-ManagedDiskId] <String>]
 [[-StorageAccountType] <String>] [-DiskEncryptionSetId <String>] [-WriteAccelerator] [-DeleteOption <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Add-AzVMDataDisk** menambahkan disk data ke komputer virtual.
Anda dapat menambahkan disk data saat membuat komputer virtual, atau Anda dapat menambahkan disk data ke komputer virtual yang ada.

## EXAMPLES

### Contoh 1: Menambahkan disk data ke komputer virtual baru
```powershell
$VirtualMachine = New-AzVMConfig -VMName "VirtualMachine07" -VMSize "Standard_A1"
$DataDiskVhdUri01 = "https://contoso.blob.core.windows.net/test/data1.vhd"
$DataDiskVhdUri02 = "https://contoso.blob.core.windows.net/test/data2.vhd"
$DataDiskVhdUri03 = "https://contoso.blob.core.windows.net/test/data3.vhd"
$VirtualMachine = Add-AzVMDataDisk -VM $VirtualMachine -Name 'DataDisk1' -Caching 'ReadOnly' -DiskSizeInGB 10 -Lun 0 -VhdUri $DataDiskVhdUri01 -CreateOption Empty
$VirtualMachine = Add-AzVMDataDisk -VM $VirtualMachine -Name 'DataDisk2' -Caching 'ReadOnly' -DiskSizeInGB 11 -Lun 1 -VhdUri $DataDiskVhdUri02 -CreateOption Empty
$VirtualMachine = Add-AzVMDataDisk -VM $VirtualMachine -Name 'DataDisk3' -Caching 'ReadOnly' -DiskSizeInGB 12 -Lun 2 -VhdUri $DataDiskVhdUri03 -CreateOption Empty
```

Perintah pertama membuat objek komputer virtual, lalu menyimpannya dalam variabel $VirtualMachine.
Perintah menetapkan nama dan ukuran ke komputer virtual.
Tiga perintah berikutnya menetapkan jalur tiga disk data ke variabel $DataDiskVhdUri 01, $DataDiskVhdUri 02, dan $DataDiskVhdUri 03.
Pendekatan ini hanya untuk keterbacaan perintah berikut.
Tiga perintah terakhir masing-masing menambahkan disk data ke komputer virtual yang disimpan dalam $VirtualMachine.
Perintah menentukan nama dan lokasi untuk disk, dan properti disk lainnya.
URI setiap disk disimpan dalam $DataDiskVhdUri 01, $DataDiskVhdUri 02, dan $DataDiskVhdUri 03.

### Contoh 2: Menambahkan disk data ke komputer virtual yang ada
```powershell
$VirtualMachine = Get-AzVM -ResourceGroupName "ResourceGroup11" -Name "VirtualMachine07"
Add-AzVMDataDisk -VM $VirtualMachine -Name "disk1" -VhdUri "https://contoso.blob.core.windows.net/vhds/diskstandard03.vhd" -LUN 0 -Caching ReadOnly -DiskSizeinGB 1 -CreateOption Empty
Update-AzVM -ResourceGroupName "ResourceGroup11" -VM $VirtualMachine
```

Perintah pertama mendapatkan komputer virtual bernama VirtualMachine07 dengan menggunakan cmdlet [Get-AzVM](./Get-AzVM.md) .
Perintah menyimpan komputer virtual dalam variabel $VirtualMachine.
Perintah kedua menambahkan disk data ke komputer virtual yang disimpan dalam $VirtualMachine.
Perintah akhir memperbarui status komputer virtual yang disimpan di $VirtualMachine di ResourceGroup11.

### Contoh 3: Menambahkan disk data ke komputer virtual baru dari gambar pengguna umum
```powershell
$VirtualMachine = New-AzVMConfig -VMName "VirtualMachine07" -VMSize "Standard_A1"
$DataImageUri = "https://contoso.blob.core.windows.net/system/Microsoft.Compute/Images/captured/dataimage.vhd"
$DataDiskUri = "https://contoso.blob.core.windows.net/test/datadisk.vhd"
$VirtualMachine = Add-AzVMDataDisk -VM $VirtualMachine -Name "disk1" -SourceImageUri $DataImageUri -VhdUri $DataDiskUri -Lun 0 -DiskSizeinGB 10 -CreateOption FromImage
```

Perintah pertama membuat objek komputer virtual dan menyimpannya dalam variabel $VirtualMachine.
Perintah menetapkan nama dan ukuran ke komputer virtual.
Dua perintah berikutnya menetapkan jalur untuk gambar data dan disk data ke variabel $DataImageUri dan $DataDiskUri masing-masing.
Pendekatan ini digunakan untuk meningkatkan keterbacaan perintah berikut.
Perintah akhir menambahkan disk data ke komputer virtual yang disimpan dalam $VirtualMachine.
Perintah menentukan nama dan lokasi untuk disk dan properti disk lainnya.

### Contoh 4: Menambahkan disk data ke komputer virtual baru dari gambar pengguna khusus
```powershell
$VirtualMachine = New-AzVMConfig -VMName "VirtualMachine07" -VMSize "Standard_A1"
$DataDiskUri = "https://contoso.blob.core.windows.net/test/datadisk.vhd"
$VirtualMachine = Add-AzVMDataDisk -VM $VirtualMachine -Name "dd1" -VhdUri $DataDiskUri -Lun 0 -DiskSizeinGB 10 -CreateOption Attach
```

Perintah pertama membuat objek komputer virtual dan menyimpannya dalam variabel $VirtualMachine.
Perintah menetapkan nama dan ukuran ke komputer virtual.
Perintah berikutnya menetapkan jalur disk data ke variabel $DataDiskUri.
Pendekatan ini digunakan untuk meningkatkan keterbacaan perintah berikut.
Perintah akhir menambahkan disk data ke komputer virtual yang disimpan di $VirtualMachine.
Perintah menentukan nama dan lokasi untuk disk, dan properti disk lainnya.

## PARAMETERS

### -Penembolokan
Menentukan mode penembolokan disk.
Nilai yang dapat diterima untuk parameter ini adalah:
- ReadOnly
- ReadWrite
- Tidak Ada Nilai default adalah ReadWrite.
Mengubah nilai ini menyebabkan komputer virtual dimulai ulang.
Pengaturan ini memengaruhi konsistensi dan performa disk.

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
Menentukan apakah cmdlet ini membuat disk di komputer virtual dari platform atau gambar pengguna, membuat disk kosong, atau melampirkan disk yang ada.
Nilai yang dapat diterima untuk parameter ini adalah:
- Melampirkan.
Tentukan opsi ini untuk membuat komputer virtual dari disk khusus.
Saat Anda menentukan opsi ini, jangan tentukan parameter *SourceImageUri* .
*VhdUri* adalah semua yang diperlukan untuk memberi tahu platform Azure lokasi hard disk virtual (VHD) untuk dilampirkan sebagai disk data ke komputer virtual.
- Kosong.
Tentukan ini untuk membuat disk data kosong.
- Dari Gambar.
Tentukan opsi ini untuk membuat komputer virtual dari citra atau disk umum.
Saat Anda menentukan opsi ini, Anda harus menentukan parameter *SourceImageUri* juga untuk memberi tahu platform Azure lokasi VHD untuk dilampirkan sebagai disk data.
Parameter *VhdUri* digunakan sebagai lokasi yang mengidentifikasi tempat VHD disk data akan disimpan saat digunakan oleh komputer virtual.

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

### -DeleteOption
Opsi Hapus Disk Data. Menentukan tindakan apa yang harus dilakukan pada disk setelah penghapusan VM. Opsinya adalah: Lepaskan, Hapus.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DiskEncryptionSetId
Menentukan ID sumber daya dari kumpulan enkripsi disk yang dikelola pelanggan.  Ini hanya dapat ditentukan untuk disk terkelola.

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
Menentukan ukuran, dalam gigabyte, dari disk kosong untuk dilampirkan ke komputer virtual.

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
Menentukan nomor unit logis (LUN) untuk disk data.

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
Menentukan ID disk terkelola.

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

### -Name
Menentukan nama disk data yang akan ditambahkan.

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
Menentukan URI sumber disk yang dilampirkan cmdlet ini.

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
Menentukan jenis akun penyimpanan disk terkelola.

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
Menentukan Pengidentifikasi Sumber Daya Seragam (URI) untuk file hard disk virtual (VHD) untuk dibuat saat gambar platform atau gambar pengguna digunakan.
Cmdlet ini menyalin objek besar biner gambar (blob) ke lokasi ini.
Ini adalah lokasi untuk memulai komputer virtual.

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
Menentukan objek komputer virtual lokal untuk menambahkan disk data.
Anda dapat menggunakan cmdlet **Get-AzVM** untuk mendapatkan objek komputer virtual.
Anda dapat menggunakan cmdlet **New-AzVMConfig** untuk membuat objek komputer virtual.

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
Menentukan apakah WriteAccelerator harus diaktifkan atau dinonaktifkan pada disk data terkelola.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.Commands.Compute.Models.PSVirtualMachine

### System.String

### Microsoft.Azure.Management.Compute.Models.CachingTypes

### System.Nullable'1[[System.Int32, System.Private.CoreLib, Version=4.0.0.0, Culture=netral, PublicKeyToken=7cec85d7bea7798e]]

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Models.PSVirtualMachine

### Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSetVM

## NOTES

## RELATED LINKS

[Remove-AzVMDataDisk](./Remove-AzVMDataDisk.md)

[Dapatkan-AzVM](./Get-AzVM.md)

[New-AzVMConfig](./New-AzVMConfig.md)
