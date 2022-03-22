---
title: Mulai menggunakan Azure PowerShell
description: 'Pelajari selengkapnya tentang: Memulai dengan Azure PowerShell'
ms.devlang: powershell
ms.topic: conceptual
ms.date: 11/15/2017
ms.custom: devx-track-azurepowershell
ms.openlocfilehash: 5fe6eb0ef2a0ab993474bee35f678c5454d4d368
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: HT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132425051"
---
# <a name="get-started-with-azure-powershell"></a>Mulai menggunakan Azure PowerShell

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

Azure PowerShell dirancang untuk mengelola dan menata sumber daya Azure dari baris perintah, dan untuk membangun skrip otomatisasi yang berfungsi melawan Azure Resource Manager. Anda dapat menggunakannya di browser Anda dengan [Azure Cloud Shell](/azure/cloud-shell/overview) atau Anda dapat menginstalnya di komputer lokal Anda. Artikel ini membantu Anda memulai dengan Azure PowerShell dan mengajarkan konsep inti di baliknya.

## <a name="install-azure-powershell"></a>Memasang Azure PowerShell

Langkah pertama adalah memastikan Anda menginstal versi terbaru Azure PowerShell. Untuk informasi tentang rilis terbaru, lihat [catatan rilis](./release-notes-azureps.md).

1. [Instal Azure PowerShell](install-azurerm-ps.md).

2. Untuk memverifikasi penginstalan berhasil, jalankan `Get-InstalledModule AzureRM -AllVersions` dari baris perintah Anda.

## <a name="azure-cloud-shell"></a>Azure Cloud Shell

Cara termudah untuk memulai adalah dengan [meluncurkan Cloud Shell](/azure/cloud-shell/quickstart).

1. Luncurkan Cloud Shell dari navigasi atas portal Microsoft Azure.

   ![Ikon Shell](~/media/get-started-azureps/shell-icon.png)

2. Pilih langganan yang ingin Anda gunakan dan buat akun penyimpanan.

   ![Buat akun penyimpanan](~/media/get-started-azureps/storage-prompt.png)

Setelah penyimpanan Anda dibuat, Cloud Shell akan membuka sesi PowerShell di browser.

![Cloud Shell untuk PowerShell](~/media/get-started-azureps/cloud-powershell.png)

Anda juga dapat menginstal Azure PowerShell dan menggunakannya secara lokal di sesi PowerShell.

## <a name="sign-in-to-azure"></a>Masuk ke Azure

Masuk secara interaktif:

1. Ketik `Connect-AzureRmAccount`. Anda akan mendapatkan kotak dialog yang meminta info masuk Azure Anda. Opsi'-Lingkungan' dapat memungkinkan Anda masuk ke Azure Tiongkok atau Azure Jerman.

   e.g. Connect-AzureRmAccount -Environment AzureChinaCloud

2. Ketik alamat email dan kata sandi yang terkait dengan akun Anda. Azure mengautentikasi dan menyimpan informasi info masuk, lalu menutup jendela.

Setelah masuk ke akun Azure, Anda dapat menggunakan cmdlet Azure PowerShell untuk mengakses dan pengelola sumber daya dalam langganan Anda.

## <a name="create-a-windows-virtual-machine-using-simple-defaults"></a>Membuat mesin virtual Windows menggunakan default sederhana

Cmdlet `New-AzureRmVM` menyediakan sintaks yang disederhanakan yang memudahkan pembuatan mesin virtual baru. Hanya terdapat dua nilai parameter yang harus Anda sediakan: nama VM dan set informasi masuk untuk akun administrator lokal di VM.

Pertama, buat objek informasi masuk.

```azurepowershell-interactive
$cred = Get-Credential -Message "Enter a username and password for the virtual machine."
```

```output
Windows PowerShell credential request.
Enter a username and password for the virtual machine.
User: localAdmin
Password for user localAdmin: *********
```

Selanjutnya, Buat VM.

```azurepowershell-interactive
New-AzureRmVM -Name SampleVM -Credential $cred
```

