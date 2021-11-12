---
title: Mulai menggunakan Azure PowerShell | Microsoft Docs
description: 'Pelajari selengkapnya tentang: Mulai menggunakan Azure PowerShell'
ms.devlang: powershell
ms.topic: conceptual
ms.date: 11/15/2017
ms.custom: devx-track-azurepowershell
ms.openlocfilehash: 78f8217bf9fefba37dc1f9d11d9331ac3a7170d9
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132428303"
---
# <a name="getting-started-with-azure-powershell"></a>Mulai menggunakan Azure PowerShell

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

Azure PowerShell dirancang untuk mengelola dan mengelola sumber daya Azure dari baris perintah, dan untuk membuat skrip otomatisasi yang bekerja dengan Azure Resource Manager. Anda dapat menggunakannya di browser dengan [Azure Cloud Shell](/azure/cloud-shell/overview), atau menginstalnya di komputer lokal lalu menggunakannya di sesi PowerShell apa pun. Artikel ini membantu agar Anda mulai menggunakannya, dan mengajari Anda konsep inti di baliknya.

## <a name="connect"></a>Koneksi

Cara termudah untuk memulai adalah dengan [meluncurkan Cloud Shell](/azure/cloud-shell/quickstart).

1. Luncurkan Cloud Shell dari navigasi atas portal Azure.

   ![Ikon Shell](~/media/get-started-azureps/shell-icon.png)

2. Pilih langganan yang ingin Anda gunakan dan buat akun penyimpanan.

   ![Membuat akun penyimpanan](~/media/get-started-azureps/storage-prompt.png)

Setelah penyimpanan dibuat, Cloud Shell akan membuka sesi PowerShell di browser.

![Cloud Shell untuk PowerShell](~/media/get-started-azureps/cloud-powershell.png)

Anda juga dapat menginstal Azure PowerShell menggunakannya secara lokal dalam sesi PowerShell.

## <a name="install-azure-powershell"></a>Menginstal Azure PowerShell

Langkah pertama adalah memastikan Anda memiliki versi terbaru Azure PowerShell diinstal. Untuk informasi tentang rilis terbaru, lihat [catatan rilis](./release-notes-azureps.md).

1. [Instal Azure PowerShell](install-azurerm-ps.md).

2. Untuk memastikan bahwa penginstalan berhasil, jalankan `Get-InstalledModule AzureRM -AllVersions` dari baris perintah Anda.

## <a name="sign-in-to-azure"></a>Masuk ke Azure

Masuk secara interaktif:

1. Ketik `Login-AzureRmAccount` . Anda akan mendapatkan kotak dialog yang meminta kredensial Azure Anda. Opsi '-EnvironmentName' dapat memungkinkan Anda mengautentikasi untuk Azure China atau Azure Germany.

   misalnya Login-AzureRmAccount -EnvironmentName AzureChinaCloud

2. Ketik alamat email dan kata sandi yang terkait dengan akun Anda. Azure mengautentikasi dan menyimpan informasi kredensial, lalu menutup jendela.

Setelah masuk ke akun Azure, Anda dapat menggunakan cmdlet Azure PowerShell untuk mengakses dan manajer sumber daya dalam langganan.

## <a name="create-a-resource-group"></a>Membuat grup sumber daya

Sekarang setelah semuanya sudah disiapkan, mari kita gunakan aplikasi Azure PowerShell sumber daya dalam Azure.

Pertama, buat Grup Sumber Daya. Grup Sumber Daya di Azure menyediakan cara untuk mengelola beberapa sumber daya yang ingin dikelompokkan secara logis. Misalnya, Anda mungkin membuat Grup Sumber Daya untuk aplikasi atau proyek dan menambahkan mesin virtual, database, dan CDN di dalamnya.

Mari kita buat grup sumber daya bernama "MyResourceGroup" di kawasan westeurope, Azure. Untuk melakukannya ketikkan perintah berikut ini:

```powershell-interactive
New-AzureRmResourceGroup -Name 'myResourceGroup' -Location 'westeurope'
```

```Output
ResourceGroupName : myResourceGroup
Location          : westeurope
ProvisioningState : Succeeded
Tags              :
ResourceId        : /subscriptions/XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX/resourceGroups/myResourceGroup
```

## <a name="create-a-windows-virtual-machine"></a>Membuat Windows Virtual

