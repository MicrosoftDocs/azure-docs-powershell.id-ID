---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
ms.assetid: 3E7B9EFA-8BC2-46EB-9AD7-43EAB7FF3891
online version: https://docs.microsoft.com/powershell/module/az.compute/set-azvmssosprofile
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Set-AzVmssOsProfile.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Set-AzVmssOsProfile.md
ms.openlocfilehash: 9ceb914dbf637672a8c2790bb96cc360e9b81bf1
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144215387"
---
# Set-AzVmssOsProfile

## SYNOPSIS
Mengatur properti profil sistem operasi VMSS.

## SYNTAX

```
Set-AzVmssOsProfile [-VirtualMachineScaleSet] <PSVirtualMachineScaleSet> [[-ComputerNamePrefix] <String>]
 [[-AdminUsername] <String>] [[-AdminPassword] <String>] [[-CustomData] <String>]
 [[-WindowsConfigurationProvisionVMAgent] <Boolean>] [-LinuxConfigurationProvisionVMAgent <Boolean>]
 [[-WindowsConfigurationEnableAutomaticUpdate] <Boolean>] [[-TimeZone] <String>]
 [[-AdditionalUnattendContent] <AdditionalUnattendContent[]>] [[-Listener] <WinRMListener[]>]
 [[-LinuxConfigurationDisablePasswordAuthentication] <Boolean>] [[-PublicKey] <SshPublicKey[]>]
 [[-Secret] <VaultSecretGroup[]>] [-WindowsConfigurationPatchMode <String>]
 [-LinuxConfigurationPatchMode <String>] [-EnableHotpatching] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzVmssOsProfile** mengatur properti profil sistem operasi Set Skala Komputer Virtual.

## EXAMPLES

### Contoh 1: Mengatur properti profil sistem operasi untuk VMSS
```powershell
$vmss = New-AzVmssConfig -Location $Loc -SkuCapacity 2 -SkuName "Standard_A0" -UpgradePolicyMode "Automatic" -NetworkInterfaceConfiguration $NetCfg
Set-AzVmssOSProfile -VirtualMachineScaleSet $vmss -ComputerNamePrefix "Test" -AdminUsername $AdminUsername -AdminPassword $AdminPassword
```

Perintah ini mengatur properti profil sistem operasi untuk objek $vmss.
Perintah mengatur awalan nama komputer untuk semua instans komputer virtual di VMSS untuk Menguji dan menyediakan nama pengguna dan kata sandi administrator.

### Contoh 2: Atur properti profil sistem operasi untuk Vm dalam mode Fleksibel dengan Hotpatching diaktifkan.
```powershell
# Setup variables.
$loc = "eastus";
$rgname = "<Resource Group Name>";
$vmssName = "myVmssSlb";
$vmNamePrefix = "vmSlb";
$vmssInstanceCount = 5;
$vmssSku = "Standard_DS1_v2";
$vnetname = "myVnet";
$vnetAddress = "10.0.0.0/16";
$subnetname = "default-slb";
$subnetAddress = "10.0.2.0/24";
$securePassword = "<Password>" | ConvertTo-SecureString -AsPlainText -Force;  
$cred = New-Object System.Management.Automation.PSCredential ("<Username>", $securePassword);

# VMSS Flex requires explicit outbound access.
# Create a virtual network.
$frontendSubnet = New-AzVirtualNetworkSubnetConfig -Name $subnetname -AddressPrefix $subnetAddress;
$virtualNetwork = New-AzVirtualNetwork -Name $vnetname -ResourceGroupName $rgname -Location $loc -AddressPrefix $vnetAddress -Subnet $frontendSubnet;

# Create a public IP address.
$publicIP = New-AzPublicIpAddress `
    -ResourceGroupName $rgname `
    -Location $loc `
    -AllocationMethod Static `
    -Sku "Standard" `
    -IpAddressVersion "IPv4" `
    -Name "myLBPublicIP";

# Create a frontend and backend IP pool.
$frontendIP = New-AzLoadBalancerFrontendIpConfig `
    -Name "myFrontEndPool" `
    -PublicIpAddress $publicIP;

$backendPool = New-AzLoadBalancerBackendAddressPoolConfig -Name "myBackEndPool" ;

