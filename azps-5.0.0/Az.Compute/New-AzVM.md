---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
ms.assetid: 05E6155D-4F0E-406B-9312-77AD97EF66EE
online version: https://docs.microsoft.com/en-us/powershell/module/az.compute/new-azvm
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Compute/Compute/help/New-AzVM.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Compute/Compute/help/New-AzVM.md
ms.openlocfilehash: 52bc6e2c8dc2ddda1fbeb0e2c6a1be802df5dd46
ms.sourcegitcommit: b4a38bcb0501a9016a4998efd377aa75d3ef9ce8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/27/2020
ms.locfileid: "132408964"
---
# New-AzVM

## SYNOPSIS
Membuat mesin virtual.

## SINTAKS

### SimpleParameterSet (Default)
```
New-AzVM [[-ResourceGroupName] <String>] [[-Location] <String>] [[-Zone] <String[]>] -Name <String>
 -Credential <PSCredential> [-VirtualNetworkName <String>] [-AddressPrefix <String>] [-SubnetName <String>]
 [-SubnetAddressPrefix <String>] [-PublicIpAddressName <String>] [-DomainNameLabel <String>]
 [-AllocationMethod <String>] [-SecurityGroupName <String>] [-OpenPorts <Int32[]>] [-Image <String>]
 [-Size <String>] [-AvailabilitySetName <String>] [-SystemAssignedIdentity] [-UserAssignedIdentity <String>]
 [-AsJob] [-DataDiskSizeInGb <Int32[]>] [-EnableUltraSSD] [-ProximityPlacementGroupId <String>]
 [-HostId <String>] [-VmssId <String>] [-Priority <String>] [-EvictionPolicy <String>] [-MaxPrice <Double>] [-EncryptionAtHost]
 [-HostGroupId <String>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### DefaultParameterSet
```
New-AzVM [-ResourceGroupName] <String> [-Location] <String> [-VM] <PSVirtualMachine> [[-Zone] <String[]>]
 [-DisableBginfoExtension] [-Tag <Hashtable>] [-LicenseType <String>] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### DiskFileParameterSet
```
New-AzVM [[-ResourceGroupName] <String>] [[-Location] <String>] -Name <String> [-VirtualNetworkName <String>]
 [-AddressPrefix <String>] [-SubnetName <String>] [-SubnetAddressPrefix <String>]
 [-PublicIpAddressName <String>] [-DomainNameLabel <String>] [-AllocationMethod <String>]
 [-SecurityGroupName <String>] [-OpenPorts <Int32[]>] -DiskFile <String> [-Linux] [-Size <String>]
 [-AvailabilitySetName <String>] [-SystemAssignedIdentity] [-UserAssignedIdentity <String>] [-AsJob]
 [-DataDiskSizeInGb <Int32[]>] [-EnableUltraSSD] [-ProximityPlacementGroupId <String>] [-HostId <String>]
 [-VmssId <String>] [-Priority <String>] [-EvictionPolicy <String>] [-MaxPrice <Double>] [-EncryptionAtHost]
 [-HostGroupId <String>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESKRIPSI
Cmdlet **New-AzVM** membuat mesin virtual di Azure.
Cmdlet ini mengambil objek mesin virtual sebagai input.
Gunakan cmdlet New-AzVMConfig untuk membuat objek mesin virtual.
Cmdlet lain bisa digunakan untuk mengonfigurasi mesin virtual, seperti Set-AzVMOperatingSystem, Set-AzVMSourceImage, Add-AzVMNetworkInterface, dan Set-AzVMOSDisk.
The `SimpleParameterSet` provides a convenient method to create a VM by making common VM creation arguments opsional.

## CONTOH

### Contoh 1: Membuat mesin virtual
```
PS C:\> New-AzVM -Name MyVm -Credential (Get-Credential)

VERBOSE: Use 'mstsc /v:myvm-222222.eastus.cloudapp.azure.com' to connect to the VM.