Setelah kami memiliki grup sumber daya, mari kita buat VM Windows di dalamnya. Untuk membuat VM baru, kami harus terlebih dahulu membuat sumber daya lain yang diperlukan dan menetapkannya pada konfigurasi. Lalu, kami dapat menggunakan konfigurasi tersebut untuk membuat VM.

### <a name="create-the-required-network-resources"></a>Membuat sumber daya jaringan yang diperlukan

Pertama, kita perlu membuat konfigurasi subnet untuk digunakan dengan proses pembuatan jaringan virtual. Kami juga membuat alamat IP publik sehingga kami dapat terhubung ke VM ini. Kami membuat grup keamanan jaringan untuk mengamankan akses ke alamat publik. Akhirnya kami membuat NIC virtual menggunakan semua sumber daya sebelumnya.

```powershell-interactive
# Variables for common values
$resourceGroup = "myResourceGroup"
$location = "westeurope"
$vmName = "myWindowsVM"

# Create a subnet configuration
$subnetConfig = New-AzureRmVirtualNetworkSubnetConfig -Name mySubnet1 -AddressPrefix 192.168.1.0/24

# Create a virtual network
$vnet = New-AzureRmVirtualNetwork -ResourceGroupName $resourceGroup -Location $location `
  -Name MYvNET1 -AddressPrefix 192.168.0.0/16 -Subnet $subnetConfig

# Create a public IP address and specify a DNS name
$publicIp = New-AzureRmPublicIpAddress -ResourceGroupName $resourceGroup -Location $location `
  -Name "mypublicdns$(Get-Random)" -AllocationMethod Static -IdleTimeoutInMinutes 4
$publicIp | Select-Object Name,IpAddress

# Create an inbound network security group rule for port 3389
$nsgRuleRDP = New-AzureRmNetworkSecurityRuleConfig -Name myNetworkSecurityGroupRuleRDP  -Protocol Tcp `
  -Direction Inbound -Priority 1000 -SourceAddressPrefix * -SourcePortRange * -DestinationAddressPrefix * `
  -DestinationPortRange 3389 -Access Allow

# Create a network security group
$nsg = New-AzureRmNetworkSecurityGroup -ResourceGroupName $resourceGroup -Location $location `
  -Name myNetworkSecurityGroup1 -SecurityRules $nsgRuleRDP

# Create a virtual network card and associate with public IP address and NSG
$nic = New-AzureRmNetworkInterface -Name myNic1 -ResourceGroupName $resourceGroup -Location $location `
  -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $publicIp.Id -NetworkSecurityGroupId $nsg.Id
```

### <a name="create-the-virtual-machine"></a>Membuat mesin virtual

Pertama, kita memerlukan serangkaian kredensial untuk OS.

```powershell-interactive
# Create user object
$cred = Get-Credential -Message "Enter a username and password for the virtual machine."
```

Setelah memiliki sumber daya yang diperlukan, kami dapat membuat VM. Untuk langkah ini, kami membuat objek konfigurasi VM, lalu kami menggunakan konfigurasi untuk membuat VM.

```powershell-interactive
# Create a virtual machine configuration
$vmConfig = New-AzureRmVMConfig -VMName $vmName -VMSize Standard_D1 |
  Set-AzureRmVMOperatingSystem -Windows -ComputerName $vmName -Credential $cred |
  Set-AzureRmVMSourceImage -PublisherName MicrosoftWindowsServer -Offer WindowsServer -Skus 2016-Datacenter -Version latest |
  Add-AzureRmVMNetworkInterface -Id $nic.Id

# Create a virtual machine
New-AzureRmVM -ResourceGroupName $resourceGroup -Location $location -VM $vmConfig
```

Perintah `New-AzureRmVM` output menghasilkan setelah VM dibuat sepenuhnya dan siap untuk digunakan.

```Output
RequestId IsSuccessStatusCode StatusCode ReasonPhrase
--------- ------------------- ---------- ------------
                         True         OK OK
```

Sekarang, masuk ke vm Windows Server VM yang baru dibuat menggunakan Remote Desktop dan alamat IP publik VM. Perintah berikut ini menampilkan alamat IP publik yang dibuat dalam skrip sebelumnya.

```powershell-interactive
$publicIp | Select-Object Name,IpAddress
```

```Output
Name                  IpAddress
----                  ---------
mypublicdns1400512543 xx.xx.xx.xx
```

Jika menggunakan sistem berbasis Windows, Anda dapat melakukannya dari baris perintah menggunakan perintah mstsc:

```powershell-interactive
mstsc /v:xx.xxx.xx.xxx
```

