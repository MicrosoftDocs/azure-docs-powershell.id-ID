---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
ms.assetid: 1BECAC91-BB43-46EB-B2C9-C965C6FBC831
online version: https://docs.microsoft.com/powershell/module/az.compute/new-azvmconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/New-AzVMConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/New-AzVMConfig.md
ms.openlocfilehash: 77c6d0a0ff85dc65488e6b46e704ce47e7b9835d
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136532456"
---
# New-AzVMConfig

## SYNOPSIS
Membuat objek mesin virtual yang dapat dikonfigurasi.

## SYNTAX

### DefaultParameterSet (Default)
```
New-AzVMConfig [-VMName] <String> [-VMSize] <String> [[-AvailabilitySetId] <String>] [[-LicenseType] <String>]
 [-Zone <String[]>] [-ProximityPlacementGroupId <String>] [-HostId <String>] [-VmssId <String>]
 [-MaxPrice <Double>] [-EvictionPolicy <String>] [-Priority <String>] [-Tags <Hashtable>] [-EnableUltraSSD]
 [-EncryptionAtHost] [-CapacityReservationGroupId <String>] [-UserData <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ExplicitIdentityParameterSet
```
New-AzVMConfig [-VMName] <String> [-VMSize] <String> [[-AvailabilitySetId] <String>] [[-LicenseType] <String>]
 [-IdentityType] <ResourceIdentityType> [-IdentityId <String[]>] [-Zone <String[]>]
 [-ProximityPlacementGroupId <String>] [-HostId <String>] [-VmssId <String>] [-MaxPrice <Double>]
 [-EvictionPolicy <String>] [-Priority <String>] [-Tags <Hashtable>] [-EnableUltraSSD] [-EncryptionAtHost]
 [-CapacityReservationGroupId <String>] [-UserData <String>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzVMConfig** membuat objek mesin virtual lokal yang dapat dikonfigurasi untuk Azure.
Cmdlet lain dapat digunakan untuk mengonfigurasi objek mesin virtual, seperti Set-AzVMOperatingSystem, Set-AzVMSourceImage, Add-AzVMNetworkInterface, dan Set-AzVMOSDisk.

## EXAMPLES

### Contoh 1: Membuat objek mesin virtual
```
PS C:\> $AvailabilitySet = Get-AzAvailabilitySet -ResourceGroupName "ResourceGroup11" -Name "AvailabilitySet03"
PS C:\> $VirtualMachine = New-AzVMConfig -VMName "VirtualMachine07" -VMSize "Standard_A1" -AvailabilitySetID $AvailabilitySet.Id
```

Perintah pertama mendapatkan ketersediaan yang diatur bernama AvailabilitySet03 dalam grup sumber daya yang bernama ResourceGroup11, lalu menyimpan objek tersebut di $AvailabilitySet sumber daya.
Perintah kedua membuat objek mesin virtual, lalu menyimpannya di $VirtualMachine variabel.
Perintah menetapkan nama dan ukuran ke komputer virtual.
Mesin virtual tersebut merupakan bagian dari ketersediaan yang telah diatur untuk $AvailabilitySet.

## PARAMETERS

### -AvailabilitySetId
Menentukan ID kumpulan ketersediaan.
Untuk mendapatkan objek kumpulan ketersediaan, gunakan cmdlet Get-AzAvailabilitySet.
Objek set ketersediaan berisi properti ID. <br>
Mesin virtual yang ditentukan dalam kumpulan ketersediaan yang sama dialokasikan ke simpul yang berbeda untuk memaksimalkan ketersediaan. <br>
Untuk informasi selengkapnya tentang kumpulan ketersediaan, [lihat Mengelola ketersediaan mesin virtual](/azure/virtual-machines/availability). <br>
Untuk informasi selengkapnya tentang pemeliharaan Azure yang direncanakan, [lihat Pemeliharaan yang direncanakan untuk mesin virtual di Azure](/azure/virtual-machines/maintenance-and-updates?toc=/azure/virtual-machines/windows/toc.json&bc=/azure/virtual-machines/windows/breadcrumb/toc.json) <br>
Saat ini, VM hanya dapat ditambahkan ke kumpulan ketersediaan pada waktu pembuatan. Ketersediaan yang diatur dengan VM yang ditambahkan harus berada di bawah grup sumber daya yang sama dengan sumber daya kumpulan ketersediaan. VM yang sudah ada tidak dapat ditambahkan ke kumpulan ketersediaan. <br>
Properti ini tidak dapat ditemukan bersama dengan referensi properti non-null.virtualMachineScaleSet.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CapacityReservationGroupId
Id Grup reservasi kapasitas yang digunakan untuk mengalokasikan.

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

### -EnableUltraSSD
Memungkinkan kemampuan untuk memiliki satu atau beberapa disk data terkelola dengan UltraSSD_LRS akun penyimpanan vm.
Disk terkelola dengan tipe akun penyimpanan UltraSSD_LRS dapat ditambahkan ke mesin virtual hanya jika properti ini diaktifkan.


```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -EncryptionAtHost
Properti EncryptionAtHost dapat digunakan oleh pengguna dalam permintaan untuk mengaktifkan atau menonaktifkan Enkripsi Host untuk mesin virtual atau kumpulan skala mesin virtual.
Cara ini akan mengaktifkan enkripsi untuk semua disk, termasuk disk Resource/Temp di host itu sendiri.
Default: Enkripsi pada host akan dinonaktifkan kecuali properti ini diatur ke true untuk sumber daya.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -CtionPolicy
Kebijakan perlindungan untuk mesin virtual Azure Spot.  Nilai yang didukung adalah 'Deallocate' dan 'Delete'.

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

### -HostId
The Id of Host

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

### -IdentityId
Menentukan daftar identitas pengguna yang terkait dengan kumpulan skala mesin virtual.
Referensi identitas pengguna akan menjadi ID sumber daya ARM dalam formulir: '/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.ManagedIdentity/identities/{identityName}'

```yaml
Type: System.String[]
Parameter Sets: ExplicitIdentityParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IdentityType
Identitas mesin virtual, jika dikonfigurasi.

```yaml
Type: System.Nullable`1[Microsoft.Azure.Management.Compute.Models.ResourceIdentityType]
Parameter Sets: ExplicitIdentityParameterSet
Aliases:
Accepted values: SystemAssigned, UserAssigned, SystemAssignedUserAssigned, None

Required: True
Position: 4
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LicenseType
Menentukan tipe lisensi, yang menunjukkan bahwa gambar atau disk untuk komputer virtual tersebut berlisensi secara lokal.
Nilai yang mungkin untuk server Windows adalah:
- Windows_Client
- Windows_Server

Kemungkinan nilai untuk sistem operasi Linux Server adalah:
- RHEL_BYOS (untuk RHEL)
- SLES_BYOS (untuk SUSE)

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxPrice
Menentukan harga maksimum yang Anda bersedia untuk membayar VM/VMSS berprioritas rendah. Harga ini dalam Dolar AS. Harga ini akan dibandingkan dengan harga berprioritas rendah saat ini untuk ukuran VM. Selain itu, harga dibandingkan pada saat pembuatan/pembaruan VM/VMSS berprioritas rendah dan operasi hanya akan berhasil jika maxPrice lebih besar dari harga prioritas rendah saat ini. MaxPrice juga akan digunakan untuk membatalkan vm/VMSS prioritas rendah jika harga berprioritas rendah saat ini melampaui maxPrice setelah pembuatan VM/VMSS. Nilai yang mungkin adalah: nilai desimal apa pun yang lebih besar dari nol. Contoh: 0,01538.  -1 menunjukkan bahwa VM/VMSS berprioritas rendah tidak boleh disederhkan untuk alasan harga. Selain itu, harga maks default adalah -1 jika tidak diberikan oleh Anda.

```yaml
Type: System.Double
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Prioritas
Prioritas untuk mesin virtual.  Hanya nilai yang didukung adalah 'Reguler', 'Titik' dan 'Rendah'.
'Reguler' adalah untuk mesin virtual biasa.
'Titik' adalah untuk menemukan mesin virtual.
'Rendah' juga untuk mesin virtual titik tetapi diganti dengan 'Titik'. Harap gunakan 'Titik' dan bukan 'Rendah'.

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

### -ProximityPlacementGroupId
Id sumber daya dari Grup Penempatan Kedekatan untuk digunakan dengan mesin virtual ini.

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

### -Tag
Tag yang dilampirkan ke sumber daya.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases: Tag

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UserData
UserData untuk VM, yang akan menjadi base-64 encoded. Pelanggan tidak boleh rahasia apa pun di sini.

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

### -VMName
Menentukan nama untuk mesin virtual.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ResourceName, Name

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VMSize
Menentukan ukuran untuk mesin virtual.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VmssId
Id kumpulan skala mesin virtual

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

### -Zone
Menentukan daftar zona ketersediaan untuk komputer virtual. Nilai yang diperbolehkan bergantung pada kapabilitas kawasan. Nilai yang diperbolehkan biasanya adalah 1,2,3.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.String[]

### System.Collections.Hashtable

### System.Management.Automation.SwitchParameter

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Models.PSVirtualMachine

## CATATAN

## RELATED LINKS

[Update-azvm](./Update-AzVM.md)

[Set-AzvMOperatingSystem](./Set-AzVMOperatingSystem.md)

[Set-azvmSourceImage](./Set-AzVMSourceImage.md)

[Get-AzAvailabilitySet](./Get-AzAvailabilitySet.md)


