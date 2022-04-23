---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
ms.assetid: 05E6155D-4F0E-406B-9312-77AD97EF66EE
online version: https://docs.microsoft.com/powershell/module/az.compute/new-azvm
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/New-AzVM.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/New-AzVM.md
ms.openlocfilehash: 0208f72961cddbbe87c80b217090fd1044a6309b
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143187029"
---
# New-AzVM

## SYNOPSIS
Membuat mesin virtual.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.compute/new-azvm) untuk informasi terbaru.

## SYNTAX

### SimpleParameterSet (Default)
```
New-AzVM [[-ResourceGroupName] <String>] [[-Location] <String>] [-EdgeZone <String>] [[-Zone] <String[]>]
 -Name <String> -Credential <PSCredential> [-NetworkInterfaceDeleteOption <String>]
 [-VirtualNetworkName <String>] [-AddressPrefix <String>] [-SubnetName <String>]
 [-SubnetAddressPrefix <String>] [-PublicIpAddressName <String>] [-DomainNameLabel <String>]
 [-AllocationMethod <String>] [-SecurityGroupName <String>] [-OpenPorts <Int32[]>] [-Image <String>]
 [-Size <String>] [-AvailabilitySetName <String>] [-SystemAssignedIdentity] [-UserAssignedIdentity <String>]
 [-AsJob] [-OSDiskDeleteOption <String>] [-DataDiskSizeInGb <Int32[]>] [-DataDiskDeleteOption <String>]
 [-EnableUltraSSD] [-ProximityPlacementGroupId <String>] [-HostId <String>] [-VmssId <String>]
 [-Priority <String>] [-EvictionPolicy <String>] [-MaxPrice <Double>] [-EncryptionAtHost]
 [-HostGroupId <String>] [-SshKeyName <String>] [-GenerateSshKey] [-CapacityReservationGroupId <String>]
 [-UserData <String>] [-PlatformFaultDomain <Int32>] [-HibernationEnabled] [-vCPUCountAvailable <Int32>]
 [-vCPUCountPerCore <Int32>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### DefaultParameterSet
```
New-AzVM [-ResourceGroupName] <String> [-Location] <String> [-EdgeZone <String>] [-VM] <PSVirtualMachine>
 [[-Zone] <String[]>] [-DisableBginfoExtension] [-Tag <Hashtable>] [-LicenseType <String>] [-AsJob]
 [-OSDiskDeleteOption <String>] [-DataDiskDeleteOption <String>] [-SshKeyName <String>] [-GenerateSshKey]
 [-vCPUCountAvailable <Int32>] [-vCPUCountPerCore <Int32>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### DiskFileParameterSet
```
New-AzVM [[-ResourceGroupName] <String>] [[-Location] <String>] [-EdgeZone <String>] -Name <String>
 [-NetworkInterfaceDeleteOption <String>] [-VirtualNetworkName <String>] [-AddressPrefix <String>]
 [-SubnetName <String>] [-SubnetAddressPrefix <String>] [-PublicIpAddressName <String>]
 [-DomainNameLabel <String>] [-AllocationMethod <String>] [-SecurityGroupName <String>] [-OpenPorts <Int32[]>]
 -DiskFile <String> [-Linux] [-Size <String>] [-AvailabilitySetName <String>] [-SystemAssignedIdentity]
 [-UserAssignedIdentity <String>] [-AsJob] [-OSDiskDeleteOption <String>] [-DataDiskSizeInGb <Int32[]>]
 [-DataDiskDeleteOption <String>] [-EnableUltraSSD] [-ProximityPlacementGroupId <String>] [-HostId <String>]
 [-VmssId <String>] [-Priority <String>] [-EvictionPolicy <String>] [-MaxPrice <Double>] [-EncryptionAtHost]
 [-HostGroupId <String>] [-CapacityReservationGroupId <String>] [-UserData <String>]
 [-PlatformFaultDomain <Int32>] [-HibernationEnabled] [-vCPUCountAvailable <Int32>] [-vCPUCountPerCore <Int32>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzVM** membuat mesin virtual di Azure.
Cmdlet ini mengambil objek mesin virtual sebagai input.
Gunakan cmdlet New-AzVMConfig untuk membuat objek mesin virtual.
Cmdlet lain dapat digunakan untuk mengonfigurasi mesin virtual, seperti Set-AzVMOperatingSystem, Set-AzVMSourceImage, Add-AzVMNetworkInterface, dan Set-AzVMOSDisk.
The `SimpleParameterSet` provides a convenient method to create a VM by making common VM creation arguments opsional.

## EXAMPLES

### Contoh 1: Membuat mesin virtual
```powershell
New-AzVM -Name MyVm -Credential (Get-Credential)
```

```output
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
Skrip akan meminta nama pengguna dan kata sandi untuk VM.
Skrip ini menggunakan beberapa cmdlet lainnya.

### Contoh 2: Membuat mesin virtual dari gambar pengguna kustom
```powershell
## VM Account
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

Contoh ini mengambil gambar sistem operasi kustom yang sudah disiapkan dan disalurkan yang sudah ada dan melampirkan disk data ke dalamnya, menyediakan jaringan baru, menyebarkan VHD, dan menjalankannya.
Skrip ini bisa digunakan untuk penyediaan otomatis karena menggunakan kredensial admin mesin virtual lokal sebaris daripada memanggil **Get-Credential** yang memerlukan interaksi pengguna.
Skrip ini mengasumsikan bahwa Anda sudah masuk ke akun Azure Anda.
Anda dapat mengonfirmasi status masuk menggunakan cmdlet **Get-AzSubscription** .

### Contoh 3: Membuat VM dari gambar marketplace tanpa IP Publik
```powershell
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

### Contoh 4: Buat VM dengan nilai UserData:
```powershell
## VM Account
$VMLocalAdminUser = "LocalAdminUser";
$VMLocalAdminSecurePassword = ConvertTo-SecureString "Password" -AsPlainText -Force;

## Azure Account
$LocationName = "eastus";
$ResourceGroupName = "MyResourceGroup";

# VM Profile & Hardware
$VMName = 'v' + $ResourceGroupName;
$domainNameLabel = "d1" + $ResourceGroupName;
$Credential = New-Object System.Management.Automation.PSCredential ($VMLocalAdminUser, $VMLocalAdminSecurePassword);

# Create UserData value
$text = "text for UserData";
$bytes = [System.Text.Encoding]::Unicode.GetBytes($text);
$userData = [Convert]::ToBase64String($bytes);

# Create VM
New-AzVM -ResourceGroupName $ResourceGroupName -Name $VMName -Credential $cred -DomainNameLabel $domainNameLabel -UserData $userData;
$vm = Get-AzVM -ResourceGroupName $ResourceGroupName -Name $VMName -UserData;
```

Nilai UserData harus selalu dikodekan dengan Base64. 

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
Jalankan cmdlet di latar belakang dan kembalikan Job untuk melacak kemajuan.

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

### -CapacityReservationGroupId
Id grup reservasi kapasitas yang digunakan untuk mengalokasikan.

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

### -Kredensial
Kredensial administrator untuk VM.

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

### -DataDiskDeleteOption
Menentukan opsi penghapusan Disk Data setelah penghapusan VM. Opsi dilepas, Hapus

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

### -DataDiskSizeInGb
Menentukan ukuran disk data dalam GB.

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

### -DisableBginfoExtension
Menunjukkan bahwa cmdlet ini tidak menginstal ekstensi **Info BG** pada mesin virtual.

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
Jalur lokal ke file hard disk virtual untuk diunggah ke cloud dan untuk membuat VM, dan harus memiliki '.vhd' sebagai akhirannya.

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
Label subdomain untuk nama domain yang sepenuhnya memenuhi syarat (FQDN) VM.  Ini akan mengambil formulir `{domainNameLabel}.{location}.cloudapp.azure.com`.

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

### -EdgeZone
Mengatur nama zona tepi. Jika diatur, kueri akan dirutekan ke zona tepi yang ditentukan, bukan kawasan utama.

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

### -EnableUltrassd
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

### -EncryptionAtHost
Properti EncryptionAtHost dapat digunakan oleh pengguna dalam permintaan untuk mengaktifkan atau menonaktifkan Enkripsi Host untuk mesin virtual atau kumpulan skala mesin virtual. Ini akan mengaktifkan enkripsi untuk semua disk termasuk disk Sumber Daya/Temp di host itu sendiri. Default: Enkripsi di host akan dinonaktifkan kecuali properti ini diatur ke true untuk sumber daya.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SimpleParameterSet, DiskFileParameterSet
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
Parameter Sets: SimpleParameterSet, DiskFileParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -GenerateSshKey
Buat pasangan kunci Publik/Privat SSH dan buat sumber daya Kunci Publik SSH di Azure.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SimpleParameterSet, DefaultParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HibernationEnabled
Bendera yang mengaktifkan atau menonaktifkan kapabilitas hibernasi pada VM.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SimpleParameterSet, DiskFileParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -HostGroupId
Menentukan grup host khusus tempat mesin virtual berada.

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
Id dari Host

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

### -Gambar
Nama gambar yang mudah dikenali di mana VM akan dibuat.  Ini termasuk: Win2019Datacenter, Win2016Datacenter, Win2012R2Datacenter, Win2012Datacenter, Win2008R2SP1, UbuntuLTS, CentOS, CoreOS, Debian, openSUSE-Leap, RHEL, SLES.

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
Menentukan tipe lisensi, yang menunjukkan bahwa gambar atau disk untuk mesin virtual telah dilisensikan di tempat.
Nilai yang memungkinkan untuk Windows Server adalah:
- Windows_Client
- Windows_Server Kemungkinan nilai untuk sistem operasi Linux Server adalah: 
- RHEL_BYOS (untuk RHEL) 
- SLES_BYOS (untuk SUSE) 

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
Menunjukkan apakah file disk untuk Linux VM, jika ditentukan; atau Windows, jika tidak ditentukan secara default.

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
Menentukan lokasi untuk mesin maya.

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
Harga maksimal penagihan mesin virtual prioritas rendah.

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

### -NetworkInterfaceDeleteOption
Menentukan tindakan apa yang harus dilakukan pada sumber daya NetworkInterface ketika VM dihapus. Opsinya adalah: Lepaskan, Hapus.

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

### -OpenPorts
Daftar port yang akan dibuka di grup keamanan jaringan (NSG) untuk VM yang dibuat.  Nilai default tergantung pada tipe gambar yang dipilih (misalnya, Windows: 3389, 5985 dan Linux: 22).

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

### -OSDiskDeleteOption
Menentukan opsi penghapusan Disk OS setelah penghapusan VM. Opsi dilepas, Hapus

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

### -PlatformFaultDomain
Menentukan domain kesalahan mesin virtual.

```yaml
Type: System.Int32
Parameter Sets: SimpleParameterSet, DiskFileParameterSet
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
Nama alamat IP publik baru (atau yang sudah ada) untuk digunakan VM yang dibuat.  Jika tidak ditentukan, nama akan dibuat.

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
Nama grup keamanan jaringan (atau yang sudah ada) baru (atau yang sudah ada) untuk digunakan VM yang dibuat.  Jika tidak ditentukan, nama akan dibuat.

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
Ukuran Mesin Virtual.  Nilai Default adalah: Standard_D2s_v3.

```yaml
Type: System.String
Parameter Sets: SimpleParameterSet, DiskFileParameterSet
Aliases:

Required: False
Position: Named
Default value: Standard_D2s_v3
Accept pipeline input: False
Accept wildcard characters: False
```

### -SshKeyName
Nama sumber daya Kunci Publik SSH.

```yaml
Type: System.String
Parameter Sets: SimpleParameterSet, DefaultParameterSet
Aliases:

Required: False
Position: Named
Default value: None
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
Nama subnet baru (atau yang sudah ada) untuk digunakan VM yang dibuat.  Jika tidak ditentukan, nama akan dibuat.

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
Jika parameter ada, maka VM ditetapkan identitas sistem terkelola yang dihasilkan secara otomatis.

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
Menentukan bahwa sumber daya dan grup sumber daya bisa ditandai dengan sekumpulan pasangan nilai nama.
Menambahkan tag ke sumber daya memungkinkan Anda mengelompokkan sumber daya bersama di seluruh grup sumber daya dan membuat tampilan Anda sendiri.
Setiap sumber daya atau grup sumber daya dapat memiliki maksimal 15 tag.

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
Nama identitas layanan terkelola yang harus ditetapkan ke VM.

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

### -UserData
UserData untuk VM, yang akan dikodekan basis 64. Pelanggan tidak boleh memberikan rahasia apa pun di sini.

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

### -vCPUCountAvailable
Menentukan jumlah vCPU yang tersedia untuk VM. Ketika properti ini tidak ditentukan dalam isi permintaan, perilaku defaultnya adalah mengaturnya ke nilai vCPU yang tersedia untuk ukuran VM yang diekspos dalam respons api [dari Daftar semua ukuran mesin virtual yang tersedia di suatu kawasan](https://docs.microsoft.com/en-us/rest/api/compute/resource-skus/list).

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
Menentukan vCPU untuk rasio inti fisik. Ketika properti ini tidak ditentukan dalam isi permintaan, perilaku default diatur ke nilai vCPUsPerCore untuk Ukuran VM yang diekspos dalam respons api dari [Daftar semua ukuran mesin virtual yang tersedia di suatu kawasan](https://docs.microsoft.com/en-us/rest/api/compute/resource-skus/list). Mengatur properti ini ke 1 juga berarti hyper-threading dinonaktifkan.

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

### -VirtualNetworkName
Nama jaringan virtual baru (atau yang sudah ada) untuk digunakan VM yang dibuat.  Jika tidak ditentukan, nama akan dibuat.

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
Cmdlet lain dapat digunakan untuk mengonfigurasi mesin virtual, seperti Set-AzVMOperatingSystem, Set-AzVMSourceImage, dan Add-AzVMNetworkInterface.

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

### -Zona
Menentukan daftar zona mesin maya.

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
Meminta konfirmasi sebelum menjalankan cmdlet.

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
Cmdlet tidak dijalankan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Azure.Commands.Compute.Models.PSVirtualMachine

### System.String[]

### System.Collections.Hashtable

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Models.PSAzureOperationResponse

### Microsoft.Azure.Commands.Compute.Models.PSVirtualMachine

## NOTES

## RELATED LINKS

[Get-AzVM](./Get-AzVM.md)

[Hapus-AzVM](./Remove-AzVM.md)

[Mulai ulang-AzVM](./Restart-AzVM.md)

[Start-AzVM](./Start-AzVM.md)

[Stop-AzVM](./Stop-AzVM.md)

[Perbarui-AzVM](./Update-AzVM.md)

[Add-AzVMDataDisk](./Add-AzVMDataDisk.md)

[Add-AzVMNetworkInterface](./Add-AzVMNetworkInterface.md)

[New-AzVMConfig](./New-AzVMConfig.md)

[Set-AzVMOperatingSystem](./Set-AzVMOperatingSystem.md)

[Set-AzVMSourceImage](./Set-AzVMSourceImage.md)

[Set-AzVMOSDisk](./Set-AzVMOSDisk.md)


