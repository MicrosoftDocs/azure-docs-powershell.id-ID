---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
ms.assetid: 1A2C843C-6962-4B0E-ACBF-A5EFF609A5BE
online version: https://docs.microsoft.com/powershell/module/az.compute/new-azvmss
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/New-AzVmss.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/New-AzVmss.md
ms.openlocfilehash: f92c25e48dcb786426d65f04c8be53794e63d397
ms.sourcegitcommit: 5df8b100721844736630242c724da453a2168434
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/26/2022
ms.locfileid: "146597370"
---
# New-AzVmss

## SYNOPSIS
Membuat VMSS.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.compute/new-azvmss) untuk informasi terbaru.

## SYNTAX

### DefaultParameter (Default)
```
New-AzVmss [-ResourceGroupName] <String> [-VMScaleSetName] <String>
 [-VirtualMachineScaleSet] <PSVirtualMachineScaleSet> [-AsJob] [-EdgeZone <String>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SimpleParameterSet
```
New-AzVmss [[-ResourceGroupName] <String>] [-VMScaleSetName] <String> [-AsJob] [-UserData <String>]
 [-ImageName <String>] -Credential <PSCredential> [-InstanceCount <Int32>] [-VirtualNetworkName <String>]
 [-SubnetName <String>] [-PublicIpAddressName <String>] [-DomainNameLabel <String>]
 [-SecurityGroupName <String>] [-LoadBalancerName <String>] [-BackendPort <Int32[]>] [-Location <String>]
 [-EdgeZone <String>] [-VmSize <String>] [-UpgradePolicyMode <UpgradeMode>] [-AllocationMethod <String>]
 [-VnetAddressPrefix <String>] [-SubnetAddressPrefix <String>] [-FrontendPoolName <String>]
 [-BackendPoolName <String>] [-SystemAssignedIdentity] [-UserAssignedIdentity <String>] [-EnableUltraSSD]
 [-Zone <System.Collections.Generic.List`1[System.String]>] [-NatBackendPort <Int32[]>]
 [-DataDiskSizeInGb <Int32[]>] [-ProximityPlacementGroupId <String>] [-HostGroupId <String>]
 [-Priority <String>] [-EvictionPolicy <String>] [-MaxPrice <Double>] [-ScaleInPolicy <String[]>]
 [-SkipExtensionsOnOverprovisionedVMs] [-EncryptionAtHost] [-PlatformFaultDomainCount <Int32>]
 [-OrchestrationMode <String>] [-CapacityReservationGroupId <String>] [-ImageReferenceId <String>]
 [-DefaultProfile <IAzureContextContainer>] [-SinglePlacementGroup] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzVmss** membuat Virtual Machine Scale Set (VMSS) di Azure.
Gunakan set parameter sederhana (`SimpleParameterSet`) untuk membuat VMSS yang telah ditetapkan dan sumber daya terkait dengan cepat. Gunakan set parameter default (`DefaultParameter`) untuk skenario yang lebih canggih saat Anda perlu mengonfigurasi setiap komponen VMSS dengan tepat dan setiap sumber daya terkait sebelum pembuatan.

## EXAMPLES

### Contoh 1: Membuat VMSS menggunakan SimpleParameterSet
```powershell
$vmssName = <VMSSNAME>
# Create credentials, I am using one way to create credentials, there are others as well. 
# Pick one that makes the most sense according to your use case.
$vmPassword = ConvertTo-SecureString <PASSWORD_HERE> -AsPlainText -Force
$vmCred = New-Object System.Management.Automation.PSCredential(<USERNAME_HERE>, $vmPassword)

#Create a VMSS using the default settings
New-AzVmss -Credential $vmCred -VMScaleSetName $vmssName
```

Perintah di atas membuat yang berikut ini dengan nama `$vmssName` :
* Grup Sumber Daya
* Jaringan virtual
* Penyeimbang beban
* IP Publik
* VMSS dengan 2 instans

Gambar default yang dipilih untuk VM di VMSS adalah `2016-Datacenter Windows Server` dan SKU adalah `Standard_DS1_v2`

### Contoh 2: Membuat VMSS menggunakan DefaultParameterSet
```powershell
# Common
$LOC = "WestUs";
$RGName = "rgkyvms";

New-AzResourceGroup -Name $RGName -Location $LOC -Force;

# SRP
$STOName = "STO" + $RGName;
$STOType = "Standard_GRS";
New-AzStorageAccount -ResourceGroupName $RGName -Name $STOName -Location $LOC -Type $STOType;
$STOAccount = Get-AzStorageAccount -ResourceGroupName $RGName -Name $STOName; 

# NRP
$SubNet = New-AzVirtualNetworkSubnetConfig -Name ("subnet" + $RGName) -AddressPrefix "10.0.0.0/24";
$VNet = New-AzVirtualNetwork -Force -Name ("vnet" + $RGName) -ResourceGroupName $RGName -Location $LOC -AddressPrefix "10.0.0.0/16" -DnsServer "10.1.1.1" -Subnet $SubNet;
$VNet = Get-AzVirtualNetwork -Name ('vnet' + $RGName) -ResourceGroupName $RGName;
$SubNetId = $VNet.Subnets[0].Id;

$PubIP = New-AzPublicIpAddress -Force -Name ("PubIP" + $RGName) -ResourceGroupName $RGName -Location $LOC -AllocationMethod Dynamic -DomainNameLabel ("PubIP" + $RGName);
$PubIP = Get-AzPublicIpAddress -Name ("PubIP"  + $RGName) -ResourceGroupName $RGName;

# Create LoadBalancer
$FrontendName = "fe" + $RGName
$BackendAddressPoolName = "bepool" + $RGName
$ProbeName = "vmssprobe" + $RGName
$InboundNatPoolName  = "innatpool" + $RGName
$LBRuleName = "lbrule" + $RGName
$LBName = "vmsslb" + $RGName

$Frontend = New-AzLoadBalancerFrontendIpConfig -Name $FrontendName -PublicIpAddress $PubIP
$BackendAddressPool = New-AzLoadBalancerBackendAddressPoolConfig -Name $BackendAddressPoolName
$Probe = New-AzLoadBalancerProbeConfig -Name $ProbeName -RequestPath healthcheck.aspx -Protocol http -Port 80 -IntervalInSeconds 15 -ProbeCount 2
$InboundNatPool = New-AzLoadBalancerInboundNatPoolConfig -Name $InboundNatPoolName  -FrontendIPConfigurationId `
    $Frontend.Id -Protocol Tcp -FrontendPortRangeStart 3360 -FrontendPortRangeEnd 3362 -BackendPort 3370;
$LBRule = New-AzLoadBalancerRuleConfig -Name $LBRuleName `
    -FrontendIPConfiguration $Frontend -BackendAddressPool $BackendAddressPool `
    -Probe $Probe -Protocol Tcp -FrontendPort 80 -BackendPort 80 `
    -IdleTimeoutInMinutes 15 -EnableFloatingIP -LoadDistribution SourceIP;
$ActualLb = New-AzLoadBalancer -Name $LBName -ResourceGroupName $RGName -Location $LOC `
    -FrontendIpConfiguration $Frontend -BackendAddressPool $BackendAddressPool `
    -Probe $Probe -LoadBalancingRule $LBRule -InboundNatPool $InboundNatPool;
$ExpectedLb = Get-AzLoadBalancer -Name $LBName -ResourceGroupName $RGName

# New VMSS Parameters
$VMSSName = "VMSS" + $RGName;

$AdminUsername = "Admin01";
$AdminPassword = "p4ssw0rd@123" + $RGName;

$PublisherName = "MicrosoftWindowsServer" 
$Offer         = "WindowsServer" 
$Sku           = "2012-R2-Datacenter" 
$Version       = "latest"
        
$VHDContainer = "https://" + $STOName + ".blob.core.contoso.net/" + $VMSSName;

$ExtName = "CSETest";
$Publisher = "Microsoft.Compute";
$ExtType = "BGInfo";
$ExtVer = "2.1";

#IP Config for the NIC
$IPCfg = New-AzVmssIPConfig -Name "Test" `
    -LoadBalancerInboundNatPoolsId $ExpectedLb.InboundNatPools[0].Id `
    -LoadBalancerBackendAddressPoolsId $ExpectedLb.BackendAddressPools[0].Id `
    -SubnetId $SubNetId;
            
#VMSS Config
$VMSS = New-AzVmssConfig -Location $LOC -SkuCapacity 2 -SkuName "Standard_E4-2ds_v4" -UpgradePolicyMode "Automatic" `
    | Add-AzVmssNetworkInterfaceConfiguration -Name "Test" -Primary $True -IPConfiguration $IPCfg `
    | Add-AzVmssNetworkInterfaceConfiguration -Name "Test2"  -IPConfiguration $IPCfg `
    | Set-AzVmssOSProfile -ComputerNamePrefix "Test"  -AdminUsername $AdminUsername -AdminPassword $AdminPassword `
    | Set-AzVmssStorageProfile -Name "Test"  -OsDiskCreateOption 'FromImage' -OsDiskCaching "None" `
    -ImageReferenceOffer $Offer -ImageReferenceSku $Sku -ImageReferenceVersion $Version `
    -ImageReferencePublisher $PublisherName -VhdContainer $VHDContainer `
    | Add-AzVmssExtension -Name $ExtName -Publisher $Publisher -Type $ExtType -TypeHandlerVersion $ExtVer -AutoUpgradeMinorVersion $True

#Create the VMSS
New-AzVmss -ResourceGroupName $RGName -Name $VMSSName -VirtualMachineScaleSet $VMSS;
```

### Contoh 3: Membuat VMSS dengan nilai UserData
```powershell
$ResourceGroupName = '<RESOURCE GROUP NAME>';
$vmssName = <VMSSNAME>;
$domainNameLabel = "dnl" + $ResourceGroupName;
# Create credentials, I am using one way to create credentials, there are others as well. 
# Pick one that makes the most sense according to your use case.
$vmPassword = ConvertTo-SecureString <PASSWORD_HERE> -AsPlainText -Force;
$vmCred = New-Object System.Management.Automation.PSCredential(<USERNAME_HERE>, $vmPassword);

$text = "UserData value to encode";
$bytes = [System.Text.Encoding]::Unicode.GetBytes($text);
$userData = [Convert]::ToBase64String($bytes);

#Create a VMSS
New-AzVmss -ResourceGroupName $ResourceGroupName -Name $vmssName -Credential $vmCred -DomainNameLabel $domainNameLabel -Userdata $userData;
$vmss = Get-AzVmss -ResourceGroupName $ResourceGroupName -VMScaleSetName $vmssName -InstanceView:$false -Userdata;
```

Contoh kompleks di atas membuat VMSS, berikut adalah penjelasan tentang apa yang terjadi:
* Perintah pertama membuat grup sumber daya dengan nama dan lokasi yang ditentukan.
* Perintah kedua menggunakan cmdlet **New-AzStorageAccount** untuk membuat akun penyimpanan.
* Perintah ketiga kemudian menggunakan cmdlet **Get-AzStorageAccount** untuk mendapatkan akun penyimpanan yang dibuat di perintah kedua dan menyimpan hasilnya dalam variabel $STOAccount.
* Perintah kelima menggunakan cmdlet **New-AzVirtualNetworkSubnetConfig** untuk membuat subnet dan menyimpan hasilnya dalam variabel bernama $SubNet.
* Perintah keenam menggunakan cmdlet **New-AzVirtualNetwork** untuk membuat jaringan virtual dan menyimpan hasilnya dalam variabel bernama $VNet.
* Perintah ketujuh menggunakan **Get-AzVirtualNetwork** untuk mendapatkan informasi tentang jaringan virtual yang dibuat dalam perintah keenam dan menyimpan informasi dalam variabel bernama $VNet.
* Perintah kedelapan dan kesembilan menggunakan **New-AzPublicIpAddress** dan **Get- AzureRmPublicIpAddress** untuk membuat dan mendapatkan informasi dari alamat IP publik tersebut.
* Perintah menyimpan informasi dalam variabel bernama $PubIP.
* Perintah kesepuluh menggunakan cmdlet **New- AzureRmLoadBalancerFrontendIpConfig** untuk membuat penyeimbang beban frontend dan menyimpan hasilnya dalam variabel bernama $Frontend.
* Perintah kesebelas menggunakan **New-AzLoadBalancerBackendAddressPoolConfig** untuk membuat konfigurasi kumpulan alamat backend dan menyimpan hasilnya dalam variabel bernama $BackendAddressPool.
* Perintah kedua belas menggunakan **New-AzLoadBalancerProbeConfig** untuk membuat pemeriksaan dan menyimpan informasi pemeriksaan dalam variabel bernama $Probe.
* Perintah ketiga belas menggunakan cmdlet **New-AzLoadBalancerInboundNatPoolConfig** untuk membuat konfigurasi kumpulan terjemahan alamat jaringan masuk (NAT) penyeimbang muatan.
* Perintah keempat belas menggunakan **New-AzLoadBalancerRuleConfig** untuk membuat konfigurasi aturan load balancer dan menyimpan hasilnya dalam variabel bernama $LBRule.
* Perintah kelima belas menggunakan cmdlet **New-AzLoadBalancer** untuk membuat load balancer dan menyimpan hasilnya dalam variabel bernama $ActualLb.
* Perintah keenam belas menggunakan **Get-AzLoadBalancer** untuk mendapatkan informasi tentang load balancer yang dibuat dalam perintah kelima belas dan menyimpan informasi dalam variabel bernama $ExpectedLb.
* Perintah ketujuh belas menggunakan cmdlet **New-AzVmssIPConfig** untuk membuat konfigurasi IP VMSS dan menyimpan informasi dalam variabel bernama $IPCfg.
* Perintah kedelapan belas menggunakan cmdlet **New-AzVmssConfig** untuk membuat objek konfigurasi VMSS dan menyimpan hasilnya dalam variabel bernama $VMSS.
* Perintah kesembilan belas menggunakan cmdlet **New-AzVmss** untuk membuat VMSS.

## PARAMETERS

### -AllocationMethod
Metode alokasi untuk Alamat IP Publik dari Set Skala (Statis atau Dinamis).  Jika tidak ada nilai yang disediakan, alokasi akan statis.

```yaml
Type: System.String
Parameter Sets: SimpleParameterSet
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

### -BackendPoolName
Nama kumpulan alamat backend yang akan digunakan dalam load balancer untuk Set Skala ini.  Jika tidak ada nilai yang disediakan, kumpulan backend baru akan dibuat, dengan nama yang sama dengan Set Skala.

```yaml
Type: System.String
Parameter Sets: SimpleParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -BackendPort
Nomor port backend yang digunakan oleh load balancer Set Skala untuk berkomunikasi dengan VM di Set Skala.  Jika tidak ada nilai yang ditentukan, port 3389 dan 5985 akan digunakan untuk Windows VMS, dan port 22 akan digunakan untuk VM Linux.

```yaml
Type: System.Int32[]
Parameter Sets: SimpleParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CapacityReservationGroupId
Id Grup reservasi kapasitas yang digunakan untuk mengalokasikan.

```yaml
Type: System.String
Parameter Sets: SimpleParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Credential
Info masuk administrator (nama pengguna dan kata sandi) untuk VM dalam Set Skala ini.

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
Menentukan ukuran disk data dalam GB.

```yaml
Type: System.Int32[]
Parameter Sets: SimpleParameterSet
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

### -DomainNameLabel
Label nama domain untuk nama domain Fully-Qualified publik (FQDN) untuk Set Skala ini. Ini adalah komponen pertama dari nama domain yang secara otomatis ditetapkan ke Set Skala. Nama domain yang ditetapkan secara otomatis menggunakan formulir (`<DomainNameLabel>.<Location>.cloudapp.azure.com`). Jika tidak ada nilai yang disediakan, label nama domain default akan menjadi perangkaian `<ScaleSetName>` dan `<ResourceGroupName>`.

```yaml
Type: System.String
Parameter Sets: SimpleParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EdgeZone
Mengatur nama zona tepi. Jika diatur, kueri akan dirutekan ke zona tepi yang ditentukan alih-alih wilayah utama.

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

### -EnableUltrassD
Gunakan disk UltraSSD untuk VM dalam set skala.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SimpleParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EncryptionAtHost
Parameter ini akan mengaktifkan enkripsi untuk semua disk termasuk disk Resource/Temp di host itu sendiri. Default: Enkripsi di host akan dinonaktifkan kecuali properti ini diatur ke true untuk sumber daya.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SimpleParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EvictionPolicy
Kebijakan pengeluaran untuk set skala komputer virtual prioritas rendah.  Hanya nilai yang didukung yang 'Batalkan alokasi' dan 'Hapus'.

```yaml
Type: System.String
Parameter Sets: SimpleParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FrontendPoolName
Nama kumpulan alamat frontend yang akan digunakan dalam load balancer Set Skala.  Jika tidak ada nilai yang disediakan, Kumpulan Alamat Frontend baru akan dibuat, dengan nama yang sama dengan set skala.

```yaml
Type: System.String
Parameter Sets: SimpleParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HostGroupId
Menentukan grup host khusus tempat set skala komputer virtual akan berada.

```yaml
Type: System.String
Parameter Sets: SimpleParameterSet
Aliases: HostGroup

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ImageName
Nama gambar untuk VM dalam Set Skala ini. Jika tidak ada nilai yang disediakan, gambar "Windows Server 2016 DataCenter" akan digunakan.

```yaml
Type: System.String
Parameter Sets: SimpleParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InstanceCount
Jumlah gambar VM dalam Set Skala.  Jika tidak ada nilai yang disediakan, 2 instans akan dibuat.

```yaml
Type: System.Int32
Parameter Sets: SimpleParameterSet
Aliases:

Required: False
Position: Named
Default value: 2
Accept pipeline input: False
Accept wildcard characters: False
```

### -LoadBalancerName
Nama load balancer yang akan digunakan dengan Set Skala ini.  Load balancer baru yang menggunakan nama yang sama dengan Set Skala akan dibuat jika tidak ada nilai yang ditentukan.

```yaml
Type: System.String
Parameter Sets: SimpleParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lokasi
Lokasi Azure tempat Set Skala ini akan dibuat.  Jika tidak ada nilai yang ditentukan, lokasi akan disimpulkan dari lokasi sumber daya lain yang dirujuk dalam parameter.

```yaml
Type: System.String
Parameter Sets: SimpleParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxPrice
Harga maksimum penagihan set skala komputer virtual berprioritas rendah.

```yaml
Type: System.Double
Parameter Sets: SimpleParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NatBackendPort
Port backend untuk terjemahan alamat jaringan masuk.

```yaml
Type: System.Int32[]
Parameter Sets: SimpleParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OrchestrationMode
Menentukan mode orkestrasi untuk set skala komputer virtual. Nilai yang mungkin: Seragam, Fleksibel

```yaml
Type: System.String
Parameter Sets: SimpleParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PlatformFaultDomainCount
Jumlah Domain Kesalahan untuk setiap grup penempatan.

```yaml
Type: System.Int32
Parameter Sets: SimpleParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Prioritas
Prioritas untuk komputer virtual dalam set skala.  Hanya nilai yang didukung adalah 'Reguler', 'Spot' dan 'Rendah'.
'Reguler' adalah untuk komputer virtual reguler.
'Spot' adalah untuk komputer virtual spot.
'Rendah' juga untuk komputer virtual spot tetapi digantikan oleh 'Spot'. Silakan gunakan 'Spot' alih-alih 'Rendah'.

```yaml
Type: System.String
Parameter Sets: SimpleParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProximityPlacementGroupId
Id sumber daya Grup Penempatan Kedekatan untuk digunakan dengan set skala ini.

```yaml
Type: System.String
Parameter Sets: SimpleParameterSet
Aliases: ProximityPlacementGroup

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PublicIpAddressName
Nama Alamat IP publik yang akan digunakan dengan set skala ini.  IPAddress Publik baru dengan nama yang sama dengan Set Skala akan dibuat jika tidak ada nilai yang disediakan.

```yaml
Type: System.String
Parameter Sets: SimpleParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya VMSS.  Jika tidak ada nilai yang ditentukan, ResourceGroup baru akan dibuat menggunakan nama yang sama dengan Set Skala.

```yaml
Type: System.String
Parameter Sets: DefaultParameter
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: System.String
Parameter Sets: SimpleParameterSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ScaleInPolicy
Aturan yang harus diikuti saat menskalakan-dalam set skala komputer virtual.  Nilai yang mungkin adalah: 'Default', 'OldestVM' dan 'NewestVM'.  'Default' ketika set skala komputer virtual diskalakan, set skala akan terlebih dahulu diseimbangkan di seluruh zona jika merupakan set skala zona.  Kemudian, itu akan seimbang di seluruh Domain Kesalahan sejauh mungkin.  Dalam setiap Domain Kesalahan, komputer virtual yang dipilih untuk dihapus akan menjadi yang terbaru yang tidak dilindungi dari penyempurnaan skala.  'OldestVM' ketika set skala komputer virtual sedang diskalakan, komputer virtual terlama yang tidak terlindungi dari penyempurnaan skala akan dipilih untuk dihapus.  Untuk set skala komputer virtual zonal, set skala pertama-tama akan seimbang di seluruh zona.  Dalam setiap zona, komputer virtual terlama yang tidak dilindungi akan dipilih untuk dihapus.  'NewestVM' ketika set skala komputer virtual sedang diskalakan, komputer virtual terbaru yang tidak terlindungi dari penyempurnaan skala akan dipilih untuk dihapus.  Untuk set skala komputer virtual zonal, set skala pertama-tama akan seimbang di seluruh zona.  Dalam setiap zona, komputer virtual terbaru yang tidak dilindungi akan dipilih untuk dihapus.

```yaml
Type: System.String[]
Parameter Sets: SimpleParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SecurityGroupName
Nama grup keamanan jaringan yang akan diterapkan ke Set Skala ini.  Jika tidak ada nilai yang disediakan, grup keamanan jaringan default dengan nama yang sama dengan Set Skala akan dibuat dan diterapkan ke Set Skala.

```yaml
Type: System.String
Parameter Sets: SimpleParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ImageReferenceId
Menentukan id unik gambar galeri bersama untuk penyebaran vmss. Ini dapat diambil dari panggilan GET gambar galeri bersama.

```yaml
Type: System.String
Parameter Sets: SimpleParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SinglePlacementGroup
Gunakan ini untuk membuat set Skala dalam satu grup penempatan, defaultnya adalah beberapa grup

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SimpleParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkipExtensionsOnOverprovisionedVMs
Menentukan bahwa ekstensi tidak berjalan pada VM ekstra yang terlalu provisi.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SimpleParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubnetAddressPrefix
Awalan alamat Subnet yang akan digunakan ScaleSet ini. Pengaturan Subnet default (192.168.1.0/24) akan diterapkan jika tidak ada nilai yang disediakan.

```yaml
Type: System.String
Parameter Sets: SimpleParameterSet
Aliases:

Required: False
Position: Named
Default value: 192.168.1.0/24
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubnetName
Nama subnet yang akan digunakan dengan Set Skala ini.  Subnet baru akan dibuat dengan nama yang sama dengan Set Skala jika tidak ada nilai yang disediakan.

```yaml
Type: System.String
Parameter Sets: SimpleParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SystemAssignedIdentity
Jika parameter ada, maka VM dalam set skala adalah(adalah) diberi identitas sistem terkelola yang dibuat secara otomatis.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: SimpleParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UpgradePolicyMode
Mode kebijakan peningkatan untuk instans VM dalam Set Skala ini.  Kebijakan peningkatan dapat menentukan peningkatan Otomatis, Manual, atau Bergulir.

```yaml
Type: Microsoft.Azure.Management.Compute.Models.UpgradeMode
Parameter Sets: SimpleParameterSet
Aliases:
Accepted values: Automatic, Manual, Rolling

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserAssignedIdentity
Nama identitas layanan terkelola yang harus ditetapkan ke VM dalam set skala.

```yaml
Type: System.String
Parameter Sets: SimpleParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UserData
UserData untuk Vmss, yang akan dikodekan base-64. Pelanggan tidak boleh meneruskan rahasia apa pun di sini.

```yaml
Type: System.String
Parameter Sets: SimpleParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VirtualMachineScaleSet
Menentukan objek **VirtualMachineScaleSet** yang berisi properti VMSS yang dibuat cmdlet ini.

```yaml
Type: Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet
Parameter Sets: DefaultParameter
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VirtualNetworkName
Nama untuk Virtual Network digunakan dengan set skala ini.  Jika tidak ada nilai yang disediakan, jaringan virtual baru dengan nama yang sama dengan Set Skala akan dibuat.

```yaml
Type: System.String
Parameter Sets: SimpleParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMScaleSetName
Menentukan nama VMSS yang dibuat cmdlet ini.

```yaml
Type: System.String
Parameter Sets: DefaultParameter
Aliases: Name

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: System.String
Parameter Sets: SimpleParameterSet
Aliases: Name

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VmSize
Ukuran instans VM dalam set skala ini.  Ukuran default (Standard_DS1_v2) akan digunakan jika tidak ada Ukuran yang ditentukan.

```yaml
Type: System.String
Parameter Sets: SimpleParameterSet
Aliases:

Required: False
Position: Named
Default value: Standard_DS1_v2
Accept pipeline input: False
Accept wildcard characters: False
```

### -VnetAddressPrefix
Awalan alamat untuk jaringan virtual yang digunakan dengan Set Skala ini.  Pengaturan awalan alamat jaringan virtual default (192.168.0.0/16) akan digunakan jika tidak ada nilai yang disediakan.

```yaml
Type: System.String
Parameter Sets: SimpleParameterSet
Aliases:

Required: False
Position: Named
Default value: 192.168.0.0/16
Accept pipeline input: False
Accept wildcard characters: False
```

### -Zona
Daftar zona ketersediaan yang menunjukkan IP yang dialokasikan untuk kebutuhan sumber daya.

```yaml
Type: System.Collections.Generic.List`1[System.String]
Parameter Sets: SimpleParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

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
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

### Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet

### System.Collections.Generic.List'1[[System.String, System.Private.CoreLib, Version=4.0.0.0, Culture=neutral, PublicKeyToken=7cec85d7bea7798e]]

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet

## NOTES

## RELATED LINKS

[Dapatkan-AzVmss](./Get-AzVmss.md)

[Remove-AzVmss](./Remove-AzVmss.md)

[Mulai ulang-AzVmss](./Restart-AzVmss.md)

[Set-AzVmss](./Set-AzVmss.md)

[Start-AzVmss](./Start-AzVmss.md)

[Stop-AzVmss](./Stop-AzVmss.md)

[Update-AzVmss](./Update-AzVmss.md)