```output
ResourceGroupName        : SampleVM
Id                       : /subscriptions/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX/resourceGroups/SampleVM/providers/Microsoft.Compute/virtualMachines/SampleVM
VmId                     : 43f6275d-ce50-49c8-a831-5d5974006e63
Name                     : SampleVM
Type                     : Microsoft.Compute/virtualMachines
Location                 : eastus
Tags                     : {}
HardwareProfile          : {VmSize}
NetworkProfile           : {NetworkInterfaces}
OSProfile                : {ComputerName, AdminUsername, WindowsConfiguration, Secrets}
ProvisioningState        : Succeeded
StorageProfile           : {ImageReference, OsDisk, DataDisks}
FullyQualifiedDomainName : samplevm-2c0867.eastus.cloudapp.azure.com
```

Ini mudah. Tetapi, Anda mungkin bertanya-tanya apa lagi yang dibuat dan bagaimana cara VM dikonfigurasi. Pertama, mari kita lihat grup sumber daya.

```azurepowershell-interactive
Get-AzureRmResourceGroup | Select-Object ResourceGroupName,Location
```

```output
ResourceGroupName          Location
-----------------          --------
cloud-shell-storage-westus westus
SampleVM                   eastus
```

Grup sumber daya **cloud-shell-storage-westus** dibuat saat pertama kali Anda menggunakan Cloud Shell. Grup sumber daya **SampleVM** dibuat dengan cmdlet `New-AzureRmVM`.

Sekarang, sumber daya apa lagi yang dibuat di grup sumber daya baru ini?

```azurepowershell-interactive
Get-AzureRmResource |
  Where ResourceGroupName -eq SampleVM |
    Select-Object ResourceGroupName,Location,ResourceType,Name
```

```output
ResourceGroupName          Location ResourceType                            Name
-----------------          -------- ------------                            ----
SAMPLEVM                   eastus   Microsoft.Compute/disks                 SampleVM_OsDisk_1_9b286c54b168457fa1f8c47...
SampleVM                   eastus   Microsoft.Compute/virtualMachines       SampleVM
SampleVM                   eastus   Microsoft.Network/networkInterfaces     SampleVM
SampleVM                   eastus   Microsoft.Network/networkSecurityGroups SampleVM
SampleVM                   eastus   Microsoft.Network/publicIPAddresses     SampleVM
SampleVM                   eastus   Microsoft.Network/virtualNetworks       SampleVM
```

Mari kita cari detail selengkapnya tentang VM. Contoh ini menunjukkan cara mengambil informasi tentang Citra OS yang digunakan untuk membuat VM.

```azurepowershell-interactive
Get-AzureRmVM -Name SampleVM -ResourceGroupName SampleVM |
  Select-Object -ExpandProperty StorageProfile |
    Select-Object -ExpandProperty ImageReference
```

```output
Publisher : MicrosoftWindowsServer
Offer     : WindowsServer
Sku       : 2016-Datacenter
Version   : latest
Id        :
```

## <a name="create-a-fully-configured-linux-virtual-machine"></a>Membuat Mesin Virtual Linux yang dikonfigurasi sepenuhnya

Contoh sebelumnya menggunakan sintaks yang disederhanakan dan nilai parameter default untuk membuat mesin virtual Windows. Dalam contoh ini, kami menyediakan nilai untuk semua opsi mesin virtual.

### <a name="create-a-resource-group"></a>Buat grup sumber daya

Untuk contoh ini kami ingin membuat Grup Sumber Daya. Grup Sumber Daya di Azure menyediakan cara untuk mengelola beberapa sumber daya yang ingin Anda kelompokkan secara logis bersama. Misalnya, Anda dapat membuat Grup Sumber Daya untuk aplikasi atau proyek dan menambahkan mesin virtual, database, dan layanan CDN di dalamnya.

Mari kita buat grup sumber daya bernama "MyResourceGroup" di wilayah westeurope Azure. Untuk melakukannya, ketikkan perintah berikut:

```azurepowershell-interactive
New-AzureRmResourceGroup -Name 'myResourceGroup' -Location 'westeurope'
```

```output
ResourceGroupName : myResourceGroup
Location          : westeurope
ProvisioningState : Succeeded
Tags              :
ResourceId        : /subscriptions/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX/resourceGroups/myResourceGroup
```