# Create the load balancer.
$lb = New-AzLoadBalancer `
    -ResourceGroupName $rgname `
    -Name "myLoadBalancer" `
    -Sku "Standard" `
    -Tier "Regional" `
    -Location $loc `
    -FrontendIpConfiguration $frontendIP `
    -BackendAddressPool $backendPool;

# Create a load balancer health probe for TCP port 80.
Add-AzLoadBalancerProbeConfig -Name "myHealthProbe" `
    -LoadBalancer $lb `
    -Protocol TCP `
    -Port 80 `
    -IntervalInSeconds 15 `
    -ProbeCount 2;

# Create a load balancer rule to distribute traffic on port TCP 80.
# The health probe from the previous step is used to make sure that traffic is
# only directed to healthy VM instances.
Add-AzLoadBalancerRuleConfig `
    -Name "myLoadBalancerRule" `
    -LoadBalancer $lb `
    -FrontendIpConfiguration $lb.FrontendIpConfigurations[0] `
    -BackendAddressPool $lb.BackendAddressPools[0] `
    -Protocol TCP `
    -FrontendPort 80 `
    -BackendPort 80 `
    -DisableOutboundSNAT `
    -Probe (Get-AzLoadBalancerProbeConfig -Name "myHealthProbe" -LoadBalancer $lb);

# Add outbound connectivity rule.
Add-AzLoadBalancerOutboundRuleConfig `
    -Name "outboundrule" `
    -LoadBalancer $lb `
    -AllocatedOutboundPort '10000' `
    -Protocol 'All' `
    -IdleTimeoutInMinutes '15' `
    -FrontendIpConfiguration $lb.FrontendIpConfigurations[0] `
    -BackendAddressPool $lb.BackendAddressPools[0];

# Update the load balancer configuration.
Set-AzLoadBalancer -LoadBalancer $lb;

# Create IP address configurations.
# Instances will require explicit outbound connectivity, for example
#   - NAT Gateway on the subnet (recommended)
#   - Instances in backend pool of Standard LB with outbound connectivity rules
#   - Public IP address on each instance
# See aka.ms/defaultoutboundaccess for more info.
$ipConfig = New-AzVmssIpConfig `
    -Name "myIPConfig" `
    -SubnetId $virtualNetwork.Subnets[0].Id `
    -LoadBalancerBackendAddressPoolsId $lb.BackendAddressPools[0].Id `
    -Primary;

# Create a config object.
# The Vmss config object stores the core information for creating a scale set.
$vmssConfig = New-AzVmssConfig `
    -Location $loc `
    -SkuCapacity $vmssInstanceCount `
    -SkuName $vmssSku `
    -OrchestrationMode 'Flexible' `
    -PlatformFaultDomainCount 1;

# Reference a virtual machine image from the gallery.
Set-AzVmssStorageProfile $vmssConfig `
    -OsDiskCreateOption "FromImage" `
    -ImageReferencePublisher "MicrosoftWindowsServer" `
    -ImageReferenceOffer "WindowsServer" `
    -ImageReferenceSku "2022-datacenter-azure-edition-core-smalldisk" `
    -ImageReferenceVersion "latest";  

# Set up information for authenticating with the virtual machine.
Set-AzVmssOsProfile $vmssConfig `
    -AdminUsername $cred.UserName `
    -AdminPassword $cred.Password `
    -ComputerNamePrefix $vmNamePrefix `
    -WindowsConfigurationProvisionVMAgent $true `
    -WindowsConfigurationPatchMode "AutomaticByPlatform" `
    -EnableHotpatching;

# Attach the virtual network to the config object.
Add-AzVmssNetworkInterfaceConfiguration `
    -VirtualMachineScaleSet $vmssConfig `
    -Name "network-config" `
    -Primary $true `
    -IPConfiguration $ipConfig `
    -NetworkApiVersion '2020-11-01';

# Define the Application Health extension properties.
$publicConfig = @{"protocol" = "http"; "port" = 80; "requestPath" = "/healthEndpoint"};
$extensionName = "myHealthExtension";
$extensionType = "ApplicationHealthWindows";
$publisher = "Microsoft.ManagedServices";
# Add the Application Health extension to the scale set model.
Add-AzVmssExtension -VirtualMachineScaleSet $vmssConfig `
    -Name $extensionName `
    -Publisher $publisher `
    -Setting $publicConfig `
    -Type $extensionType `
    -TypeHandlerVersion "1.0" `
    -AutoUpgradeMinorVersion $True;

# Create the virtual machine scale set.
$vmss = New-AzVmss `
    -ResourceGroupName $rgname `
    -Name $vmssName `
    -VirtualMachineScaleSet $vmssConfig;
