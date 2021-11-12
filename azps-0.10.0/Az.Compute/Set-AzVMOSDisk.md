---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help-Help.xml
Module Name: Az.Compute
ms.assetid: 8F7AF1B8-D769-452C-92CF-4486C3EB894D
online version: https://docs.microsoft.com/en-us/powershell/module/az.compute/set-azvmosdisk
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Compute/Compute/help/Set-AzVMOSDisk.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/Azs-tzl/src/Compute/Compute/help/Set-AzVMOSDisk.md
ms.openlocfilehash: 378d0d33d6cc1ceb2eca4773d93f76afbf75cf4b
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132420222"
---
# Set-AzVMOSDisk

## SYNOPSIS
Mengatur properti disk sistem operasi pada komputer virtual.

## SYNTAX

### DefaultParamSet (Default)
```
Set-AzVMOSDisk [-VM] <PSVirtualMachine> [[-Name] <String>] [[-VhdUri] <String>]
 [[-Caching] <CachingTypes>] [[-SourceImageUri] <String>] [[-CreateOption] <DiskCreateOptionTypes>]
 [-DiskSizeInGB <Int32>] [-ManagedDiskId <String>] [-StorageAccountType <StorageAccountTypes>]
 [-WriteAccelerator] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### WindowsParamSet
```
Set-AzVMOSDisk [-VM] <PSVirtualMachine> [[-Name] <String>] [[-VhdUri] <String>]
 [[-Caching] <CachingTypes>] [[-SourceImageUri] <String>] [[-CreateOption] <DiskCreateOptionTypes>] [-Windows]
 [-DiskSizeInGB <Int32>] [-ManagedDiskId <String>] [-StorageAccountType <StorageAccountTypes>]
 [-WriteAccelerator] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### WindowsDiskEncryptionParameterSet
```
Set-AzVMOSDisk [-VM] <PSVirtualMachine> [[-Name] <String>] [[-VhdUri] <String>]
 [[-Caching] <CachingTypes>] [[-SourceImageUri] <String>] [[-CreateOption] <DiskCreateOptionTypes>] [-Windows]
 [-DiskEncryptionKeyUrl] <String> [-DiskEncryptionKeyVaultId] <String> [[-KeyEncryptionKeyUrl] <String>]
 [[-KeyEncryptionKeyVaultId] <String>] [-DiskSizeInGB <Int32>] [-ManagedDiskId <String>]
 [-StorageAccountType <StorageAccountTypes>] [-WriteAccelerator] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### LinuxParamSet
```
Set-AzVMOSDisk [-VM] <PSVirtualMachine> [[-Name] <String>] [[-VhdUri] <String>]
 [[-Caching] <CachingTypes>] [[-SourceImageUri] <String>] [[-CreateOption] <DiskCreateOptionTypes>] [-Linux]
 [-DiskSizeInGB <Int32>] [-ManagedDiskId <String>] [-StorageAccountType <StorageAccountTypes>]
 [-WriteAccelerator] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### LinuxDiskEncryptionParameterSet