ResourceGroupName        : MyVm
Id                       : /subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/MyVm/provi
ders/Microsoft.Compute/virtualMachines/MyVm
VmId                     : 11111111-1111-1111-1111-111111111111
Name                     : MyVm
Type                     : Microsoft.Compute/virtualMachines
Location                 : eastus
Tags                     : {}
HardwareProfile          : {VmSize}
NetworkProfile           : {NetworkInterfaces}
OSProfile                : {ComputerName, AdminUsername, WindowsConfiguration, Secrets}
ProvisioningState        : Succeeded
StorageProfile           : {ImageReference, OsDisk, DataDisks}
FullyQualifiedDomainName : myvm-222222.eastus.cloudapp.azure.com
```

Contoh skrip ini memperlihatkan cara membuat mesin virtual.
Skrip akan meminta nama pengguna dan kata sandi VM.
Skrip ini menggunakan beberapa cmdlet lain.

### Contoh 2: Membuat mesin virtual dari gambar pengguna kustom
```
PS C:\> ## VM Account
# Credentials for Local Admin account you created in the sysprepped (generalized) vhd image
$VMLocalAdminUser = "LocalAdminUser"
$VMLocalAdminSecurePassword = ConvertTo-SecureString "Password" -AsPlainText -Force
## Azure Account
$LocationName = "westus"
$ResourceGroupName = "MyResourceGroup"
# This a Premium_LRS storage account.
# It is required in order to run a client VM with efficiency and high performance.
$StorageAccount = "Mydisk"

## VM
$OSDiskName = "MyClient"
$ComputerName = "MyClientVM"
$OSDiskUri = "https://Mydisk.blob.core.windows.net/disks/MyOSDisk.vhd"
$SourceImageUri = "https://Mydisk.blob.core.windows.net/vhds/MyOSImage.vhd"
$VMName = "MyVM"
# Modern hardware environment with fast disk, high IOPs performance.
# Required to run a client VM with efficiency and performance
$VMSize = "Standard_DS3"
$OSDiskCaching = "ReadWrite"
$OSCreateOption = "FromImage"

## Networking
$DNSNameLabel = "mydnsname" # mydnsname.westus.cloudapp.azure.com
$NetworkName = "MyNet"
$NICName = "MyNIC"
$PublicIPAddressName = "MyPIP"
$SubnetName = "MySubnet"
$SubnetAddressPrefix = "10.0.0.0/24"
$VnetAddressPrefix = "10.0.0.0/16"

$SingleSubnet = New-AzVirtualNetworkSubnetConfig -Name $SubnetName -AddressPrefix $SubnetAddressPrefix
$Vnet = New-AzVirtualNetwork -Name $NetworkName -ResourceGroupName $ResourceGroupName -Location $LocationName -AddressPrefix $VnetAddressPrefix -Subnet $SingleSubnet
$PIP = New-AzPublicIpAddress -Name $PublicIPAddressName -DomainNameLabel $DNSNameLabel -ResourceGroupName $ResourceGroupName -Location $LocationName -AllocationMethod Dynamic
$NIC = New-AzNetworkInterface -Name $NICName -ResourceGroupName $ResourceGroupName -Location $LocationName -SubnetId $Vnet.Subnets[0].Id -PublicIpAddressId $PIP.Id

$Credential = New-Object System.Management.Automation.PSCredential ($VMLocalAdminUser, $VMLocalAdminSecurePassword);

$VirtualMachine = New-AzVMConfig -VMName $VMName -VMSize $VMSize
$VirtualMachine = Set-AzVMOperatingSystem -VM $VirtualMachine -Windows -ComputerName $ComputerName -Credential $Credential -ProvisionVMAgent -EnableAutoUpdate
$VirtualMachine = Add-AzVMNetworkInterface -VM $VirtualMachine -Id $NIC.Id
$VirtualMachine = Set-AzVMOSDisk -VM $VirtualMachine -Name $OSDiskName -VhdUri $OSDiskUri -SourceImageUri $SourceImageUri -Caching $OSDiskCaching -CreateOption $OSCreateOption -Windows

New-AzVM -ResourceGroupName $ResourceGroupName -Location $LocationName -VM $VirtualMachine -Verbose
```

Contoh ini menggunakan gambar sistem operasi kustom ter generalisasi yang sudah ada dan melampirkan disk data ke dalamnya, menyediakan jaringan baru, menempatkan VHD, dan menjalankannya.
Skrip ini bisa digunakan untuk penyediaan otomatis karena skrip ini menggunakan kredensial admin mesin virtual lokal sebaris, bukan memanggil **Get-Credential** yang memerlukan interaksi pengguna.
Skrip ini mengasumsikan bahwa Anda sudah masuk ke akun Azure.
Anda bisa mengonfirmasi status masuk Anda dengan menggunakan cmdlet **Get-AzSubscription.**

### Contoh 3: Buat VM dari gambar marketplace tanpa IP Publik
```
$VMLocalAdminUser = "LocalAdminUser"
$VMLocalAdminSecurePassword = ConvertTo-SecureString <password> -AsPlainText -Force
$LocationName = "westus"
$ResourceGroupName = "MyResourceGroup"
$ComputerName = "MyVM"
$VMName = "MyVM"
$VMSize = "Standard_DS3"