Grup sumber daya baru ini akan digunakan untuk berisi semua sumber daya yang diperlukan untuk VM baru yang kami buat. Untuk membuat VM Linux baru, pertama-tama kita harus membuat sumber daya lain yang diperlukan dan menetapkannya ke konfigurasi. Kemudian kita dapat menggunakan konfigurasi tersebut untuk membuat VM. Selain itu, Anda harus memiliki kunci publik SSH bernama `id_rsa.pub` di direktori .ssh profil pengguna Anda.

#### <a name="create-the-required-network-resources"></a>Membuat sumber daya jaringan yang diperlukan

Pertama-tama, kita perlu membuat konfigurasi subnet untuk digunakan dengan proses pembuatan jaringan virtual. Kita juga membuat alamat IP publik sehingga dapat terhubung ke VM ini. Kita membuat kelompok keamanan jaringan untuk mengamankan akses ke alamat publik. Terakhir, kita membuat NIC virtual menggunakan semua sumber daya sebelumnya.

```azurepowershell-interactive
# Variables for common values
$resourceGroup = "myResourceGroup"
$location = "westeurope"
$vmName = "myLinuxVM"

# Definer user name and blank password
$securePassword = ConvertTo-SecureString 'azurepassword' -AsPlainText -Force
$cred = New-Object System.Management.Automation.PSCredential ("azureuser", $securePassword)

# Create a subnet configuration
$subnetConfig = New-AzureRmVirtualNetworkSubnetConfig -Name mySubnet2 -AddressPrefix 192.168.2.0/24

# Create a virtual network
$vnet = New-AzureRmVirtualNetwork -ResourceGroupName $resourceGroup -Location $location `
  -Name MYvNET2 -AddressPrefix 192.168.0.0/16 -Subnet $subnetConfig

# Create a public IP address and specify a DNS name
$publicIp = New-AzureRmPublicIpAddress -ResourceGroupName $resourceGroup -Location $location `
  -Name "mypublicdns$(Get-Random)" -AllocationMethod Static -IdleTimeoutInMinutes 4
$publicIp | Select-Object Name,IpAddress

# Create an inbound network security group rule for port 22
$nsgRuleSSH = New-AzureRmNetworkSecurityRuleConfig -Name myNetworkSecurityGroupRuleSSH  -Protocol Tcp `
  -Direction Inbound -Priority 1000 -SourceAddressPrefix * -SourcePortRange * -DestinationAddressPrefix * `
  -DestinationPortRange 22 -Access Allow

# Create a network security group
$nsg = New-AzureRmNetworkSecurityGroup -ResourceGroupName $resourceGroup -Location $location `
  -Name myNetworkSecurityGroup2 -SecurityRules $nsgRuleSSH

# Create a virtual network card and associate with public IP address and NSG
$nic = New-AzureRmNetworkInterface -Name myNic2 -ResourceGroupName $resourceGroup -Location $location `
  -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $publicIp.Id -NetworkSecurityGroupId $nsg.Id
```

### <a name="create-the-vm-configuration"></a>Membuat konfigurasi VM

Sekarang, kita memiliki sumber daya yang diperlukan untuk dapat membuat objek konfigurasi VM.

```azurepowershell-interactive
# Create a virtual machine configuration
$vmConfig = New-AzureRmVMConfig -VMName $vmName -VMSize Standard_D1 |
  Set-AzureRmVMOperatingSystem -Linux -ComputerName $vmName -Credential $cred -DisablePasswordAuthentication |
  Set-AzureRmVMSourceImage -PublisherName Canonical -Offer UbuntuServer -Skus 14.04.2-LTS -Version latest |
  Add-AzureRmVMNetworkInterface -Id $nic.Id

# Configure SSH Keys
$sshPublicKey = Get-Content -Raw "$env:USERPROFILE\.ssh\id_rsa.pub"
Add-AzureRmVMSshPublicKey -VM $vmConfig -KeyData $sshPublicKey -Path "/home/azureuser/.ssh/authorized_keys"
```

### <a name="create-the-virtual-machine"></a>Membuat komputer virtual

Sekarang kita dapat membuat VM menggunakan objek konfigurasi VM.

