---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
online version: https://docs.microsoft.com/powershell/module/az.compute/add-azvmssvmdatadisk
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Add-AzVmssVMDataDisk.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Add-AzVmssVMDataDisk.md
ms.openlocfilehash: a10a7c49e325afba48842f0f3d84be9d70b32538
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141999642"
---
# Add-AzVmssVMDataDisk

## SYNOPSIS
Menambahkan disk data ke VM Vmss.

## SYNTAX

```
Add-AzVmssVMDataDisk [-VirtualMachineScaleSetVM] <PSVirtualMachineScaleSetVM> [-Lun] <Int32>
 [-CreateOption] <String> [-ManagedDiskId] <String> [-StorageAccountType <String>]
 [-DiskEncryptionSetId <String>] [-Caching <CachingTypes>] [-DiskSizeInGB <Int32>] [-WriteAccelerator]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Add-AzVmssVMDataDisk** menambahkan disk data ke Vmss VM.

## EXAMPLES

### Contoh 1: Menambahkan disk data terkelola ke VM VM.
```powershell
$disk = Get-AzDisk -ResourceGroupName $rgname -DiskName $diskname0
$VmssVM = Get-AzVmssVM -ResourceGroupName "myrg" -VMScaleSetName "myvmss" -InstanceId 0
$VmssVM = Add-AzVmssVMDataDisk -VirtualMachineScaleSetVM $VmssVM -Lun 0 -DiskSizeInGB 10 -CreateOption Attach -StorageAccountType Standard_LRS -ManagedDiskId $disk.Id
Update-AzVmssVM -VirtualMachineScaleSetVM $VmssVM
```

Perintah pertama akan mendapatkan disk terkelola yang sudah ada.
Perintah berikutnya mendapatkan VM Vmss yang sudah ada yang diberikan oleh nama grup sumber daya, nama vmss dan ID instans.
Perintah berikutnya menambahkan disk yang dikelola ke VM Vmss yang disimpan secara lokal di $VmssVM.
Perintah terakhir memperbarui VM VM dengan disk data tambahan.

## PARAMETERS

### -Caching
Menentukan mode cache diska.
Nilai yang dapat diterima untuk parameter ini adalah:
- ReadOnly
- ReadWrite
- Tidak Ada Nilai default adalah ReadWrite.
Mengubah nilai ini menyebabkan mesin virtual dimulai ulang.
Pengaturan ini mempengaruhi konsistensi dan kinerja disk.

```yaml
Type: Microsoft.Azure.Management.Compute.Models.CachingTypes
Parameter Sets: (All)
Aliases:
Accepted values: None, ReadOnly, ReadWrite

Required: False
Position: Named
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
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
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
Menentukan ID sumber daya kumpulan enkripsi disk yang dikelola pelanggan.  Ini hanya dapat ditentukan untuk disk yang dikelola.

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
Menentukan ukuran, dalam gigabyte, disk kosong untuk dilampirkan ke mesin virtual.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Lun
Menentukan nomor unit logika (LUN) untuk disk data.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ManagedDiskId
Menentukan ID disk yang dikelola.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -StorageAccountType
Menentukan tipe akun penyimpanan disk terkelola.

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

### -VirtualMachineScaleSetVM
Menentukan skala mesin virtual lokal set objek VM tempat untuk menambahkan disk data.
Anda dapat menggunakan cmdlet **Get-AzVmssVM** untuk mendapatkan skala mesin virtual yang mengatur objek VM.

```yaml
Type: Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSetVM
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -WriteAccelerator
Menentukan apakah WriteAccelerator harus diaktifkan atau dinonaktifkan pada disk data yang dikelola.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSetVM

### System.Int32

### System.String

### Microsoft.Azure.Management.Compute.Models.CachingTypes

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSetVM

## CATATAN

## RELATED LINKS