$NetworkName = "MyNet"
$NICName = "MyNIC"
$SubnetName = "MySubnet"
$SubnetAddressPrefix = "10.0.0.0/24"
$VnetAddressPrefix = "10.0.0.0/16"

$SingleSubnet = New-AzVirtualNetworkSubnetConfig -Name $SubnetName -AddressPrefix $SubnetAddressPrefix
$Vnet = New-AzVirtualNetwork -Name $NetworkName -ResourceGroupName $ResourceGroupName -Location $LocationName -AddressPrefix $VnetAddressPrefix -Subnet $SingleSubnet
$NIC = New-AzNetworkInterface -Name $NICName -ResourceGroupName $ResourceGroupName -Location $LocationName -SubnetId $Vnet.Subnets[0].Id

$Credential = New-Object System.Management.Automation.PSCredential ($VMLocalAdminUser, $VMLocalAdminSecurePassword);

$VirtualMachine = New-AzVMConfig -VMName $VMName -VMSize $VMSize
$VirtualMachine = Set-AzVMOperatingSystem -VM $VirtualMachine -Windows -ComputerName $ComputerName -Credential $Credential -ProvisionVMAgent -EnableAutoUpdate
$VirtualMachine = Add-AzVMNetworkInterface -VM $VirtualMachine -Id $NIC.Id
$VirtualMachine = Set-AzVMSourceImage -VM $VirtualMachine -PublisherName 'MicrosoftWindowsServer' -Offer 'WindowsServer' -Skus '2012-R2-Datacenter' -Version latest

New-AzVM -ResourceGroupName $ResourceGroupName -Location $LocationName -VM $VirtualMachine -Verbose
```

Contoh ini menyediakan jaringan baru dan menggunakan VM Windows VM dari Marketplace tanpa membuat alamat IP publik atau Grup Keamanan Jaringan.
Skrip ini bisa digunakan untuk penyediaan otomatis karena skrip ini menggunakan kredensial admin mesin virtual lokal sebaris, bukan memanggil **Get-Credential** yang memerlukan interaksi pengguna.

## PARAMETERS

### -AddressPrefix
Prefiks alamat untuk jaringan virtual yang akan dibuat untuk VM.

```yaml
Type: System.String
Parameter Sets: SimpleParameterSet, DiskFileParameterSet
Aliases:

Required: False
Position: Named
Default value: 192.168.0.0/16
Accept pipeline input: False
Accept wildcard characters: False
```

### -AllocationMethod
Metode alokasi IP untuk IP publik yang akan dibuat untuk VM.

```yaml
Type: System.String
Parameter Sets: SimpleParameterSet, DiskFileParameterSet
Aliases:
Accepted values: Static, Dynamic

Required: False
Position: Named
Default value: Static
Accept pipeline input: False
Accept wildcard characters: False
```

### -AsJob
Jalankan cmdlet di latar belakang dan kembalikan Pekerjaan untuk melacak kemajuan.

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

### -AvailabilitySetName
Menentukan nama untuk kumpulan ketersediaan.

```yaml
Type: System.String
Parameter Sets: SimpleParameterSet, DiskFileParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Kredensial administrator VM.

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: SimpleParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DataDiskSizeInGb
Menentukan ukuran disk data di GB.

```yaml
Type: System.Int32[]
Parameter Sets: SimpleParameterSet, DiskFileParameterSet
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

### -DisableBginfoExtension
Menunjukkan bahwa cmdlet ini tidak menginstal ekstensi **Info BG** pada komputer virtual.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DefaultParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DiskFile
Jalur lokal ke file hard disk virtual yang akan diunggah ke awan dan untuk membuat VM, serta harus memiliki '.vhd' sebagai akhirannya.

```yaml
Type: System.String
Parameter Sets: DiskFileParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DomainNameLabel
Label subdomain untuk nama domain berkualifikasi penuh (FQDN, Fully-Qualified Domain Name) VM.  Ini akan mengambil formulir `{domainNameLabel}.{location}.cloudapp.azure.com` .