```azurepowershell-interactive
New-AzureRmVM -ResourceGroupName $resourceGroup -Location $location -VM $vmConfig
```

Sekarang VM telah dibuat, Anda dapat masuk ke VM Linux baru menggunakan SSH dengan alamat IP publik VM yang Anda buat:

```bash
ssh xx.xxx.xxx.xxx
```

```output
Welcome to Ubuntu 14.04.4 LTS (GNU/Linux 3.19.0-65-generic x86_64)

 * Documentation:  https://help.ubuntu.com/

  System information as of Sun Feb 19 00:32:28 UTC 2017

  System load: 0.31              Memory usage: 3%   Processes:       89
  Usage of /:  39.6% of 1.94GB   Swap usage:   0%   Users logged in: 0

  Graph this data and manage this system at:
    https://landscape.canonical.com/

  Get cloud support with Ubuntu Advantage Cloud Guest:
    http://www.ubuntu.com/business/services/cloud

0 packages can be updated.
0 updates are security updates.



The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.

my-login@MyLinuxVM:../../..$
```

## <a name="creating-other-resources-in-azure"></a>Membuat sumber daya lain di Azure

Kita sekarang telah menelusuri cara membuat Grup Sumber Daya, VM Linux, dan VM Server Windows. Anda juga dapat membuat banyak jenis sumber daya Azure lainnya.

Misalnya, untuk membuat Azure Network Load Balancer yang kemudian dapat kita kaitkan dengan VM yang baru dibuat, kita dapat menggunakan perintah buat berikut:

```azurepowershell-interactive
New-AzureRmLoadBalancer -Name MyLoadBalancer -ResourceGroupName myResourceGroup -Location westeurope
```

Kita juga dapat membuat Virtual Network privat baru (biasa disebut sebagai "VNet" dalam Azure) untuk infrastruktur menggunakan perintah berikut:

```azurepowershell-interactive
$subnetConfig = New-AzureRmVirtualNetworkSubnetConfig -Name mySubnet2 -AddressPrefix 10.0.0.0/16
$vnet = New-AzureRmVirtualNetwork -ResourceGroupName myResourceGroup -Location westeurope `
  -Name MYvNET3 -AddressPrefix 10.0.0.0/16 -Subnet $subnetConfig
```

Apa yang membuat Azure dan Azure PowerShell kuat adalah kita dapat menggunakannya tidak hanya untuk mendapatkan infrastruktur berbasis cloud tetapi juga untuk membuat layanan platform terkelola. Layanan platform terkelola juga dapat dikombinasikan dengan infrastruktur untuk membangun solusi yang lebih kuat.

Misalnya, Anda dapat menggunakan Azure PowerShell untuk membuat Azure AppService. Azure AppService adalah layanan platform terkelola yang menyediakan cara hebat untuk menghosting aplikasi web tanpa harus khawatir tentang infrastruktur. Setelah membuat Azure AppService, Anda dapat membuat dua Azure Web Apps baru dalam AppService menggunakan perintah berikut:

```azurepowershell-interactive
# Create an Azure AppService that we can host any number of web apps within
New-AzureRmAppServicePlan -Name MyAppServicePlan -Tier Basic -NumberofWorkers 2 -WorkerSize Small -ResourceGroupName myResourceGroup -Location westeurope

# Create Two Web Apps within the AppService (note: name param must be a unique DNS entry)
New-AzureRmWebApp -Name MyWebApp43432 -AppServicePlan MyAppServicePlan -ResourceGroupName myResourceGroup -Location westeurope
New-AzureRmWebApp -Name MyWebApp43433 -AppServicePlan MyAppServicePlan -ResourceGroupName myResourceGroup -Location westeurope
```

## <a name="listing-deployed-resources"></a>Mencantumkan sumber daya yang disebarkan

Anda dapat menggunakan cmdlet `Get-AzureRmResource` untuk mencantumkan sumber daya yang berjalan di Azure. Contoh berikut menunjukkan sumber daya yang baru saja kita buat di grup sumber daya baru.

```azurepowershell-interactive
Get-AzureRmResource |
  Where-Object ResourceGroupName -eq myResourceGroup |
    Select-Object Name,Location,ResourceType