```


## PARAMETERS

### -AdditionalUnattendContent
Menentukan objek isi tak terjaga.
Anda dapat menggunakan Add-AzVMAdditionalUnattendContent untuk membuat objek.

```yaml
Type: Microsoft.Azure.Management.Compute.Models.AdditionalUnattendContent[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 8
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AdminPassword
Menentukan kata sandi administrator yang akan digunakan untuk semua instans komputer virtual di VMSS.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -AdminUsername
Menentukan nama akun administrator yang akan digunakan untuk semua instans komputer virtual di VMSS. <br>
**pembatasan Windows-saja:** Tidak dapat berakhiran \".\" <br>
**Nilai yang tidak diizinkan:** \" administrator\", \"admin\", \"pengguna\", \"user1\", \"menguji\", \"user2\", \"test1\", \"user3\", \"admin1\", \"1\", \"123\", \"a\", \"actuser\", adm\", \"\"admin2\", \"aspnet\", \"cadangan\", \"konsol\", \"david\", \"tamu\", \"john\", \"pemilik\", \"root\", \"server\", \"sql\", \"dukungan \", \"support_388945a0\", \"sys\", \"test2\", \"test3\", \"user4\", \"user5\". <br>
**Panjang minimum (Linux):** 1 karakter <br>
**Panjang maksimum (Linux):** 64 karakter <br>
**Panjang maksimum (Windows):** 20 karakter  <br>
<li> Untuk daftar pengguna sistem bawaan di Linux yang tidak boleh digunakan di bidang ini, lihat [Memilih Nama Pengguna untuk Linux di Azure](https://docs.microsoft.com/azure/devops/organizations/settings/naming-restrictions).

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

### -ComputerNamePrefix
Menentukan awalan nama komputer untuk semua instans komputer virtual di VMSS.
Panjang nama komputer harus 1 hingga 15 karakter.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -CustomData
Menentukan string data kustom yang dikodekan base-64.
Ini didekodekan ke array biner yang disimpan sebagai file pada komputer virtual.
Panjang maksimum array biner adalah 65535 byte. <br>
Untuk menggunakan cloud-init untuk VM Anda, lihat [Menggunakan cloud-init untuk menyesuaikan VM Linux selama pembuatan](/azure/virtual-machines/linux/tutorial-automate-vm-deployment).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -EnableHotpatching
Memungkinkan pelanggan untuk menambal Azure Vm mereka tanpa memerlukan boot ulang. Untuk enableHotpatching, 'provisionVMAgent' harus diatur ke true dan 'patchMode' harus diatur ke 'AutomaticByPlatform'.

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

### -LinuxConfigurationDisablePasswordAuthentication
Menunjukkan bahwa cmdlet ini menonaktifkan autentikasi kata sandi.

```yaml
Type: System.Nullable`1[System.Boolean]
Parameter Sets: (All)
Aliases:

Required: False
Position: 10
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -LinuxConfigurationPatchMode
Menentukan mode Patching Tamu VM ke komputer virtual IaaS atau komputer virtual yang terkait dengan set skala komputer virtual dengan OrchestrationMode sebagai Flexible.<br /><br /> Potensi nilai:<br /><br /> **ImageDefault** - Konfigurasi patching default komputer virtual digunakan. <br /><br /> **AutomaticByPlatform** - Komputer virtual akan diperbarui secara otomatis oleh platform. Properti provisionVMAgent harus benar

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

### -LinuxConfigurationProvisionVMAgent
Menunjukkan apakah agen komputer virtual harus disediakan pada komputer virtual. <br><br> Ketika properti ini tidak ditentukan dalam isi permintaan, perilaku default adalah mengaturnya ke true.  Ini akan memastikan bahwa Agen VM diinstal pada VM sehingga ekstensi dapat ditambahkan ke VM nanti

```yaml
Type: System.Nullable`1[System.Boolean]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Listener
Menentukan pendengar Windows Remote Management (WinRM).
Ini memungkinkan Windows PowerShell jarak jauh.
Anda dapat menggunakan cmdlet Add-AzVmssWinRMListener untuk membuat pendengar.

```yaml
Type: Microsoft.Azure.Management.Compute.Models.WinRMListener[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 9
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PublicKey
Menentukan objek kunci umum Secure Shell (SSH).
Anda dapat menggunakan cmdlet Add-AzVMSshPublicKey untuk membuat objek.

```yaml
Type: Microsoft.Azure.Management.Compute.Models.SshPublicKey[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 11
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Rahasia
Menentukan objek rahasia yang berisi referensi sertifikat untuk ditempatkan pada komputer virtual.
Anda dapat menggunakan cmdlet Add-AzVmssSecret untuk membuat objek rahasia.

```yaml
Type: Microsoft.Azure.Management.Compute.Models.VaultSecretGroup[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 12
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Zona Waktu
Menentukan zona waktu komputer virtual. misalnya \"Waktu\" Standar Pasifik. <br>
Nilai yang mungkin dapat [TimeZoneInfo.Id](https://docs.microsoft.com/dotnet/api/system.timezoneinfo.id?#System_TimeZoneInfo_Id) nilai dari zona waktu yang dikembalikan oleh [TimeZoneInfo.GetSystemTimeZones](https://docs.microsoft.com/dotnet/api/system.timezoneinfo.getsystemtimezones).

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 7
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VirtualMachineScaleSet
Menentukan objek VMSS.
Anda dapat menggunakan cmdlet New-AzVmssConfig untuk membuat objek.

```yaml
Type: Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -WindowsConfigurationEnableAutomaticUpdate
Menunjukkan apakah komputer virtual di VMSS diaktifkan untuk pembaruan otomatis.

```yaml
Type: System.Nullable`1[System.Boolean]
Parameter Sets: (All)
Aliases:

Required: False
Position: 6
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -WindowsConfigurationPatchMode
Menentukan mode Patching Tamu VM ke komputer virtual IaaS atau komputer virtual yang terkait dengan set skala komputer virtual dengan OrchestrationMode sebagai Flexible.<br /><br /> Potensi nilai:<br /><br /> **Manual** - Anda mengontrol aplikasi patch ke komputer virtual. Anda melakukan ini dengan menerapkan patch secara manual di dalam VM. Dalam mode ini, pembaruan otomatis dinonaktifkan; properti WindowsConfiguration.enableAutomaticUpdates harus false<br /><br /> **AutomaticByOS** - Komputer virtual akan diperbarui secara otomatis oleh OS. Properti WindowsConfiguration.enableAutomaticUpdates harus benar. <br /><br /> **AutomaticByPlatform** - komputer virtual akan diperbarui secara otomatis oleh platform. Properti provisionVMAgent dan WindowsConfiguration.enableAutomaticUpdates harus benar


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

### -WindowsConfigurationProvisionVMAgent
Menunjukkan apakah agen komputer virtual harus disediakan pada komputer virtual di VMSS.

```yaml
Type: System.Nullable`1[System.Boolean]
Parameter Sets: (All)
Aliases:

Required: False
Position: 5
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Menunjukkan yang akan terjadi jika cmdlet dijalankan. Cmdlet tidak dijalankan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet

### System.String

### System.Nullable'1[[System.Boolean, System.Private.CoreLib, Version=4.0.0.0, Culture=netral, PublicKeyToken=7cec85d7bea7798e]]

### Microsoft.Azure.Management.Compute.Models.AdditionalUnattendContent[]

### Microsoft.Azure.Management.Compute.Models.WinRMListener[]

### Microsoft.Azure.Management.Compute.Models.SshPublicKey[]

### Microsoft.Azure.Management.Compute.Models.VaultSecretGroup[]

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet

## NOTES

## RELATED LINKS

[Add-AzVMAdditionalUnattendContent](./Add-AzVMAdditionalUnattendContent.md)

[Add-AzVmssWinRMListener](./Add-AzVmssWinRMListener.md)

[Add-AzVMSshPublicKey](./Add-AzVMSshPublicKey.md)

[Tambahkan-AzVmssSecret](./Add-AzVmssSecret.md)

[New-AzVmssConfig](./New-AzVmssConfig.md)


