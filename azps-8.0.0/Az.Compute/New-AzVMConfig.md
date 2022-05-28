---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
ms.assetid: 1BECAC91-BB43-46EB-B2C9-C965C6FBC831
online version: https://docs.microsoft.com/powershell/module/az.compute/new-azvmconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/New-AzVMConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/New-AzVMConfig.md
ms.openlocfilehash: bab6fad772a9e948685f9a0423b844435b3b835a
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145538253"
---
# New-AzVMConfig

## SYNOPSIS
Membuat objek komputer virtual yang dapat dikonfigurasi.

## SYNTAX

### DefaultParameterSet (Default)
```
New-AzVMConfig [-VMName] <String> [-VMSize] <String> [[-AvailabilitySetId] <String>] [[-LicenseType] <String>]
 [-Zone <String[]>] [-ProximityPlacementGroupId <String>] [-HostId <String>] [-VmssId <String>]
 [-MaxPrice <Double>] [-EvictionPolicy <String>] [-Priority <String>] [-Tags <Hashtable>] [-EnableUltraSSD]
 [-EncryptionAtHost] [-CapacityReservationGroupId <String>] [-ImageReferenceId <String>] [-UserData <String>] [-PlatformFaultDomain <Int32>]
 [-HibernationEnabled] [-vCPUCountAvailable <Int32>] [-vCPUCountPerCore <Int32>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ExplicitIdentityParameterSet
```
New-AzVMConfig [-VMName] <String> [-VMSize] <String> [[-AvailabilitySetId] <String>] [[-LicenseType] <String>]
 [-IdentityType] <ResourceIdentityType> [-IdentityId <String[]>] [-Zone <String[]>]
 [-ProximityPlacementGroupId <String>] [-HostId <String>] [-VmssId <String>] [-MaxPrice <Double>]
 [-EvictionPolicy <String>] [-Priority <String>] [-Tags <Hashtable>] [-EnableUltraSSD] [-EncryptionAtHost]
 [-CapacityReservationGroupId <String>] [-ImageReferenceId <String>] [-UserData <String>] [-PlatformFaultDomain <Int32>]
 [-HibernationEnabled] [-vCPUCountAvailable <Int32>] [-vCPUCountPerCore <Int32>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzVMConfig** membuat objek komputer virtual lokal yang dapat dikonfigurasi untuk Azure.
Cmdlet lain dapat digunakan untuk mengonfigurasi objek komputer virtual, seperti Set-AzVMOperatingSystem, Set-AzVMSourceImage, Add-AzVMNetworkInterface, dan Set-AzVMOSDisk.

## EXAMPLES

### Contoh 1: Membuat objek komputer virtual
```powershell
$AvailabilitySet = Get-AzAvailabilitySet -ResourceGroupName "ResourceGroup11" -Name "AvailabilitySet03"
$VirtualMachine = New-AzVMConfig -VMName "VirtualMachine07" -VMSize "Standard_A1" -AvailabilitySetID $AvailabilitySet.Id
```

Perintah pertama mendapatkan set ketersediaan bernama AvailabilitySet03 di grup sumber daya bernama ResourceGroup11, lalu menyimpan objek tersebut dalam variabel $AvailabilitySet.
Perintah kedua membuat objek komputer virtual, lalu menyimpannya dalam variabel $VirtualMachine.
Perintah menetapkan nama dan ukuran ke komputer virtual.
Komputer virtual milik set ketersediaan yang disimpan di $AvailabilitySet.

## PARAMETERS

### -AvailabilitySetId
Menentukan ID set ketersediaan.
Untuk mendapatkan objek set ketersediaan, gunakan cmdlet Get-AzAvailabilitySet.
Objek set ketersediaan berisi properti ID. <br>
Komputer virtual yang ditentukan dalam set ketersediaan yang sama dialokasikan ke simpul yang berbeda untuk memaksimalkan ketersediaan. <br>
Untuk informasi selengkapnya tentang set ketersediaan, lihat [Mengelola ketersediaan komputer virtual](/azure/virtual-machines/availability). <br>
Untuk informasi selengkapnya tentang pemeliharaan [terencana Azure, lihat Pemeliharaan terencana untuk komputer virtual di Azure](/azure/virtual-machines/maintenance-and-updates?toc=/azure/virtual-machines/windows/toc.json&bc=/azure/virtual-machines/windows/breadcrumb/toc.json) <br>
Saat ini, VM hanya dapat ditambahkan ke ketersediaan yang ditetapkan pada waktu pembuatan. Ketersediaan yang diatur ke tempat VM ditambahkan harus berada di bawah grup sumber daya yang sama dengan sumber daya set ketersediaan. VM yang ada tidak dapat ditambahkan ke set ketersediaan. <br>
Properti ini tidak dapat ada bersama dengan referensi properties.virtualMachineScaleSet non-null.

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

### -EnableUltrassD
Memungkinkan kemampuan untuk memiliki satu atau beberapa disk data terkelola dengan jenis akun penyimpanan UltraSSD_LRS pada VM.
Disk terkelola dengan jenis akun penyimpanan UltraSSD_LRS dapat ditambahkan ke komputer virtual hanya jika properti ini diaktifkan.


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
Properti EncryptionAtHost dapat digunakan oleh pengguna dalam permintaan untuk mengaktifkan atau menonaktifkan Enkripsi Host untuk komputer virtual atau set skala komputer virtual.
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
Kebijakan pengeluaran untuk komputer virtual Azure Spot.  Nilai yang didukung adalah 'Batalkan alokasi' dan 'Hapus'.

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

### -HibernationEnabled
Bendera yang mengaktifkan atau menonaktifkan kemampuan hibernasi pada VM.

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
Menentukan daftar identitas pengguna yang terkait dengan set skala komputer virtual.
Referensi identitas pengguna akan menjadi id sumber daya ARM dalam formulir: '/subscriptions/{subscriptionId}/resourceGroups/{resourceGroupName}/providers/Microsoft.ManagedIdentity/identities/{identityName}'

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
Identitas komputer virtual, jika dikonfigurasi.

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
Menentukan jenis lisensi, yang menunjukkan bahwa gambar atau disk untuk komputer virtual dilisensikan secara lokal.
Nilai yang mungkin untuk server Windows adalah:
- Windows_Client
- Windows_Server

Nilai yang mungkin untuk sistem operasi Linux Server adalah:
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
Menentukan harga maksimum yang ingin Anda bayar untuk VM/VMSS berprioritas rendah. Harga ini dalam Dolar AS. Harga ini akan dibandingkan dengan harga prioritas rendah saat ini untuk ukuran VM. Selain itu, harga dibandingkan pada saat membuat/memperbarui VM/VMSS prioritas rendah dan operasi hanya akan berhasil jika maxPrice lebih besar dari harga prioritas rendah saat ini. maxPrice juga akan digunakan untuk mengusir VM/VMSS prioritas rendah jika harga prioritas rendah saat ini melampaui maxPrice setelah pembuatan VM/VMSS. Nilai yang mungkin adalah: nilai desimal apa pun yang lebih besar dari nol. Contoh: 0,01538.  -1 menunjukkan bahwa VM/VMSS prioritas rendah tidak boleh dikeluarkan karena alasan harga. Selain itu, harga maksimum default adalah -1 jika tidak disediakan oleh Anda.

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

### -PlatformFaultDomain
Menentukan domain kesalahan komputer virtual.

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

### -Prioritas
Prioritas untuk komputer virtual.  Hanya nilai yang didukung adalah 'Reguler', 'Spot' dan 'Rendah'.
'Reguler' adalah untuk komputer virtual reguler.
'Spot' adalah untuk komputer virtual spot.
'Rendah' juga untuk komputer virtual spot tetapi digantikan oleh 'Spot'. Silakan gunakan 'Spot' alih-alih 'Rendah'.

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
Id sumber daya Grup Penempatan Kedekatan untuk digunakan dengan komputer virtual ini.

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

### -ImageReferenceId
Menentukan id unik gambar galeri bersama untuk penyebaran vm. Ini dapat diambil dari panggilan GET gambar galeri bersama.

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

### -UserData
UserData untuk VM, yang akan dikodekan base-64. Pelanggan tidak boleh meneruskan rahasia apa pun di sini.

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

### -vCPUCountAvailable
Menentukan jumlah vCPU yang tersedia untuk VM. Ketika properti ini tidak ditentukan dalam isi permintaan, perilaku defaultnya adalah mengaturnya ke nilai vCPU yang tersedia untuk ukuran VM yang diekspos dalam respons api daftar [semua ukuran komputer virtual yang tersedia di suatu wilayah](https://docs.microsoft.com/en-us/rest/api/compute/resource-skus/list).

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

### -vCPUCountPerCore
Menentukan rasio vCPU ke inti fisik. Ketika properti ini tidak ditentukan dalam isi permintaan, perilaku default diatur ke nilai vCPUsPerCore untuk Ukuran VM yang diekspos dalam respons api daftar [semua ukuran komputer virtual yang tersedia di suatu wilayah](https://docs.microsoft.com/en-us/rest/api/compute/resource-skus/list). Mengatur properti ini ke 1 juga berarti bahwa hyper-threading dinonaktifkan.

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

### -VMName
Menentukan nama untuk komputer virtual.

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
Menentukan ukuran untuk komputer virtual.

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
Id set skala komputer virtual

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
Menentukan daftar zona ketersediaan untuk komputer virtual. Nilai yang diizinkan bergantung pada kemampuan wilayah. Nilai yang diizinkan biasanya adalah 1,2,3.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

### System.String[]

### System.Collections.Hashtable

### System.Management.Automation.SwitchParameter

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Models.PSVirtualMachine

## NOTES

## RELATED LINKS

[Update-AzVM](./Update-AzVM.md)

[Set-AzVMOperatingSystem](./Set-AzVMOperatingSystem.md)

[Set-AzVMSourceImage](./Set-AzVMSourceImage.md)

[Get-AzAvailabilitySet](./Get-AzAvailabilitySet.md)