```
Set-AzVMOSDisk [-VM] <PSVirtualMachine> [[-Name] <String>] [[-VhdUri] <String>]
 [[-Caching] <CachingTypes>] [[-SourceImageUri] <String>] [[-CreateOption] <DiskCreateOptionTypes>] [-Linux]
 [-DiskEncryptionKeyUrl] <String> [-DiskEncryptionKeyVaultId] <String> [[-KeyEncryptionKeyUrl] <String>]
 [[-KeyEncryptionKeyVaultId] <String>] [-DiskSizeInGB <Int32>] [-ManagedDiskId <String>]
 [-StorageAccountType <StorageAccountTypes>] [-WriteAccelerator] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzVMOSDisk** mengatur properti disk sistem operasi pada mesin virtual.

## EXAMPLES

### Contoh 1: Mengatur properti pada mesin virtual dari gambar platform
```
PS C:\> $AvailabilitySet = Get-AzAvailabilitySet -ResourceGroupName "ResourceGroup11" -Name "AvailabilitySet13" 
PS C:\> $VirtualMachine = New-AzVMConfig -VMName "VirtualMachine17" -VMSize "Standard_A1" -AvailabilitySetID $AvailabilitySet.Id 
PS C:\> Set-AzVMOSDisk -VM $VirtualMachine -Name "OsDisk12" -VhdUri "os.vhd" -Caching ReadWrite
PS C:\> $VirtualMachine = Set-AzVMOperatingSystem -VM $VirtualMachine -Linux -ComputerName "MainComputer" -Credential (Get-Credential) 
PS C:\> $VirtualMachine = Set-AzVMSourceImage -VM $VirtualMachine -PublisherName "Canonical" -Offer "UbuntuServer" -Skus "15.10" -Version "latest" -Caching ReadWrite
PS C:\> $VirtualMachine = Set-AzVMOSDisk -VM $VirtualMachine -Name "osDisk.vhd" -VhdUri "https://mystorageaccount.blob.core.windows.net/disks/" -CreateOption FromImage
PS C:> New-AzVM -VM $VirtualMachine -ResouceGroupName "ResourceGroup11"
```

Perintah pertama mendapatkan kumpulan ketersediaan bernama TersediaSet13 tersedia dalam grup sumber daya yang bernama ResourceGroup11, lalu menyimpan objek tersebut dalam $AvailabilitySet sumber daya.
Perintah kedua membuat objek mesin virtual, lalu menyimpannya di $VirtualMachine variabel.
Perintah menetapkan nama dan ukuran ke komputer virtual.
Mesin virtual tersebut merupakan bagian dari ketersediaan yang telah diatur untuk $AvailabilitySet.
Perintah terakhir mengatur properti di komputer virtual dalam $VirtualMachine.

### Contoh 2: Mengatur properti pada mesin virtual dari gambar pengguna umum
```
PS C:\> $AvailabilitySet = Get-AzAvailabilitySet -ResourceGroupName "ResourceGroup11" -Name "AvailabilitySet13" 
PS C:\> $VirtualMachine = New-AzVMConfig -VMName "VirtualMachine17" -VMSize "Standard_A1"
PS C:\> $VirtualMachine = Set-AzVMOperatingSystem -VM $VirtualMachine -Linux -ComputerName "MainComputer" -Credential (Get-Credential)
PS C:\> $VirtualMachine = Set-AzVMOSDisk -VM $VirtualMachine -Name "osDisk.vhd" -SourceImageUri "https://mystorageaccount.blob.core.windows.net/vhds/myOSImage.vhd" -VhdUri "https://mystorageaccount.blob.core.windows.net/disks/" -CreateOption fromImage -Linux
PS C:> New-AzVM -VM $VirtualMachine -ResouceGroupName "ResourceGroup11"
```

Perintah pertama mendapatkan kumpulan ketersediaan bernama TersediaSet13 yang tersedia dalam grup sumber daya yang bernama ResourceGroup11 dan menyimpan objek tersebut di $AvailabilitySet sumber daya.
Perintah kedua membuat objek mesin virtual dan menyimpannya dalam $VirtualMachine variabel.
Perintah menetapkan nama dan ukuran ke komputer virtual.
Mesin virtual tersebut merupakan bagian dari ketersediaan yang telah diatur untuk $AvailabilitySet.
Perintah terakhir mengatur properti di komputer virtual dalam $VirtualMachine.

### Contoh 3: Mengatur properti pada mesin virtual dari gambar pengguna khusus
```
PS C:\> $AvailabilitySet = Get-AzAvailabilitySet -ResourceGroupName "ResourceGroup11" -Name "AvailabilitySet13" 
PS C:\> $VirtualMachine = New-AzVMConfig -VMName "VirtualMachine17" -VMSize "Standard_A1"
PS C:\> $VirtualMachine = Set-AzVMOSDisk -VM $VirtualMachine -Name "osDisk.vhd" -VhdUri "https://mystorageaccount.blob.core.windows.net/disks/" -CreateOption Attach -Linux
PS C:> New-AzVM -VM $VirtualMachine -ResouceGroupName "ResourceGroup11"
```

Perintah pertama mendapatkan kumpulan ketersediaan bernama TersediaSet13 yang tersedia dalam grup sumber daya yang bernama ResourceGroup11 dan menyimpan objek tersebut di $AvailabilitySet sumber daya.
Perintah kedua membuat objek mesin virtual dan menyimpannya dalam $VirtualMachine variabel.
Perintah menetapkan nama dan ukuran ke komputer virtual.
Mesin virtual tersebut merupakan bagian dari ketersediaan yang telah diatur untuk $AvailabilitySet.
Perintah terakhir mengatur properti di komputer virtual dalam $VirtualMachine.

### Contoh 4: Mengatur pengaturan enkripsi disk pada disk sistem operasi mesin virtual
```
PS C:\> $VirtualMachine = New-AzVMConfig -VMName "VirtualMachine17" -VMSize "Standard_A1"
PS C:> $VirtualMachine = Set-AzVMOSDisk -VM $VirtualMachine -Name "OsDisk12" -VhdUri "os.vhd" -Caching ReadWrite -Windows -CreateOption "Attach" -DiskEncryptionKeyUrl "https://mytestvault.vault.azure.net/secrets/Test1/514ceb769c984379a7e0230bddaaaaaa" -DiskEncryptionKeyVaultId "/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/myresourcegroup/providers/Microsoft.KeyVault/vaults/mytestvault"
PS C:> New-AzVM -VM $VirtualMachine -ResouceGroupName " ResourceGroup11"
```

Contoh ini mengatur pengaturan enkripsi disk pada disk sistem operasi mesin virtual.

## PARAMETERS

### -Caching
Menentukan mode cache dari disk sistem operasi.
Nilai valid adalah: 

- ReadOnly
- ReadWrite

Nilai defaultnya adalah ReadWrite.
Mengubah nilai cache menyebabkan komputer virtual memulai ulang.

Pengaturan ini mempengaruhi kinerja disk.

```yaml
Type: CachingTypes
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
Menentukan apakah cmdlet ini membuat disk di komputer virtual dari platform atau gambar pengguna, atau melampirkan disk yang sudah ada.
Nilai valid adalah: 

