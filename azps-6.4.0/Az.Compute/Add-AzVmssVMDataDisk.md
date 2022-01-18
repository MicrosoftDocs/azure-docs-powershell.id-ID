---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
online version: https://docs.microsoft.com/powershell/module/az.compute/add-azvmssvmdatadisk
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Add-AzVmssVMDataDisk.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Add-AzVmssVMDataDisk.md
ms.openlocfilehash: f7342f4427a3baa6db87ab1bce893870b819d13c
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136195222"
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
Cmdlet **Add-AzVmssVMDataDisk** menambahkan disk data ke VM Vmss.

## EXAMPLES

### Contoh 1: Add a managed data disk to a Vmss VM.
```powershell
PS C:\> $disk = Get-AzDisk -ResourceGroupName $rgname -DiskName $diskname0
PS C:\> $VmssVM = Get-AzVmssVM -ResourceGroupName "myrg" -VMScaleSetName "myvmss" -InstanceId 0
PS C:\> $VmssVM = Add-AzVmssVMDataDisk -VirtualMachineScaleSetVM $VmssVM -Lun 0 -DiskSizeInGB 10 -CreateOption Attach -StorageAccountType Standard_LRS -ManagedDiskId $disk.Id
PS C:\> Update-AzVmssVM -VirtualMachineScaleSetVM $VmssVM
```

Perintah pertama mendapatkan disk terkelola yang sudah ada.
Perintah berikutnya akan memiliki Vmss VM yang sudah ada yang diberikan oleh nama grup sumber daya, nama vmss dan ID instans.
Perintah berikutnya menambahkan disk terkelola ke VMss VM yang disimpan secara lokal di $VmssVM.
Perintah terakhir memperbarui VM VM dengan disk data tambahan.

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
Position: Named
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
Menentukan ID dari disk yang dikelola.

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
Menentukan tipe akun penyimpanan dari disk terkelola.

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

### -virtualMachinescaleSetvm
Menentukan skala mesin virtual lokal mengatur objek VM yang akan ditambahkan disk data.
Anda dapat menggunakan cmdlet **Get-AzVmssVM** untuk mendapatkan objek VM yang diatur skala mesin virtual.

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
Menentukan apakah WriteAccelerator harus diaktifkan atau dinonaktifkan di disk data yang dikelola.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachinescaleSetVM

### System.Int32

### System.String

### Microsoft.Azure.Management.Compute.Models.CachingTypes

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachinescaleSetVM

## CATATAN

## RELATED LINKS