```yaml
Type: System.String
Parameter Sets: SimpleParameterSet, DiskFileParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableUltraSSD
Gunakan disk UltraSSD untuk vm.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SimpleParameterSet, DiskFileParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CtionPolicy
Kebijakan perlindungan untuk mesin virtual Azure Spot.  Nilai yang didukung adalah 'Deallocate' dan 'Delete'.

```yaml
Type: System.String
Parameter Sets: SimpleParameterSet, DiskFileParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HostGroupId
Menentukan grup host khusus tempat mesin virtual akan berada.

```yaml
Type: System.String
Parameter Sets: SimpleParameterSet, DiskFileParameterSet
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
Parameter Sets: SimpleParameterSet, DiskFileParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Image
Nama gambar yang mudah digunakan dan VM akan dibuat.  Termasuk: Win2016Datacenter, Win2012R2Datacenter, Win2012Datacenter, Win2008R2SP1, UbuntuLTS, CentOS, CoreOS, Debian, openSUSE-Leap, RHEL, SLES.

```yaml
Type: System.String
Parameter Sets: SimpleParameterSet
Aliases: ImageName

Required: False
Position: Named
Default value: Win2016Datacenter
Accept pipeline input: False
Accept wildcard characters: False
```

### -LicenseType
Menentukan tipe lisensi, yang menunjukkan bahwa gambar atau disk untuk komputer virtual tersebut berlisensi secara lokal.
Nilai ini hanya digunakan untuk gambar yang berisi Windows sistem operasi Server.
Nilai yang dapat diterima untuk parameter ini adalah:
- Windows_Client
- Windows_Server Nilai ini tidak dapat diperbarui.
Jika Anda menentukan parameter ini untuk pembaruan, nilai harus cocok dengan nilai awal untuk mesin virtual.

```yaml
Type: System.String
Parameter Sets: DefaultParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Linux
Menunjukkan apakah file disk tersebut adalah untuk Linux VM, jika ditentukan; atau Windows, jika tidak ditentukan secara default.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: DiskFileParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lokasi
Menentukan lokasi untuk mesin virtual.

```yaml
Type: System.String
Parameter Sets: SimpleParameterSet, DiskFileParameterSet
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: System.String
Parameter Sets: DefaultParameterSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxPrice
Harga maksimum tagihan mesin virtual berprioritas rendah.

```yaml
Type: System.Double
Parameter Sets: SimpleParameterSet, DiskFileParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EncryptionAtHost
Properti EncryptionAtHost dapat digunakan oleh pengguna dalam permintaan untuk mengaktifkan atau menonaktifkan Enkripsi Host untuk mesin virtual atau kumpulan skala mesin virtual. Cara ini akan mengaktifkan enkripsi untuk semua disk, termasuk disk Resource/Temp di host itu sendiri. Default: Enkripsi pada host akan dinonaktifkan kecuali properti ini diatur ke true untuk sumber daya.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SimpleParameterSet, DiskParameterSet
Aliases: 

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```


### -Nama
Nama sumber daya VM.

```yaml
Type: System.String
Parameter Sets: SimpleParameterSet, DiskFileParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OpenPorts
Daftar port yang terbuka pada grup keamanan jaringan (NSG) untuk VM yang dibuat.  Nilai default bergantung pada tipe gambar yang dipilih (misalnya, Windows: 3389, 5985 dan Linux: 22).

```yaml
Type: System.Int32[]
Parameter Sets: SimpleParameterSet, DiskFileParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Prioritas
Prioritas untuk mesin virtual.  Hanya nilai yang didukung adalah 'Reguler', 'Titik' dan 'Rendah'.
'Reguler' adalah untuk mesin virtual biasa.
'Titik' adalah untuk menemukan mesin virtual.
'Rendah' juga untuk mesin virtual titik tetapi diganti dengan 'Titik'. Harap gunakan 'Titik' dan bukan 'Rendah'.

```yaml
Type: System.String
Parameter Sets: SimpleParameterSet, DiskFileParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProximityPlacementGroupId
Id sumber daya dari Grup Penempatan Kedekatan untuk digunakan dengan mesin virtual ini.

```yaml
Type: System.String
Parameter Sets: SimpleParameterSet, DiskFileParameterSet
Aliases: ProximityPlacementGroup

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PublicIpAddressName
Nama alamat IP publik baru (atau yang sudah ada) agar VM yang dibuat dapat digunakan.  Jika tidak ditentukan, nama akan dihasilkan.

```yaml
Type: System.String
Parameter Sets: SimpleParameterSet, DiskFileParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: SimpleParameterSet, DiskFileParameterSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: System.String
Parameter Sets: DefaultParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SecurityGroupName
Nama grup keamanan jaringan (atau yang sudah ada) yang baru (NSG) agar VM yang dibuat dapat digunakan.  Jika tidak ditentukan, nama akan dihasilkan.