- Lampirkan.
Tentukan opsi ini untuk membuat mesin virtual dari disk khusus.
Ketika Anda menentukan opsi ini, jangan tentukan parameter *SourceImageUri.*
Sebagai gantinya, Set-AzVMSourceImage cmdlet.
Anda juga harus menggunakan parameter *Windows* *atau Linux* untuk memberi tahu tipe sistem operasi di VHD platform Azure2.
Parameter *VhdUri* sudah cukup untuk memberi tahu platform Azure2 mengenai lokasi disk untuk dilampirkan. 
- FromImage.
Tentukan opsi ini untuk membuat mesin virtual dari gambar platform atau gambar pengguna umum.
Dalam kasus gambar pengguna yang di generalisasi, Anda juga perlu menentukan parameter *SourceImageUri* dan parameter *Windows* atau *Linux* untuk memberi tahu lokasi platform Azure dan tipe disk sistem operasi VHD daripada menggunakan cmdlet **Set-AzVMSourceImage.**
Dalam kasus gambar platform, parameter *VhdUri* sudah memadai. 
- Kosong.

```yaml
Type: DiskCreateOptionTypes
Parameter Sets: (All)
Aliases: 
Accepted values: FromImage, Empty, Attach

Required: False
Position: 5
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

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

### -DiskEncryptionKeyUrl
Menentukan lokasi kunci enkripsi disk.

```yaml
Type: String
Parameter Sets: WindowsDiskEncryptionParameterSet, LinuxDiskEncryptionParameterSet
Aliases: 

Required: True
Position: 7
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DiskEncryptionKeyVaultId
Menentukan ID sumber daya Vault Kunci yang berisi kunci enkripsi disk.

```yaml
Type: String
Parameter Sets: WindowsDiskEncryptionParameterSet, LinuxDiskEncryptionParameterSet
Aliases: 

Required: True
Position: 8
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DiskSizeInGB
Menentukan ukuran, dalam GB, disk sistem operasi.

```yaml
Type: Int32
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
Type: String
Parameter Sets: WindowsDiskEncryptionParameterSet, LinuxDiskEncryptionParameterSet
Aliases: 

Required: False
Position: 9
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KeyEncryptionKeyVaultId
Menentukan ID sumber daya Vault Kunci yang berisi kunci enkripsi kunci.

```yaml
Type: String
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
Tentukan parameter ini untuk penggunaan mesin virtual berbasis gambar pengguna.

```yaml
Type: SwitchParameter
Parameter Sets: LinuxParamSet, LinuxDiskEncryptionParameterSet
Aliases: 

Required: False
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagedDiskId
Menentukan ID dari disk yang dikelola.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Menentukan nama disk sistem operasi.

```yaml
Type: String
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
Type: String
Parameter Sets: (All)
Aliases: SourceImage

Required: False
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StorageAccountType
Menentukan tipe akun penyimpanan dari disk terkelola.

```yaml
Type: StorageAccountTypes
Parameter Sets: (All)
Aliases: 
Accepted values: StandardLRS, PremiumLRS

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VhdUri
Menentukan Uniform Resource Identifier (URI) dari hard disk virtual (VHD).

Untuk mesin virtual berbasis gambar, parameter ini menentukan file VHD untuk dibuat ketika gambar platform atau gambar pengguna ditentukan.
Ini adalah lokasi disalinnya objek besar biner (BLOB) gambar untuk memulai mesin virtual.

Untuk skenario boot mesin virtual berbasis disk, parameter ini menentukan file VHD yang digunakan mesin virtual secara langsung untuk memulai.

```yaml
Type: String
Parameter Sets: (All)
Aliases: OSDiskVhdUri, DiskVhdUri

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Menentukan objek mesin virtual lokal untuk mengatur properti disk sistem operasi.
Untuk mendapatkan objek mesin virtual, gunakan cmdlet Get-AzVM.

```yaml
Type: PSVirtualMachine
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
Type: SwitchParameter
Parameter Sets: WindowsParamSet, WindowsDiskEncryptionParameterSet
Aliases: 

Required: False
Position: 6
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WriteAccelerator
Menentukan apakah WriteAccelerator harus diaktifkan atau dinonaktifkan di disk OS.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### PSVirtualMachine
Parameter 'VM' menerima nilai tipe 'PSVirtualMachine' dari saluran

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Models.PSVirtualMachine

## CATATAN

## RELATED LINKS

[Get-azvm](./Get-AzVM.md)

[Get-AzAvailabilitySet](./Get-AzAvailabilitySet.md)

[New-azvmConfig](./New-AzVMConfig.md)