Masukkan kombinasi nama pengguna/kata sandi yang sama dengan yang Anda gunakan saat membuat VM untuk masuk.

## <a name="create-a-linux-virtual-machine"></a>Membuat Komputer Virtual Linux

Untuk membuat VM Linux baru, kami harus terlebih dahulu membuat sumber daya lain yang diperlukan dan menetapkannya ke konfigurasi. Lalu, kami dapat menggunakan konfigurasi tersebut untuk membuat VM. Ini mengasumsikan bahwa Anda sudah membuat grup sumber daya seperti yang diperlihatkan sebelumnya. Anda juga harus memiliki kunci publik FIREFOX yang `id_rsa.pub` dinamai dalam direktori .directory .directory dari profil pengguna Anda.

### <a name="create-the-required-network-resources"></a>Membuat sumber daya jaringan yang diperlukan

Pertama, kita perlu membuat konfigurasi subnet untuk digunakan dengan proses pembuatan jaringan virtual. Kami juga membuat alamat IP publik sehingga kami dapat terhubung ke VM ini. Kami membuat grup keamanan jaringan untuk mengamankan akses ke alamat publik. Akhirnya kami membuat NIC virtual menggunakan semua sumber daya sebelumnya.

```powershell-interactive
# Variables for common values
$resourceGroup = "myResourceGroup"
$location = "westeurope"
$vmName = "myLinuxVM"

# Definer user name and blank password
$securePassword = ConvertTo-SecureString ' ' -AsPlainText -Force
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

### <a name="create-the-virtual-machine"></a>Membuat mesin virtual

Setelah memiliki sumber daya yang diperlukan, kami dapat membuat VM. Untuk langkah ini, kami membuat objek konfigurasi VM, lalu kami menggunakan konfigurasi untuk membuat VM.

```powershell-interactive
# Create a virtual machine configuration
$vmConfig = New-AzureRmVMConfig -VMName $vmName -VMSize Standard_D1 |
  Set-AzureRmVMOperatingSystem -Linux -ComputerName $vmName -Credential $cred -DisablePasswordAuthentication |
  Set-AzureRmVMSourceImage -PublisherName Canonical -Offer UbuntuServer -Skus 14.04.2-LTS -Version latest |
  Add-AzureRmVMNetworkInterface -Id $nic.Id

# Configure SSH Keys
$sshPublicKey = Get-Content "$env:USERPROFILE\.ssh\id_rsa.pub"
Add-AzureRmVMSshPublicKey -VM $vmConfig -KeyData $sshPublicKey -Path "/home/azureuser/.ssh/authorized_keys"

# Create a virtual machine
New-AzureRmVM -ResourceGroupName $resourceGroup -Location $location -VM $vmConfig
```

Setelah VM dibuat, Anda dapat masuk ke Linux VM baru menggunakan VM MENGGUNAKAN VM publik dengan alamat IP publik VM yang Anda buat:

```bash
ssh xx.xxx.xxx.xxx
```

```Output
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

## <a name="creating-other-resources-in-azure"></a>Membuat sumber daya lainnya di Azure

Kini kami telah mempelajari cara membuat Grup Sumber Daya, Linux VM, dan vm Windows Server. Anda juga dapat membuat berbagai tipe sumber daya Azure lainnya.

Misalnya, untuk membuat Penyeimbang Muat Jaringan Azure yang kemudian bisa kami kaitkan dengan VM yang baru dibuat, kami bisa menggunakan perintah buat berikut ini:

```powershell-interactive
New-AzureRmLoadBalancer -Name MyLoadBalancer -ResourceGroupName myResourceGroup -Location westeurope
```

Kami juga dapat membuat Jaringan Virtual pribadi baru (biasanya disebut sebagai "VNet" dalam Azure) untuk infrastruktur kami yang menggunakan perintah berikut:

```powershell-interactive
$subnetConfig = New-AzureRmVirtualNetworkSubnetConfig -Name mySubnet2 -AddressPrefix 10.0.0.0/16
$vnet = New-AzureRmVirtualNetwork -ResourceGroupName myResourceGroup -Location westeurope `
  -Name MYvNET3 -AddressPrefix 10.0.0.0/16 -Subnet $subnetConfig