```yaml
Type: System.String
Parameter Sets: SimpleParameterSet, DiskFileParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Size
Ukuran Mesin Virtual.  Nilai Defaultnya adalah: Standard_DS1_v2.

```yaml
Type: System.String
Parameter Sets: SimpleParameterSet, DiskFileParameterSet
Aliases:

Required: False
Position: Named
Default value: Standard_DS1_v2
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubnetAddressPrefix
Prefiks alamat untuk subnet yang akan dibuat untuk VM.

```yaml
Type: System.String
Parameter Sets: SimpleParameterSet, DiskFileParameterSet
Aliases:

Required: False
Position: Named
Default value: 192.168.1.0/24
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubnetName
Nama subnet baru (atau yang sudah ada) agar VM yang dibuat dapat digunakan.  Jika tidak ditentukan, nama akan dihasilkan.

```yaml
Type: System.String
Parameter Sets: SimpleParameterSet, DiskFileParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SystemAssignedIdentity
Jika parameter ada, VM akan menetapkan identitas sistem terkelola yang dihasilkan secara otomatis.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SimpleParameterSet, DiskFileParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tag
Menentukan bahwa sumber daya dan grup sumber daya dapat ditandai dengan kumpulan pasangan nama nilai.
Menambahkan tag ke sumber daya memungkinkan Anda mengelompokkan sumber daya bersama-sama di seluruh grup sumber daya dan untuk membuat tampilan Anda sendiri.
Setiap grup sumber daya atau sumber daya dapat memiliki maksimal 15 tag.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: DefaultParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -UserAssignedIdentity
Nama identitas layanan terkelola yang harus ditetapkan pada VM.

```yaml
Type: System.String
Parameter Sets: SimpleParameterSet, DiskFileParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualNetworkName
Nama jaringan virtual baru (atau yang sudah ada) agar VM yang dibuat dapat digunakan.  Jika tidak ditentukan, nama akan dihasilkan.

```yaml
Type: System.String
Parameter Sets: SimpleParameterSet, DiskFileParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VM
Menentukan mesin virtual lokal untuk dibuat.
Untuk mendapatkan objek mesin virtual, gunakan cmdlet New-AzVMConfig.
Cmdlet lain bisa digunakan untuk mengonfigurasi mesin virtual, seperti Set-AzVMOperatingSystem, Set-AzVMSourceImage, dan Add-AzVMNetworkInterface.

```yaml
Type: Microsoft.Azure.Commands.Compute.Models.PSVirtualMachine
Parameter Sets: DefaultParameterSet
Aliases: VMProfile

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -VmssId
ID Kumpulan Skala Mesin Virtual yang akan dikaitkan dengan VM ini

```yaml
Type: System.String
Parameter Sets: SimpleParameterSet, DiskFileParameterSet
Aliases:
Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Zone
Menentukan daftar zona mesin virtual.

```yaml
Type: System.String[]
Parameter Sets: SimpleParameterSet
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

```yaml
Type: System.String[]
Parameter Sets: DefaultParameterSet
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak berjalan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUT

### System.String

### Microsoft.Azure.Commands.Compute.Models.PSVirtualMachine

### System.String[]

### System.Collections.Hashtable

## OUTPUT

### Microsoft.Azure.Commands.Compute.Models.PSAzureOperationResponse

### Microsoft.Azure.Commands.Compute.Models.PSVirtualMachine

## CATATAN

## LINK TERKAIT

[Get-azvm](./Get-AzVM.md)

[Remove-azvm](./Remove-AzVM.md)

[Mulai ulang-azvm](./Restart-AzVM.md)

[Start-azvm](./Start-AzVM.md)

[Stop-azvm](./Stop-AzVM.md)

[Update-azvm](./Update-AzVM.md)

[Add-AzvMDataDisk](./Add-AzVMDataDisk.md)

[Add-AzvMNetworkInterface](./Add-AzVMNetworkInterface.md)

[New-azvmConfig](./New-AzVMConfig.md)

[Set-AzvMOperatingSystem](./Set-AzVMOperatingSystem.md)

[Set-azvmSourceImage](./Set-AzVMSourceImage.md)

[Set-AzvMOSDisk](./Set-AzVMOSDisk.md)


