---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help-Help.xml
Module Name: Az.Compute
ms.assetid: 169E6694-82CD-4FCB-AB3D-E8A74001B8DB
online version: https://docs.microsoft.com/en-us/powershell/module/az.compute/add-azvmdatadisk
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Compute/Compute/help/Add-AzVMDataDisk.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Compute/Compute/help/Add-AzVMDataDisk.md
ms.openlocfilehash: 4c7e59b847ec1ae1d95c5a884c8979d12d193084
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142721345"
---
# Add-AzVMDataDisk

## SYNOPSIS
Menambahkan disk data ke mesin virtual.

## SYNTAX

```
Add-AzVMDataDisk [-VM] <PSVirtualMachine> [[-Name] <String>] [[-VhdUri] <String>]
 [[-Caching] <CachingTypes>] [[-DiskSizeInGB] <Int32>] [-Lun] <Int32> [-CreateOption] <DiskCreateOptionTypes>
 [[-SourceImageUri] <String>] [[-ManagedDiskId] <String>] [[-StorageAccountType] <StorageAccountTypes>]
 [-WriteAccelerator] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Add-AzVMDataDisk** menambahkan disk data ke mesin virtual.
Anda dapat menambahkan disk data saat membuat mesin virtual, atau menambahkan disk data ke mesin virtual yang sudah ada.

## EXAMPLES

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

Perintah pertama membuat objek mesin virtual, lalu menyimpannya dalam variabel $VirtualMachine.
Perintah menetapkan nama dan ukuran ke mesin virtual.

Tiga perintah berikutnya menetapkan jalur dari tiga disk data ke variabel $DataDiskVhdUri 01, $DataDiskVhdUri 02, dan $DataDiskVhdUri 03.
Pendekatan ini hanya untuk keterbacaan perintah berikut.

Tiga perintah terakhir masing-masing menambahkan disk data ke mesin virtual yang disimpan di $VirtualMachine.
Perintah menentukan nama dan lokasi untuk diska, dan properti disk lainnya.
URI dari setiap disk disimpan di $DataDiskVhdUri 01, $DataDiskVhdUri 02, dan $DataDiskVhdUri 03.

### Contoh 2: Menambahkan disk data ke mesin virtual yang sudah ada
```
PS C:\> $VirtualMachine = Get-AzVM -ResourceGroupName "ResourceGroup11" -Name "VirtualMachine07"
PS C:\> Add-AzVMDataDisk -VM $VirtualMachine -Name "disk1" -VhdUri "https://contoso.blob.core.windows.net/vhds/diskstandard03.vhd" -LUN 0 -Caching ReadOnly -DiskSizeinGB 1 -CreateOption Empty
PS C:\> Update-AzVM -ResourceGroupName "ResourceGroup11" -VM $VirtualMachine
```

Perintah pertama mendapatkan mesin virtual bernama VirtualMachine07 dengan menggunakan cmdlet [Get-AzVM](./Get-AzVM.md) .
Perintah menyimpan mesin virtual dalam variabel $VirtualMachine.

Perintah kedua menambahkan disk data ke mesin virtual yang disimpan di $VirtualMachine.

Perintah terakhir memperbarui status mesin virtual yang disimpan di $VirtualMachine di ResourceGroup11.

### Contoh 3: Menambahkan disk data ke mesin virtual baru dari gambar pengguna umum
```
PS C:\> $VirtualMachine = New-AzVMConfig -VMName "VirtualMachine07" -VMSize "Standard_A1"
PS C:\> $DataImageUri = "https://contoso.blob.core.windows.net/system/Microsoft.Compute/Images/captured/dataimage.vhd"
PS C:\> $DataDiskUri = "https://contoso.blob.core.windows.net/test/datadisk.vhd"
PS C:\> $VirtualMachine = Add-AzVMDataDisk -VM $VirtualMachine -Name "disk1" -SourceImageUri $DataImageUri -VhdUri $DataDiskUri -Lun 0 -DiskSizeinGB 10 -CreateOption FromImage
```

Perintah pertama membuat objek mesin virtual dan menyimpannya dalam variabel $VirtualMachine.
Perintah menetapkan nama dan ukuran ke mesin virtual.

Dua perintah berikutnya menetapkan jalur untuk disk data dan gambar data ke variabel $DataImageUri dan $DataDiskUri.
Pendekatan ini digunakan untuk meningkatkan keterbacaan perintah berikut.

Perintah akhir menambahkan disk data ke mesin virtual yang disimpan di $VirtualMachine.
Perintah menentukan nama dan lokasi untuk diska dan properti disk lainnya.

### Contoh 4: Menambahkan disk data ke mesin virtual baru dari gambar pengguna khusus
```
PS C:\> $VirtualMachine = New-AzVMConfig -VMName "VirtualMachine07" -VMSize "Standard_A1"
PS C:\> $DataDiskUri = "https://contoso.blob.core.windows.net/test/datadisk.vhd"
PS C:\> $VirtualMachine = Add-AzVMDataDisk -VM $VirtualMachine -Name "dd1" -VhdUri $DataDiskUri -Lun 0 -DiskSizeinGB 10 -CreateOption Attach
```

Perintah pertama membuat objek mesin virtual dan menyimpannya dalam variabel $VirtualMachine.
Perintah menetapkan nama dan ukuran ke mesin virtual.

Perintah berikutnya menetapkan jalur disk data ke variabel $DataDiskUri.
Pendekatan ini digunakan untuk meningkatkan keterbacaan perintah berikut.

Perintah terakhir menambahkan disk data ke mesin virtual yang disimpan di $VirtualMachine.
Perintah menentukan nama dan lokasi untuk diska, dan properti disk lainnya.

## PARAMETERS

### -Caching
Menentukan mode cache diska.
Nilai yang dapat diterima untuk parameter ini adalah:

- ReadOnly
- ReadWrite
- Tidak

Nilai defaultnya adalah ReadWrite.
Mengubah nilai ini menyebabkan mesin virtual dimulai ulang.

Pengaturan ini mempengaruhi konsistensi dan kinerja disk.

```yaml
Type: CachingTypes
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
Menentukan apakah cmdlet ini membuat disk di mesin virtual dari platform atau gambar pengguna, membuat disk kosong, atau melampirkan disk yang sudah ada.
Nilai yang dapat diterima untuk parameter ini adalah:

- Melampirkan.
Tentukan opsi ini untuk membuat mesin virtual dari disk khusus.
Saat Anda menentukan opsi ini, jangan tentukan parameter *SourceImageUri* .
*VhdUri* adalah semua yang diperlukan untuk memberi tahu platform Azure lokasi hard disk virtual (VHD) untuk dilampirkan sebagai disk data ke mesin virtual.
- Kosong.
Tentukan ini untuk membuat disk data kosong.
- FromImage.
Tentukan opsi ini untuk membuat mesin virtual dari citra atau disk yang diskala.
Ketika menentukan opsi ini, Anda harus menentukan parameter *SourceImageUri* juga untuk memberi tahu platform Azure lokasi VHD untuk dilampirkan sebagai disk data.
Parameter *VhdUri* digunakan sebagai lokasi yang mengidentifikasi tempat VHD disk data akan disimpan ketika digunakan oleh mesin virtual.

```yaml
Type: DiskCreateOptionTypes
Parameter Sets: (All)
Aliases: 
Accepted values: FromImage, Empty, Attach

Required: True
Position: 6
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DiskSizeInGB
Menentukan ukuran, dalam gigabyte, disk kosong untuk dilampirkan ke mesin virtual.

```yaml
Type: Int32
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
Type: Int32
Parameter Sets: (All)
Aliases: 

Required: True
Position: 5
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ManagedDiskId
Menentukan ID disk yang dikelola.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 8
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nama
Menentukan nama disk data yang akan ditambahkan.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SourceImageUri
Menentukan URI sumber diska yang dilampirkan cmdlet ini.

```yaml
Type: String
Parameter Sets: (All)
Aliases: SourceImage

Required: False
Position: 7
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageAccountType
Menentukan tipe akun penyimpanan disk terkelola.

```yaml
Type: StorageAccountTypes
Parameter Sets: (All)
Aliases: 
Accepted values: StandardLRS, PremiumLRS

Required: False
Position: 9
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VhdUri
Menentukan Uniform Resource Identifier (URI) untuk file hard disk virtual (VHD) untuk dibuat ketika gambar platform atau gambar pengguna digunakan.
Cmdlet ini menyalin gambar objek biner besar (blob) ke lokasi ini.
Ini adalah lokasi untuk memulai mesin virtual.

```yaml
Type: String
Parameter Sets: (All)
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
Type: PSVirtualMachine
Parameter Sets: (All)
Aliases: VMProfile

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -WriteAccelerator
Menentukan apakah WriteAccelerator harus diaktifkan atau dinonaktifkan pada disk data.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### PSVirtualMachine
Parameter 'VM' menerima nilai tipe 'PSVirtualMachine' dari pipeline

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Models.PSVirtualMachine

## NOTES

## RELATED LINKS

[Remove-AzVMDataDisk](./Remove-AzVMDataDisk.md)

[Get-AzVM](./Get-AzVM.md)

[New-AzVMConfig](./New-AzVMConfig.md)
