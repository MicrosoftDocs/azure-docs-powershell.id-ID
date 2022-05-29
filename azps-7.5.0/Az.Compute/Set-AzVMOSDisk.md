---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
ms.assetid: 8F7AF1B8-D769-452C-92CF-4486C3EB894D
online version: https://docs.microsoft.com/powershell/module/az.compute/set-azvmosdisk
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Set-AzVMOSDisk.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Set-AzVMOSDisk.md
ms.openlocfilehash: d71c51f71761cda3a0d72ab99fd351df9385e3b8
ms.sourcegitcommit: 321c644cf2161807a71e1af318fc5c5311d22e25
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/25/2022
ms.locfileid: "145778214"
---
# Set-AzVMOSDisk

## SYNOPSIS
Mengatur properti disk sistem operasi pada komputer virtual.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.compute/set-azvmosdisk) untuk informasi terbaru.

## SYNTAX

### DefaultParamSet (Default)
```
Set-AzVMOSDisk [-VM] <PSVirtualMachine> [[-Name] <String>] [[-VhdUri] <String>] [[-Caching] <CachingTypes>]
 [[-SourceImageUri] <String>] [[-CreateOption] <String>] [-DiskSizeInGB <Int32>] [-ManagedDiskId <String>]
 [-StorageAccountType <String>] [-DiskEncryptionSetId <String>] [-WriteAccelerator] [-DiffDiskSetting <String>]
 [-DiffDiskPlacement <String>] [-DeleteOption <String>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### WindowsParamSet
```
Set-AzVMOSDisk [-VM] <PSVirtualMachine> [[-Name] <String>] [[-VhdUri] <String>] [[-Caching] <CachingTypes>]
 [[-SourceImageUri] <String>] [[-CreateOption] <String>] [-Windows] [-DiskSizeInGB <Int32>]
 [-ManagedDiskId <String>] [-StorageAccountType <String>] [-DiskEncryptionSetId <String>] [-WriteAccelerator]
 [-DiffDiskSetting <String>] [-DiffDiskPlacement <String>] [-DeleteOption <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### WindowsDiskEncryptionParameterSet
```
Set-AzVMOSDisk [-VM] <PSVirtualMachine> [[-Name] <String>] [[-VhdUri] <String>] [[-Caching] <CachingTypes>]
 [[-SourceImageUri] <String>] [[-CreateOption] <String>] [-Windows] [-DiskEncryptionKeyUrl] <String>
 [-DiskEncryptionKeyVaultId] <String> [[-KeyEncryptionKeyUrl] <String>] [[-KeyEncryptionKeyVaultId] <String>]
 [-DiskSizeInGB <Int32>] [-ManagedDiskId <String>] [-StorageAccountType <String>]
 [-DiskEncryptionSetId <String>] [-WriteAccelerator] [-DiffDiskSetting <String>] [-DiffDiskPlacement <String>]
 [-DeleteOption <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### LinuxParamSet
```
Set-AzVMOSDisk [-VM] <PSVirtualMachine> [[-Name] <String>] [[-VhdUri] <String>] [[-Caching] <CachingTypes>]
 [[-SourceImageUri] <String>] [[-CreateOption] <String>] [-Linux] [-DiskSizeInGB <Int32>]
 [-ManagedDiskId <String>] [-StorageAccountType <String>] [-DiskEncryptionSetId <String>] [-WriteAccelerator]
 [-DiffDiskSetting <String>] [-DiffDiskPlacement <String>] [-DeleteOption <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### LinuxDiskEncryptionParameterSet
```
Set-AzVMOSDisk [-VM] <PSVirtualMachine> [[-Name] <String>] [[-VhdUri] <String>] [[-Caching] <CachingTypes>]
 [[-SourceImageUri] <String>] [[-CreateOption] <String>] [-Linux] [-DiskEncryptionKeyUrl] <String>
 [-DiskEncryptionKeyVaultId] <String> [[-KeyEncryptionKeyUrl] <String>] [[-KeyEncryptionKeyVaultId] <String>]
 [-DiskSizeInGB <Int32>] [-ManagedDiskId <String>] [-StorageAccountType <String>]
 [-DiskEncryptionSetId <String>] [-WriteAccelerator] [-DiffDiskSetting <String>] [-DiffDiskPlacement <String>]
 [-DeleteOption <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzVMOSDisk** mengatur properti disk sistem operasi pada komputer virtual.

## EXAMPLES

### Contoh 1: Mengatur properti pada komputer virtual dari gambar platform
```powershell
$AvailabilitySet = Get-AzAvailabilitySet -ResourceGroupName "ResourceGroup11" -Name "AvailabilitySet13" 
$VirtualMachine = New-AzVMConfig -VMName "VirtualMachine17" -VMSize "Standard_A1" -AvailabilitySetID $AvailabilitySet.Id 
Set-AzVMOSDisk -VM $VirtualMachine -Name "OsDisk12" -VhdUri "os.vhd" -Caching ReadWrite
$VirtualMachine = Set-AzVMOperatingSystem -VM $VirtualMachine -Linux -ComputerName "MainComputer" -Credential (Get-Credential) 
$VirtualMachine = Set-AzVMSourceImage -VM $VirtualMachine -PublisherName "Canonical" -Offer "UbuntuServer" -Skus "15.10" -Version "latest"
$VirtualMachine = Set-AzVMOSDisk -VM $VirtualMachine -Name "osDisk.vhd" -VhdUri "https://mystorageaccount.blob.core.windows.net/disks/" -CreateOption FromImage
New-AzVM -VM $VirtualMachine -ResourceGroupName "ResourceGroup11"
```

Perintah pertama mendapatkan set ketersediaan bernama AvailabilitySet13 dalam grup sumber daya bernama ResourceGroup11, lalu menyimpan objek tersebut dalam variabel $AvailabilitySet.
Perintah kedua membuat objek komputer virtual, lalu menyimpannya dalam variabel $VirtualMachine.
Perintah menetapkan nama dan ukuran ke komputer virtual.
Komputer virtual milik set ketersediaan yang disimpan di $AvailabilitySet.
Perintah akhir mengatur properti pada komputer virtual di $VirtualMachine.

### Contoh 2: Mengatur properti pada komputer virtual dari gambar pengguna umum
```powershell
$AvailabilitySet = Get-AzAvailabilitySet -ResourceGroupName "ResourceGroup11" -Name "AvailabilitySet13" 
$VirtualMachine = New-AzVMConfig -VMName "VirtualMachine17" -VMSize "Standard_A1"
$VirtualMachine = Set-AzVMOperatingSystem -VM $VirtualMachine -Linux -ComputerName "MainComputer" -Credential (Get-Credential)
$VirtualMachine = Set-AzVMOSDisk -VM $VirtualMachine -Name "osDisk.vhd" -SourceImageUri "https://mystorageaccount.blob.core.windows.net/vhds/myOSImage.vhd" -VhdUri "https://mystorageaccount.blob.core.windows.net/disks/" -CreateOption fromImage -Linux
New-AzVM -VM $VirtualMachine -ResourceGroupName "ResourceGroup11"
```

Perintah pertama mendapatkan set ketersediaan bernama AvailabilitySet13 di grup sumber daya bernama ResourceGroup11 dan menyimpan objek tersebut dalam variabel $AvailabilitySet.
Perintah kedua membuat objek komputer virtual dan menyimpannya dalam variabel $VirtualMachine.
Perintah menetapkan nama dan ukuran ke komputer virtual.
Komputer virtual milik set ketersediaan yang disimpan di $AvailabilitySet.
Perintah akhir mengatur properti pada komputer virtual di $VirtualMachine.

### Contoh 3: Mengatur properti pada komputer virtual dari gambar pengguna khusus
```powershell
$AvailabilitySet = Get-AzAvailabilitySet -ResourceGroupName "ResourceGroup11" -Name "AvailabilitySet13" 
$VirtualMachine = New-AzVMConfig -VMName "VirtualMachine17" -VMSize "Standard_A1"
$VirtualMachine = Set-AzVMOSDisk -VM $VirtualMachine -Name "osDisk.vhd" -VhdUri "https://mystorageaccount.blob.core.windows.net/disks/" -CreateOption Attach -Linux
New-AzVM -VM $VirtualMachine -ResourceGroupName "ResourceGroup11"
```

Perintah pertama mendapatkan set ketersediaan bernama AvailabilitySet13 di grup sumber daya bernama ResourceGroup11 dan menyimpan objek tersebut dalam variabel $AvailabilitySet.
Perintah kedua membuat objek komputer virtual dan menyimpannya dalam variabel $VirtualMachine.
Perintah menetapkan nama dan ukuran ke komputer virtual.
Komputer virtual milik set ketersediaan yang disimpan di $AvailabilitySet.
Perintah akhir mengatur properti pada komputer virtual di $VirtualMachine.

### Contoh 4: Mengatur pengaturan enkripsi disk pada disk sistem operasi komputer virtual
```powershell
$VirtualMachine = New-AzVMConfig -VMName "VirtualMachine17" -VMSize "Standard_A1"
$VirtualMachine = Set-AzVMOSDisk -VM $VirtualMachine -Name "OsDisk12" -VhdUri "os.vhd" -Caching ReadWrite -Windows -CreateOption "Attach" -DiskEncryptionKeyUrl "https://mytestvault.vault.azure.net/secrets/Test1/514ceb769c984379a7e0230bddaaaaaa" -DiskEncryptionKeyVaultId "/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/myresourcegroup/providers/Microsoft.KeyVault/vaults/mytestvault"
New-AzVM -VM $VirtualMachine -ResourceGroupName " ResourceGroup11"
```

Contoh ini mengatur pengaturan enkripsi disk pada disk sistem operasi komputer virtual.

## PARAMETERS

### -Penembolokan
Menentukan mode penembolokan disk sistem operasi.
Nilai yang valid adalah: 
- ReadOnly
- ReadWrite Nilai defaultnya adalah ReadWrite.
Mengubah nilai penembolokan menyebabkan komputer virtual dimulai ulang.
Pengaturan ini memengaruhi performa disk.

```yaml
Type: System.Nullable`1[Microsoft.Azure.Management.Compute.Models.CachingTypes]
Parameter Sets: (All)
Aliases:
Accepted values: None, ReadOnly, ReadWrite

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CreateOption
Menentukan apakah cmdlet ini membuat disk di komputer virtual dari platform atau gambar pengguna, atau melampirkan disk yang ada.
Nilai yang valid adalah: 
- Melampirkan.
Tentukan opsi ini untuk membuat komputer virtual dari disk khusus.
Saat Anda menentukan opsi ini, jangan tentukan parameter *SourceImageUri* .
Sebagai gantinya, gunakan cmdlet Set-AzVMSourceImage.
Anda juga harus menggunakan parameter *Windows* atau *Linux* untuk memberi tahu platform azure jenis sistem operasi pada VHD.
Parameter *VhdUri* sudah cukup untuk memberi tahu platform azure lokasi disk yang akan dilampirkan. 
- FromImage.
Tentukan opsi ini untuk membuat komputer virtual dari gambar platform atau gambar pengguna umum.
Dalam kasus gambar pengguna umum, Anda juga perlu menentukan parameter *SourceImageUri* dan parameter *Windows* atau *Linux* untuk memberi tahu platform Azure lokasi dan jenis disk sistem operasi VHD alih-alih menggunakan cmdlet **Set-AzVMSourceImage**.
Dalam kasus gambar platform, parameter *VhdUri* sudah cukup. 
- Kosong.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 5
Default value: None
Accept pipeline input: False
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
Menentukan opsi penghapusan Disk OS setelah penghapusan VM. Opsinya adalah Lepaskan, Hapus

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

### -DiffDiskPlacement
Menentukan penempatan disk ephemeral untuk disk sistem operasi. Properti ini dapat digunakan oleh pengguna dalam permintaan untuk memilih lokasi yaitu disk cache atau ruang disk sumber daya untuk provisi disk OS Ephemeral. Untuk informasi selengkapnya tentang persyaratan ukuran disk OS Ephemeral, silakan lihat persyaratan ukuran disk OS Ephemeral untuk VM Windows di https://docs.microsoft.com/azure/virtual-machines/windows/ephemeral-os-disks#size-requirements dan Linux VM di https://docs.microsoft.com/azure/virtual-machines/linux/ephemeral-os-disks#size-requirements. Parameter ini hanya dapat digunakan jika parameter DiffDiskSetting diatur ke 'Lokal'.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -DiffDiskSetting
Menentukan pengaturan disk yang berbeda untuk disk sistem operasi.

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

### -DiskEncryptionKeyUrl
Menentukan lokasi kunci enkripsi disk.

```yaml
Type: System.String
Parameter Sets: WindowsDiskEncryptionParameterSet, LinuxDiskEncryptionParameterSet
Aliases:

Required: True
Position: 7
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DiskEncryptionKeyVaultId
Menentukan ID sumber daya dari Key Vault yang berisi kunci enkripsi disk.

```yaml
Type: System.String
Parameter Sets: WindowsDiskEncryptionParameterSet, LinuxDiskEncryptionParameterSet
Aliases:

Required: True
Position: 8
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DiskEncryptionSetId
Menentukan ID sumber daya set enkripsi disk yang dikelola pelanggan.  Ini hanya dapat ditentukan untuk disk terkelola.

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
Menentukan ukuran, dalam GB, dari disk sistem operasi.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyEncryptionKeyUrl
Menentukan lokasi kunci enkripsi kunci.

```yaml
Type: System.String
Parameter Sets: WindowsDiskEncryptionParameterSet, LinuxDiskEncryptionParameterSet
Aliases:

Required: False
Position: 9
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyEncryptionKeyVaultId
Menentukan ID sumber daya dari Key Vault yang berisi kunci enkripsi kunci.

```yaml
Type: System.String
Parameter Sets: WindowsDiskEncryptionParameterSet, LinuxDiskEncryptionParameterSet
Aliases:

Required: False
Position: 10
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Linux
Menunjukkan bahwa sistem operasi pada gambar pengguna adalah Linux.
Tentukan parameter ini untuk penyebaran komputer virtual berbasis gambar pengguna.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LinuxParamSet, LinuxDiskEncryptionParameterSet
Aliases:

Required: False
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagedDiskId
Menentukan ID disk terkelola.

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

### -Name
Menentukan nama disk sistem operasi.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: OSDiskName, DiskName

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SourceImageUri
Menentukan URI VHD untuk skenario gambar pengguna.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: SourceImage

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageAccountType
Menentukan jenis akun penyimpanan disk terkelola.

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

### -VhdUri
Menentukan Pengidentifikasi Sumber Daya Seragam (URI) dari hard disk virtual (VHD).
Untuk komputer virtual berbasis gambar, parameter ini menentukan file VHD yang akan dibuat saat gambar platform atau gambar pengguna ditentukan.
Ini adalah lokasi tempat objek besar biner gambar (BLOB) disalin untuk memulai komputer virtual.
Untuk skenario boot komputer virtual berbasis disk, parameter ini menentukan file VHD yang digunakan komputer virtual secara langsung untuk memulai.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: OSDiskVhdUri, DiskVhdUri

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Menentukan objek komputer virtual lokal untuk mengatur properti disk sistem operasi.
Untuk mendapatkan objek komputer virtual, gunakan cmdlet Get-AzVM.

```yaml
Type: Microsoft.Azure.Commands.Compute.Models.PSVirtualMachine
Parameter Sets: (All)
Aliases: VMProfile

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Windows
Menunjukkan bahwa sistem operasi pada gambar pengguna Windows.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: WindowsParamSet, WindowsDiskEncryptionParameterSet
Aliases:

Required: False
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WriteAccelerator
Menentukan apakah WriteAccelerator harus diaktifkan atau dinonaktifkan pada disk OS.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.Commands.Compute.Models.PSVirtualMachine

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Models.PSVirtualMachine

## NOTES

## RELATED LINKS

[Dapatkan-AzVM](./Get-AzVM.md)

[Get-AzAvailabilitySet](./Get-AzAvailabilitySet.md)

[New-AzVMConfig](./New-AzVMConfig.md)