```

Yang membuat Azure dan Azure PowerShell canggih adalah bahwa kami dapat menggunakannya tidak hanya untuk mendapatkan infrastruktur berbasis awan tetapi juga untuk membuat layanan platform terkelola. Layanan platform terkelola juga dapat digabungkan dengan infrastruktur untuk membangun solusi yang jauh lebih efektif.

Misalnya, Anda bisa menggunakan Azure PowerShell untuk membuat Aplikasi Azure AppService. Azure AppService adalah layanan platform terkelola yang menyediakan cara hebat untuk menghosting aplikasi web tanpa perlu khawatir tentang infrastruktur. Setelah membuat Azure AppService, Anda bisa membuat dua Aplikasi Azure Web baru di dalam AppService menggunakan perintah berikut:

```powershell-interactive
# Create an Azure AppService that we can host any number of web apps within
New-AzureRmAppServicePlan -Name MyAppServicePlan -Tier Basic -NumberofWorkers 2 -WorkerSize Small -ResourceGroupName myResourceGroup -Location westeurope

# Create Two Web Apps within the AppService (note: name param must be a unique DNS entry)
New-AzureRmWebApp -Name MyWebApp43432 -AppServicePlan MyAppServicePlan -ResourceGroupName myResourceGroup -Location westeurope
New-AzureRmWebApp -Name MyWebApp43433 -AppServicePlan MyAppServicePlan -ResourceGroupName myResourceGroup -Location westeurope
```

## <a name="listing-deployed-resources"></a>Daftar sumber daya yang disebarkan

Anda dapat menggunakan `Get-AzureRmResource` cmdlet untuk mencantumkan sumber daya yang berjalan di Azure. Contoh berikut ini memperlihatkan sumber daya yang baru saja kita buat dalam grup sumber daya baru.

```powershell-interactive
Get-AzureRmResource |
  Where-Object ResourceGroupName -eq myResourceGroup |
    Select-Object Name,Location,ResourceType
```

```Output
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

Untuk membersihkan akun Azure, Anda ingin menghapus sumber daya yang kami buat dalam contoh ini. Anda dapat menggunakan `Remove-AzureRm*` cmdlet untuk menghapus sumber daya yang tidak lagi dibutuhkan. Untuk menghapus Windows VM yang kami buat, menggunakan perintah berikut:

```powershell-interactive
Remove-AzureRmVM -Name myWindowsVM -ResourceGroupName myResourceGroup
```

Anda akan diminta untuk mengonfirmasi bahwa Anda ingin menghapus sumber daya tersebut.

```Output
Confirm
Are you sure you want to remove resource group 'myResourceGroup'
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): Y
```

Anda juga bisa menggunakan hapus banyak sumber daya sekaligus. Misalnya, perintah berikut ini menghapus semua grup sumber daya "MyResourceGroup" yang telah kami gunakan untuk semua sampel dalam tutorial Mulai ini. Ini menghapus grup sumber daya dan semua sumber daya di dalamnya.

```powershell-interactive
Remove-AzureRmResourceGroup -Name myResourceGroup
```

```Output
Confirm
Are you sure you want to remove resource group 'myResourceGroup'
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): Y
```

Ini bisa membutuhkan waktu beberapa menit hingga selesai.

## <a name="get-samples"></a>Dapatkan contoh

Untuk mempelajari selengkapnya tentang cara menggunakan Azure PowerShell, lihat skrip kami yang paling umum untuk [VM Linux](/azure/virtual-machines/linux/powershell-samples?toc=%2fpowershell%2fazure%%2ftoc.json), [Windows VM](/azure/virtual-machines/windows/powershell-samples?toc=%2fpowershell%2fazure%%2ftoc.json), Web [Apps](/azure/app-service-web/app-service-powershell-samples?toc=%2fpowershell%2fazure%%2ftoc.json), dan SQL [Database .](/azure/sql-database/sql-database-powershell-samples?toc=%2fpowershell%2fazure%%2ftoc.json)

## <a name="next-steps"></a>Langkah berikutnya

* [Masuk dengan Azure PowerShell](authenticate-azureps.md)
* [Kelola langganan Azure dengan Azure PowerShell](manage-subscriptions-azureps.md)
* [Membuat prinsipal layanan di Azure menggunakan Azure PowerShell](create-azure-service-principal-azureps.md)
* Baca [catatan Rilis](./release-notes-azureps.md) tentang melakukan migrasi dari rilis yang lebih lama.
* Dapatkan bantuan dari komunitas:
  * [Forum Azure di MSDN](https://go.microsoft.com/fwlink/p/?LinkId=320212)
  * [alur tumpuk](https://go.microsoft.com/fwlink/?LinkId=320213)