```

```output
Name                                                  Location   ResourceType
----                                                  --------   ------------
myLinuxVM_OsDisk_1_36ca038791f642ba91270879088c249a   westeurope Microsoft.Compute/disks
myWindowsVM_OsDisk_1_f627e6e2bb454c72897d72e9632adf9a westeurope Microsoft.Compute/disks
myLinuxVM                                             westeurope Microsoft.Compute/virtualMachines
myWindowsVM                                           westeurope Microsoft.Compute/virtualMachines
myWindowsVM/BGInfo                                    westeurope Microsoft.Compute/virtualMachines/extensions
myNic1                                                westeurope Microsoft.Network/networkInterfaces
myNic2                                                westeurope Microsoft.Network/networkInterfaces
myNetworkSecurityGroup1                               westeurope Microsoft.Network/networkSecurityGroups
myNetworkSecurityGroup2                               westeurope Microsoft.Network/networkSecurityGroups
mypublicdns245369171                                  westeurope Microsoft.Network/publicIPAddresses
mypublicdns779537141                                  westeurope Microsoft.Network/publicIPAddresses
MYvNET1                                               westeurope Microsoft.Network/virtualNetworks
MYvNET2                                               westeurope Microsoft.Network/virtualNetworks
micromyresomywi032907510                              westeurope Microsoft.Storage/storageAccounts
```

## <a name="deleting-resources"></a>Menghapus sumber daya

Untuk menghapus akun Azure Anda, Anda akan menghapus sumber daya yang kita buat dalam contoh ini. Anda dapat menggunakan cmdlet `Remove-AzureRm*` untuk menghapus sumber daya yang tidak lagi Anda butuhkan. Untuk menghapus VM Windows yang kita buat, menggunakan perintah berikut:

```azurepowershell-interactive
Remove-AzureRmVM -Name myWindowsVM -ResourceGroupName myResourceGroup
```

Anda akan diminta untuk mengonfirmasi bahwa Anda ingin menghapus sumber daya.

```output
Confirm
Are you sure you want to remove resource group 'myResourceGroup'
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): Y
```

Anda juga dapat menggunakan hapus banyak sumber daya sekaligus. Misalnya, perintah berikut menghapus semua grup sumber daya "MyResourceGroup" yang telah kita gunakan untuk semua sampel dalam tutorial Memulai ini. Ini menghapus grup sumber daya dan semua sumber daya di dalamnya.

```azurepowershell-interactive
Remove-AzureRmResourceGroup -Name myResourceGroup
```

```output
Confirm
Are you sure you want to remove resource group 'myResourceGroup'
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): Y
```

Proses ini bisa memerlukan waktu beberapa menit.

## <a name="get-samples"></a>Mendapatkan sampel

Untuk mempelajari lebih lanjut tentang cara menggunakan Azure PowerShell, lihat skrip kami yang paling umum untuk [VM Linux](/azure/virtual-machines/linux/powershell-samples?toc=%2fpowershell%2fazure%%2ftoc.json), [VM Windows](/azure/virtual-machines/windows/powershell-samples?toc=%2fpowershell%2fazure%%2ftoc.json), [Aplikasi Web](/azure/app-service-web/app-service-powershell-samples?toc=%2fpowershell%2fazure%%2ftoc.json), dan [Database SQL](/azure/sql-database/sql-database-powershell-samples?toc=%2fpowershell%2fazure%%2ftoc.json).

## <a name="next-steps"></a>Langkah berikutnya

* [Masuk dengan Azure PowerShell](authenticate-azureps.md)
* [Mengelola langganan Azure dengan Azure PowerShell](manage-subscriptions-azureps.md)
* [Membuat perwakilan layanan di Azure menggunakan Azure PowerShell](create-azure-service-principal-azureps.md)
* Baca [Catatan rilis](./release-notes-azureps.md) tentang migrasi dari rilis yang lebih lama.
* Mendapatkan bantuan dari komunitas:
  * [Forum Azure di MSDN](https://go.microsoft.com/fwlink/p/?LinkId=320212)
  * [stackoverflow](https://go.microsoft.com/fwlink/?LinkId=320213)
