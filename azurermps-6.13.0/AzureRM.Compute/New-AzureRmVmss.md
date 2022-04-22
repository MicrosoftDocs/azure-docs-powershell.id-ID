---
external help file: Microsoft.Azure.Commands.Compute.dll-Help.xml
Module Name: AzureRM.Compute
ms.assetid: 1A2C843C-6962-4B0E-ACBF-A5EFF609A5BE
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.compute/new-azurermvmss
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Compute/Commands.Compute/help/New-AzureRmVmss.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Compute/Commands.Compute/help/New-AzureRmVmss.md
ms.openlocfilehash: 9f6135917f2e6cbfc05511637b3b20bd126d54b5
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142923287"
---
# New-AzureRmVmss

## SYNOPSIS
Membuat VMSS.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### DefaultParameter (Default)
```
New-AzureRmVmss [-ResourceGroupName] <String> [-VMScaleSetName] <String>
 [-VirtualMachineScaleSet] <PSVirtualMachineScaleSet> [-AsJob] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SimpleParameterSet
```
New-AzureRmVmss [[-ResourceGroupName] <String>] [-VMScaleSetName] <String> [-AsJob] [-ImageName <String>]
 -Credential <PSCredential> [-InstanceCount <Int32>] [-VirtualNetworkName <String>] [-SubnetName <String>]
 [-PublicIpAddressName <String>] [-DomainNameLabel <String>] [-SecurityGroupName <String>]
 [-LoadBalancerName <String>] [-BackendPort <Int32[]>] [-Location <String>] [-VmSize <String>]
 [-UpgradePolicyMode <UpgradeMode>] [-AllocationMethod <String>] [-VnetAddressPrefix <String>]
 [-SubnetAddressPrefix <String>] [-FrontendPoolName <String>] [-BackendPoolName <String>]
 [-SystemAssignedIdentity] [-UserAssignedIdentity <String>]
 [-Zone <System.Collections.Generic.List`1[System.String]>] [-NatBackendPort <Int32[]>]
 [-DataDiskSizeInGb <Int32[]>] [-DefaultProfile <IAzureContextContainer>] [-SinglePlacementGroup] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **AzureRmVmss baru** membuat Kumpulan Skala Mesin Virtual (VMSS) di Azure.
Gunakan kumpulan parameter sederhana (`SimpleParameterSet`) untuk membuat VMSS yang telah ditetapkan sebelumnya dan sumber daya terkait dengan cepat. Gunakan kumpulan parameter default (`DefaultParameter`) untuk skenario tingkat lanjut lainnya saat Anda perlu mengonfigurasi setiap komponen VMSS dan setiap sumber daya terkait sebelum pembuatan.

## EXAMPLES

### Contoh 1: Membuat VMSS menggunakan **`SimpleParameterSet`**
```powershell
$vmssName = <VMSSNAME>
# Create credentials, I am using one way to create credentials, there are others as well. 
# Pick one that makes the most sense according to your use case.
$vmPassword = ConvertTo-SecureString <PASSWORD_HERE> -AsPlainText -Force
$vmCred = New-Object System.Management.Automation.PSCredential(<USERNAME_HERE>, $vmPassword)

#Create a VMSS using the default settings
New-AzureRmVmss -Credential $vmCred -VMScaleSetName $vmssName
```

Perintah di atas membuat yang berikut ini dengan nama `$vmssName` :
* Grup Sumber Daya
* Jaringan virtual
* Penyeimbang beban
* IP publik
* VMSS dengan 2 instans

Gambar default yang dipilih untuk VM dalam VMSS adalah `2016-Datacenter Windows Server` dan SKU `Standard_DS1_v2`

### Contoh 2: Membuat VMSS menggunakan **`DefaultParameterSet`**
```powershell
# Common
$LOC = "WestUs";
$RGName = "rgkyvms";

New-AzureRmResourceGroup -Name $RGName -Location $LOC -Force;

# SRP
$STOName = "STO" + $RGName;
$STOType = "Standard_GRS";
New-AzureRmStorageAccount -ResourceGroupName $RGName -Name $STOName -Location $LOC -Type $STOType;
$STOAccount = Get-AzureRmStorageAccount -ResourceGroupName $RGName -Name $STOName; 

# NRP
$SubNet = New-AzureRmVirtualNetworkSubnetConfig -Name ("subnet" + $RGName) -AddressPrefix "10.0.0.0/24";
$VNet = New-AzureRmVirtualNetwork -Force -Name ("vnet" + $RGName) -ResourceGroupName $RGName -Location $LOC -AddressPrefix "10.0.0.0/16" -DnsServer "10.1.1.1" -Subnet $SubNet;
$VNet = Get-AzureRmVirtualNetwork -Name ('vnet' + $RGName) -ResourceGroupName $RGName;
$SubNetId = $VNet.Subnets[0].Id;

$PubIP = New-AzureRmPublicIpAddress -Force -Name ("PubIP" + $RGName) -ResourceGroupName $RGName -Location $LOC -AllocationMethod Dynamic -DomainNameLabel ("PubIP" + $RGName);
$PubIP = Get-AzureRmPublicIpAddress -Name ("PubIP"  + $RGName) -ResourceGroupName $RGName;

# Create LoadBalancer
$FrontendName = "fe" + $RGName
$BackendAddressPoolName = "bepool" + $RGName
$ProbeName = "vmssprobe" + $RGName
$InboundNatPoolName  = "innatpool" + $RGName
$LBRuleName = "lbrule" + $RGName
$LBName = "vmsslb" + $RGName

$Frontend = New-AzureRmLoadBalancerFrontendIpConfig -Name $FrontendName -PublicIpAddress $PubIP
$BackendAddressPool = New-AzureRmLoadBalancerBackendAddressPoolConfig -Name $BackendAddressPoolName
$Probe = New-AzureRmLoadBalancerProbeConfig -Name $ProbeName -RequestPath healthcheck.aspx -Protocol http -Port 80 -IntervalInSeconds 15 -ProbeCount 2
$InboundNatPool = New-AzureRmLoadBalancerInboundNatPoolConfig -Name $InboundNatPoolName  -FrontendIPConfigurationId `
    $Frontend.Id -Protocol Tcp -FrontendPortRangeStart 3360 -FrontendPortRangeEnd 3362 -BackendPort 3370;
$LBRule = New-AzureRmLoadBalancerRuleConfig -Name $LBRuleName `
    -FrontendIPConfiguration $Frontend -BackendAddressPool $BackendAddressPool `
    -Probe $Probe -Protocol Tcp -FrontendPort 80 -BackendPort 80 `
    -IdleTimeoutInMinutes 15 -EnableFloatingIP -LoadDistribution SourceIP;
$ActualLb = New-AzureRmLoadBalancer -Name $LBName -ResourceGroupName $RGName -Location $LOC `
    -FrontendIpConfiguration $Frontend -BackendAddressPool $BackendAddressPool `
    -Probe $Probe -LoadBalancingRule $LBRule -InboundNatPool $InboundNatPool;
$ExpectedLb = Get-AzureRmLoadBalancer -Name $LBName -ResourceGroupName $RGName

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
$IPCfg = New-AzureRmVmssIPConfig -Name "Test" `
    -LoadBalancerInboundNatPoolsId $ExpectedLb.InboundNatPools[0].Id `
    -LoadBalancerBackendAddressPoolsId $ExpectedLb.BackendAddressPools[0].Id `
    -SubnetId $SubNetId;
            
#VMSS Config
$VMSS = New-AzureRmVmssConfig -Location $LOC -SkuCapacity 2 -SkuName "Standard_A2" -UpgradePolicyMode "Automatic" `
    | Add-AzureRmVmssNetworkInterfaceConfiguration -Name "Test" -Primary $True -IPConfiguration $IPCfg `
    | Add-AzureRmVmssNetworkInterfaceConfiguration -Name "Test2"  -IPConfiguration $IPCfg `
    | Set-AzureRmVmssOSProfile -ComputerNamePrefix "Test"  -AdminUsername $AdminUsername -AdminPassword $AdminPassword `
    | Set-AzureRmVmssStorageProfile -Name "Test"  -OsDiskCreateOption 'FromImage' -OsDiskCaching "None" `
    -ImageReferenceOffer $Offer -ImageReferenceSku $Sku -ImageReferenceVersion $Version `
    -ImageReferencePublisher $PublisherName -VhdContainer $VHDContainer `
    | Add-AzureRmVmssExtension -Name $ExtName -Publisher $Publisher -Type $ExtType -TypeHandlerVersion $ExtVer -AutoUpgradeMinorVersion $True

#Create the VMSS
New-AzureRmVmss -ResourceGroupName $RGName -Name $VMSSName -VirtualMachineScaleSet $VMSS;
```

Contoh kompleks di atas membuat VMSS, berikut ini adalah penjelasan tentang apa yang terjadi:
* Perintah pertama membuat grup sumber daya dengan nama dan lokasi yang ditentukan.
* Perintah kedua menggunakan cmdlet **New-AzureRmStorageAccount** untuk membuat akun penyimpanan.
* Perintah ketiga kemudian menggunakan cmdlet **Get-AzureRmStorageAccount** untuk membuat akun penyimpanan dibuat di perintah kedua dan menyimpan hasilnya dalam variabel $STOAccount.
* Perintah kelima menggunakan cmdlet **New-AzureRmVirtualNetworkSubnetConfig** untuk membuat subnet dan menyimpan hasilnya dalam variabel bernama $SubNet.
* Perintah keenam menggunakan cmdlet **New-AzureRmVirtualNetwork** untuk membuat jaringan virtual dan menyimpan hasilnya dalam variabel bernama $VNet.
* Perintah ketujuh menggunakan **Get-AzureRmVirtualNetwork** untuk mendapatkan informasi tentang jaringan virtual yang dibuat dalam perintah keenam dan menyimpan informasi dalam variabel bernama $VNet.
* Perintah kedelapan dan kesembilan menggunakan **New-AzureRmPublicIpAddress** dan **Get- AzureRmPublicIpAddress** untuk membuat dan mendapatkan informasi dari alamat IP publik tersebut.
* Perintah menyimpan informasi dalam variabel bernama $PubIP.
* Perintah kesepuluh menggunakan cmdlet **New- AzureRmLoadBalancerFrontendIpConfig** untuk membuat frontend load balancer dan menyimpan hasilnya dalam variabel bernama $Frontend.
* Perintah kesebelas menggunakan **New-AzureRmLoadBalancerBackendAddressPoolConfig** untuk membuat konfigurasi kumpulan alamat backend dan menyimpan hasilnya dalam variabel bernama $BackendAddressPool.
* Perintah kedua belas menggunakan **New-AzureRmLoadBalancerProbeConfig** untuk membuat probe dan menyimpan informasi probe dalam variabel bernama $Probe.
* Perintah ketiga belas menggunakan cmdlet **New-AzureRmLoadBalancerInboundNatPoolConfig** untuk membuat konfigurasi kumpulan terjemahan alamat jaringan masuk (NAT) penyeimbang muatan.
* Perintah keempat belas menggunakan **New-AzureRmLoadBalancerRuleConfig** untuk membuat konfigurasi aturan load balancer dan menyimpan hasilnya dalam variabel bernama $LBRule.
* Perintah kelima belas menggunakan cmdlet **New-AzureRmLoadBalancer** untuk membuat load balancer dan menyimpan hasilnya dalam variabel bernama $ActualLb.
* Perintah keenam belas menggunakan **Get-AzureRmLoadBalancer** untuk mendapatkan informasi tentang load balancer yang dibuat dalam perintah kelima belas dan menyimpan informasi dalam variabel bernama $ExpectedLb.
* Perintah ketujuh belas menggunakan cmdlet **New-AzureRmVmssIPConfig** untuk membuat konfigurasi IP VMSS dan menyimpan informasi dalam variabel bernama $IPCfg.
* Perintah kedelapan belas menggunakan cmdlet **New-AzureRmVmsConfig** untuk membuat objek konfigurasi VMSS dan menyimpan hasilnya dalam variabel bernama $VMSS.
* Perintah kesembilan belas menggunakan cmdlet **New-AzureRmVmss** untuk membuat VMSS.

## PARAMETERS

### -AllocationMethod
Metode alokasi untuk Alamat IP Publik Kumpulan Skala (Statis atau Dinamis).  Jika tidak ada nilai yang disediakan, alokasi akan statis.

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

### -BackendPoolName
Nama kumpulan alamat backend yang digunakan dalam penyeimbang muat untuk Kumpulan Skala ini.  Jika tidak ada nilai yang disediakan, kumpulan backend baru akan dibuat, dengan nama yang sama seperti Kumpulan Skala.

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
Nomor port backend yang digunakan oleh penyeimbang muatan Kumpulan Skala untuk berkomunikasi dengan VM dalam Kumpulan Skala.  Jika tidak ada nilai yang ditentukan, port 3389 dan 5985 akan digunakan untuk Windows VMS, dan port 22 akan digunakan untuk VM Linux.

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

### -Kredensial
Kredensial administrator (nama pengguna dan kata sandi) untuk VM dalam Kumpulan Skala ini.

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
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DomainNameLabel
Label nama domain untuk nama domain Fully-Qualified publik (FQDN) untuk Kumpulan Skala ini. Ini adalah komponen pertama nama domain yang ditetapkan secara otomatis ke Kumpulan Skala. Nama Domain yang ditetapkan secara otomatis menggunakan formulir (<DomainNameLabel>.<Location>. cloudapp.azure.com). Jika tidak ada nilai yang disediakan, label nama domain default akan menjadi penggandaan dan <ScaleSetName> <ResourceGroupName>.

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
Nama kumpulan alamat frontend untuk digunakan dalam penyeimbang muatan Kumpulan Skala.  Jika tidak ada nilai yang disediakan, Kumpulan Alamat Frontend baru akan dibuat, dengan nama yang sama seperti kumpulan skala.

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

### -ImageName
Nama gambar untuk VM dalam Kumpulan Skala ini. Jika tidak ada nilai yang disediakan, gambar "Windows Server 2016 DataCenter" akan digunakan.

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
Jumlah gambar VM dalam Kumpulan Skala.  Jika tidak ada nilai yang disediakan, 2 instans akan dibuat.

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
Nama penyeimbang muatan yang digunakan dengan Kumpulan Skala ini.  Penyeimbang muatan baru menggunakan nama yang sama seperti Kumpulan Skala akan dibuat jika tidak ada nilai yang ditentukan.

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
Lokasi Azure tempat Kumpulan Skala ini akan dibuat.  Jika tidak ada nilai yang ditentukan, lokasi akan disimpulkan dari lokasi sumber daya lain yang dirujuk dalam parameter.

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

### -NatBackendPort
Port backend untuk penerjemahan alamat jaringan masuk.

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

### -PublicIpAddressName
Nama Alamat IP publik untuk digunakan dengan kumpulan skala ini.  Alamat IP Publik baru dengan nama yang sama seperti Kumpulan Skala akan dibuat jika tidak ada nilai yang disediakan.

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
Menentukan nama grup sumber daya VMSS.  Jika tidak ada nilai yang ditentukan, ResourceGroup baru akan dibuat menggunakan nama yang sama seperti Kumpulan Skala.

```yaml
Type: System.String
Parameter Sets: DefaultParameter
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: System.String
Parameter Sets: SimpleParameterSet
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SecurityGroupName
Nama grup keamanan jaringan untuk diterapkan ke Kumpulan Skala ini.  Jika tidak ada nilai yang disediakan, grup keamanan jaringan default dengan nama yang sama seperti Kumpulan Skala akan dibuat dan diterapkan ke Kumpulan Skala.

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
Gunakan ini untuk membuat kumpulan Skala dalam grup penempatan tunggal, defaultnya adalah beberapa grup

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
Prefiks alamat Subnet yang akan digunakan oleh ScaleSet ini. Pengaturan Default Subnet (192.168.1.0/24) akan diterapkan jika tidak ada nilai yang disediakan.

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
Nama subnet yang akan digunakan dengan Kumpulan Skala ini.  Subnet baru akan dibuat dengan nama yang sama seperti Kumpulan Skala jika tidak ada nilai yang disediakan.

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
Jika parameter ada, maka VM dalam kumpulan skala adalah(adalah) menetapkan identitas sistem terkelola yang dihasilkan secara otomatis.

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
Mode kebijakan pemutakhiran untuk instans VM dalam Kumpulan Skala ini.  Kebijakan pemutakhiran dapat menentukan pemutakhiran Otomatis, Manual, atau Rolling.

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
Nama identitas layanan terkelola yang harus ditetapkan ke VM dalam kumpulan skala.

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

### -VirtualMachineScaleSet
Menentukan objek **VirtualMachineScaleSet** yang berisi properti VMSS yang dibuat cmdlet ini.

```yaml
Type: Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet
Parameter Sets: DefaultParameter
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VirtualNetworkName
Nama untuk Virtual Network digunakan dengan kumpulan skala ini.  Jika tidak ada nilai yang disertakan, jaringan virtual baru dengan nama yang sama seperti Kumpulan Skala akan dibuat.

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
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

```yaml
Type: System.String
Parameter Sets: SimpleParameterSet
Aliases: Name

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VmSize
Ukuran instans VM dalam kumpulan skala ini.  Ukuran default (Standard_DS1_v2) akan digunakan jika tidak ada Ukuran yang ditentukan.

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
Prefiks alamat untuk jaringan virtual yang digunakan dengan Kumpulan Skala ini.  Pengaturan prefiks alamat jaringan virtual default (192.168.0.0/16) akan digunakan jika tidak ada nilai yang disediakan.

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
Daftar zona ketersediaan yang mencantumkan IP yang dialokasikan untuk sumber daya yang diperlukan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet
Parameter: VirtualMachineScaleSet (ByValue)

### System.Collections.Generic.List'1[[System.String, mscorlib, Version=4.0.0.0, Culture=netral, PublicKeyToken=b77a5c561934e089]]

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet

## NOTES

## RELATED LINKS

[Get-AzureRmVms](./Get-AzureRmVmss.md)

[Hapus-AzureRmVms](./Remove-AzureRmVmss.md)

[Mulai ulang-AzureRmVms](./Restart-AzureRmVmss.md)

[Set-AzureRmVms](./Set-AzureRmVmss.md)

[Mulai AzureRmVms](./Start-AzureRmVmss.md)

[Stop-AzureRmVms](./Stop-AzureRmVmss.md)

[Pembaruan-AzureRmVms](./Update-AzureRmVmss.md)


