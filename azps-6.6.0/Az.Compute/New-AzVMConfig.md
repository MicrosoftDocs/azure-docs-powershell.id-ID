---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
ms.assetid: 1BECAC91-BB43-46EB-B2C9-C965C6FBC831
online version: https://docs.microsoft.com/powershell/module/az.compute/new-azvmconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/New-AzVMConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/New-AzVMConfig.md
ms.openlocfilehash: cde28960c995c640212436b3c5f29cc7073f3a6f
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141960585"
---
# New-AzVMConfig

## SYNOPSIS
Membuat objek mesin virtual yang dapat dikonfigurasi.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.compute/new-azvmconfig) untuk informasi terbaru.

## SYNTAX

### DefaultParameterSet (Default)
```
New-AzVMConfig [-VMName] <String> [-VMSize] <String> [[-AvailabilitySetId] <String>] [[-LicenseType] <String>]
 [-Zone <String[]>] [-ProximityPlacementGroupId <String>] [-HostId <String>] [-VmssId <String>]
 [-MaxPrice <Double>] [-EvictionPolicy <String>] [-Priority <String>] [-Tags <Hashtable>] [-EnableUltraSSD]
 [-EncryptionAtHost] [-CapacityReservationGroupId <String>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### ExplicitIdentityParameterSet
```
New-AzVMConfig [-VMName] <String> [-VMSize] <String> [[-AvailabilitySetId] <String>] [[-LicenseType] <String>]
 [-IdentityType] <ResourceIdentityType> [-IdentityId <String[]>] [-Zone <String[]>]
 [-ProximityPlacementGroupId <String>] [-HostId <String>] [-VmssId <String>] [-MaxPrice <Double>]
 [-EvictionPolicy <String>] [-Priority <String>] [-Tags <Hashtable>] [-EnableUltraSSD] [-EncryptionAtHost]
 [-CapacityReservationGroupId <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
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

Perintah pertama mendapatkan kumpulan ketersediaan bernama AvailabilitySet03 dalam grup sumber daya bernama ResourceGroup11, lalu menyimpan objek tersebut dalam variabel $AvailabilitySet.
Perintah kedua membuat objek mesin virtual, lalu menyimpannya dalam variabel $VirtualMachine.
Perintah menetapkan nama dan ukuran ke mesin virtual.
Mesin virtual termasuk dalam kumpulan ketersediaan yang disimpan di $AvailabilitySet.

## PARAMETERS

### -AvailabilitySetId
Menentukan ID kumpulan ketersediaan.
Untuk mendapatkan objek kumpulan ketersediaan, gunakan cmdlet Get-AzAvailabilitySet.
Objek set ketersediaan berisi properti ID. <br>
Mesin virtual yang ditentukan dalam kumpulan ketersediaan yang sama dialokasikan ke node yang berbeda untuk memaksimalkan ketersediaan. <br>
Untuk informasi selengkapnya tentang kumpulan ketersediaan, lihat [Mengelola ketersediaan mesin virtual](/azure/virtual-machines/availability). <br>
Untuk informasi selengkapnya tentang pemeliharaan terencana Azure, lihat [Pemeliharaan terencana untuk mesin virtual di Azure](/azure/virtual-machines/maintenance-and-updates?toc=/azure/virtual-machines/windows/toc.json&bc=/azure/virtual-machines/windows/breadcrumb/toc.json) <br>
Saat ini, VM hanya dapat ditambahkan ke ketersediaan yang diatur pada waktu pembuatan. Ketersediaan yang diatur untuk tempat VM ditambahkan harus berada di bawah grup sumber daya yang sama dengan sumber daya kumpulan ketersediaan. VM yang sudah ada tidak bisa ditambahkan ke kumpulan ketersediaan. <br>
Properti ini tidak dapat ada bersama dengan referensi non-null properties.virtualMachineScaleSet.

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
Id grup reservasi kapasitas yang digunakan untuk mengalokasikan.

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

### -EnableUltrassd
Memungkinkan kemampuan untuk memiliki satu atau beberapa disk data terkelola dengan tipe akun penyimpanan UltraSSD_LRS pada VM.
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
Ini akan mengaktifkan enkripsi untuk semua disk termasuk disk Sumber Daya/Temp di host itu sendiri.
Default: Enkripsi di host akan dinonaktifkan kecuali properti ini diatur ke true untuk sumber daya.

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

### -EvictionPolicy
Kebijakan penggalian untuk mesin virtual Azure Spot.  Nilai yang didukung adalah 'Deallocate' dan 'Delete'.

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
Id dari Host

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
Referensi identitas pengguna akan berupa id sumber daya ARM dalam formulir: '/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.ManagedIdentity/identities/{identityName}'

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
Menentukan tipe lisensi, yang menunjukkan bahwa gambar atau disk untuk mesin virtual telah dilisensikan di tempat.
Nilai yang memungkinkan untuk Windows Server adalah:
- Windows_Client
- Windows_Server

Nilai yang memungkinkan untuk sistem operasi Linux Server adalah:
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
Menentukan harga maksimum yang ingin Anda bayar untuk VM/VMSS berprioritas rendah. Harga ini adalah dalam Dolar AS. Harga ini akan dibandingkan dengan harga prioritas rendah saat ini untuk ukuran VM. Juga, harga dibandingkan pada saat membuat / memperbarui VM / VMSS prioritas rendah dan operasi hanya akan berhasil jika maxPrice lebih besar dari harga prioritas rendah saat ini. MaxPrice juga akan digunakan untuk mengusir VM/VMSS berprioritas rendah jika harga prioritas rendah saat ini melampaui maxPrice setelah pembuatan VM/VMSS. Nilai yang memungkinkan adalah: nilai desimal apa pun yang lebih besar dari nol. Contoh: 0.01538.  -1 menunjukkan bahwa VM/VMSs prioritas rendah tidak boleh diusir karena alasan harga. Selain itu, harga maks default adalah -1 jika tidak disediakan oleh Anda.

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
'Reguler' adalah untuk mesin virtual reguler.
'Spot' adalah untuk mesin virtual spot.
'Rendah' juga untuk mesin virtual spot tetapi digantikan dengan 'Spot'. Silakan gunakan 'Spot' dan bukan 'Rendah'.

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

### -Tags
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

### -VMName
Menentukan nama untuk mesin maya.

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

### -Zona
Menentukan daftar zona ketersediaan untuk mesin maya. Nilai yang diperbolehkan bergantung pada kapabilitas kawasan. Nilai yang diizinkan biasanya adalah 1,2,3.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.String[]

### System.Collections.Hashtable

### System.Management.Automation.SwitchParameter

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Models.PSVirtualMachine

## CATATAN

## RELATED LINKS

[Perbarui-AzVM](./Update-AzVM.md)

[Set-AzVMOperatingSystem](./Set-AzVMOperatingSystem.md)

[Set-AzVMSourceImage](./Set-AzVMSourceImage.md)

[Get-AzAvailabilitySet](./Get-AzAvailabilitySet.md)


