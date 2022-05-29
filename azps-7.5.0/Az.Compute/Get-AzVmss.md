---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
ms.assetid: FC6BC096-DBC4-48DA-A366-B87EB18A0496
online version: https://docs.microsoft.com/powershell/module/az.compute/get-azvmss
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Get-AzVmss.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Get-AzVmss.md
ms.openlocfilehash: 09048745454c1bff47ed39c7345b5e8dafb5d3b2
ms.sourcegitcommit: 321c644cf2161807a71e1af318fc5c5311d22e25
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/25/2022
ms.locfileid: "145798352"
---
# Dapatkan-AzVmss

## SYNOPSIS
Mendapatkan properti VMSS.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.compute/get-azvmss) untuk informasi terbaru.

## SYNTAX

### DefaultParameter (Default)
```
Get-AzVmss [[-ResourceGroupName] <String>] [[-VMScaleSetName] <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### FriendMethod
```
Get-AzVmss [[-ResourceGroupName] <String>] [[-VMScaleSetName] <String>] [-InstanceView] [-UserData]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### OSUpgradeHistoryMethodParameter
```
Get-AzVmss [[-ResourceGroupName] <String>] [[-VMScaleSetName] <String>] [-OSUpgradeHistory]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzVmss** mendapatkan tampilan model dan instans Dari Virtual Machine Scale Set (VMSS).
Tampilan model adalah properti yang ditentukan pengguna dari set skala komputer virtual.
Tampilan instans adalah status tingkat instans dari set skala komputer virtual.
Tentukan parameter *InstanceView* untuk hanya mendapatkan tampilan instans dari set skala komputer virtual.

## EXAMPLES

### Contoh 1: Mendapatkan properti VMSS
```powershell
Get-AzVmss -ResourceGroupName "Group001" -VMScaleSetName "VMSS001"
```

```output
ResourceGroupName                           : Group001
Sku                                         :
  Name                                      : Standard_DS1_v2
  Tier                                      : Standard
  Capacity                                  : 2
UpgradePolicy                               :
  Mode                                      : Manual
VirtualMachineProfile                       :
  OsProfile                                 :
    ComputerNamePrefix                      : test
    AdminUsername                           : contoso
    WindowsConfiguration                    :
      ProvisionVMAgent                      : True
      EnableAutomaticUpdates                : True
  StorageProfile                            :
    ImageReference                          :
      Publisher                             : MicrosoftWindowsServer
      Offer                                 : WindowsServer
      Sku                                   : 2016-Datacenter
      Version                               : latest
    OsDisk                                  :
      Caching                               : None
      CreateOption                          : FromImage
      ManagedDisk                           :
        StorageAccountType                  : Premium_LRS
  NetworkProfile                            :
    NetworkInterfaceConfigurations[0]       :
      Name                                  : Group001
      Primary                               : True
      EnableAcceleratedNetworking           : False
      NetworkSecurityGroup                  :
        Id                                  : /subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/Group001
/providers/Microsoft.Network/networkSecurityGroups/Group001
      DnsSettings                           :
      IpConfigurations[0]                   :
        Name                                : Group001
        Subnet                              :
          Id                                : /subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/group001
/providers/Microsoft.Network/virtualNetworks/Group001/subnets/Group001
        PrivateIPAddressVersion             : IPv4
        LoadBalancerBackendAddressPools[0]  :
          Id                                : /subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/group001
/providers/Microsoft.Network/loadBalancers/Group001/backendAddressPools/Group001
        LoadBalancerInboundNatPools[0]      :
          Id                                : /subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/group001
/providers/Microsoft.Network/loadBalancers/Group001/inboundNatPools/Group001
        LoadBalancerInboundNatPools[1]      :
          Id                                : /subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/group001
/providers/Microsoft.Network/loadBalancers/Group001/inboundNatPools/Group001
      EnableIPForwarding                    : False
ProvisioningState                           : Succeeded
Overprovision                               : True
UniqueId                                    : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
SinglePlacementGroup                        : False
Id                                          : /subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx/resourceGroups/Group001/
providers/Microsoft.Compute/virtualMachineScaleSets/VMSS001
Name                                        : VMSS001
Type                                        : Microsoft.Compute/virtualMachineScaleSets
Location                                    : eastus
Tags                                        : {}
```

Perintah ini mendapatkan properti VMSS bernama VMSS001 yang termasuk dalam grup sumber daya bernama Group001.
Karena perintah tidak menentukan parameter sakelar *InstanceView* , cmdlet mendapatkan tampilan model dari set skala komputer virtual.

### Contoh 2: Mendapatkan semua Vm dalam grup sumber daya
```powershell
Get-AzVmss -ResourceGroupName "Group001"
```

```output
ResourceGroupName                               Name       Location             Sku Capacity ProvisioningState
-----------------                               ----       --------             --- -------- -----------------
Group001                                       VMSS001      eastus Standard_DS1_v2        2         Succeeded
Group001                                       VMSS002      eastus     Standard_A1        2         Succeeded
```

Dapatkan semua Vm dalam grup sumber daya "Group001"

### Contoh 3: Mendapatkan semua Vm dalam langganan
```powershell
Get-AzVmss
```

```output
ResourceGroupName                               Name       Location             Sku Capacity ProvisioningState
-----------------                               ----       --------             --- -------- -----------------
Group001                                       VMSS001      eastus Standard_DS1_v2        2         Succeeded
Group001                                       VMSS002      eastus     Standard_A1        2         Succeeded
Group002                                       VMSS003      eastus     Standard_A1        1         Succeeded
Group002                                       VMSS004      eastus Standard_DS1_v2        2         Succeeded
```

Dapatkan semua Vm dalam langganan.

### Contoh 4: Dapatkan semua Vm menggunakan pemfilteran
```powershell
Get-AzVmss -Name VMSS00*
```

```output
ResourceGroupName                               Name       Location             Sku Capacity ProvisioningState
-----------------                               ----       --------             --- -------- -----------------
Group001                                       VMSS001      eastus Standard_DS1_v2        2         Succeeded
Group001                                       VMSS002      eastus     Standard_A1        2         Succeeded
Group002                                       VMSS003      eastus     Standard_A1        1         Succeeded
Group002                                       VMSS004      eastus Standard_DS1_v2        2         Succeeded
```

Dapatkan semua Vm dalam langganan yang dimulai dengan "VMSS00".

### Contoh 5: Dapatkan Vm dengan nilai UserData
```powershell
Get-AzVmss -ResourceGroupName <RESOURCE GROUP NAME> -VMScaleSetName <VMSS NAME> -InstanceView:$false -UserData;
```

```output
ResourceGroupName                           : <RESOURCE GROUP NAME>
Sku                                         :
  Name                                      : Standard_DS1_v2
  Tier                                      : Standard
  Capacity                                  : 2
UpgradePolicy                               :
  Mode                                      : Manual
ProvisioningState                           : Succeeded
Overprovision                               : True
DoNotRunExtensionsOnOverprovisionedVMs      : False
UniqueId                                    : <UNIQUE ID>
SinglePlacementGroup                        : False
Id                                          : /subscriptions/<SUBSCRIPTION ID>/resourceGroups/<RESOURCE GROUP NAME>/providers/Microsoft.Compute/virtualMachineScaleSets/<VMSS NAME>
Name                                        : usdvmss
Type                                        : Microsoft.Compute/virtualMachineScaleSets
Location                                    : eastus
Tags                                        :
{"azsecpack":"nonprod","platformsettings.host_environment.service.platform_optedin_for_rootcerts":"true"}
VirtualMachineProfile                       :
  OsProfile                                 :
    ComputerNamePrefix                      : <PREFIX>
    AdminUsername                           : <USERNAME>
    WindowsConfiguration                    :
      ProvisionVMAgent                      : True
      EnableAutomaticUpdates                : True
  StorageProfile                            :
    ImageReference                          :
      Publisher                             : MicrosoftWindowsServer
      Offer                                 : WindowsServer
      Sku                                   : 2016-Datacenter
      Version                               : latest
    OsDisk                                  :
      Caching                               : None
      CreateOption                          : FromImage
      DiskSizeGB                            : 127
      OsType                                : Windows
      ManagedDisk                           :
        StorageAccountType                  : Premium_LRS
  NetworkProfile                            :
    NetworkInterfaceConfigurations[0]       :
      Name                                  : <VMSS NAME>
      Primary                               : True
      EnableAcceleratedNetworking           : False
      DnsSettings                           :
      IpConfigurations[0]                   :
        Name                                : <VMSS NAME>
        Subnet                              :
          Id                                : /subscriptions/<SUBSCRIPTION ID>/resourceGroups/<RESOURCE GROUP NAME>/providers/Microsoft.Network/virtualNetworks/<VMSS NAME>/subnets/<VMSS NAME>
        PrivateIPAddressVersion             : IPv4
        LoadBalancerBackendAddressPools[0]  :
          Id                                : /subscriptions/<SUBSCRIPTION ID>/resourceGroups/<RESOURCE GROUP NAME>/providers/Microsoft.Network/loadBalancers/<VMSS NAME>/backendAddressPools/<VMSS NAME>
        LoadBalancerInboundNatPools[0]      :
          Id                                : /subscriptions/<SUBSCRIPTION ID>/resourceGroups/<RESOURCE GROUP NAME>/providers/Microsoft.Network/loadBalancers/<VMSS NAME>/inboundNatPools/<VMSS NAME>
        LoadBalancerInboundNatPools[1]      :
          Id                                : /subscriptions/<SUBSCRIPTION ID>/resourceGroups/<RESOURCE GROUP NAME>/providers/Microsoft.Network/loadBalancers/<VMSS NAME>/inboundNatPools/<VMSS NAME>
      EnableIPForwarding                    : False
  ExtensionProfile                          :
    Extensions[0]                           :
      Name                                  : Microsoft.Azure.Security.AntimalwareSignature.AntimalwareConfiguration
      Publisher                             : Microsoft.Azure.Security.AntimalwareSignature
      Type                                  : AntimalwareConfiguration
      TypeHandlerVersion                    : 2.0
      AutoUpgradeMinorVersion               : True
      EnableAutomaticUpgrade                : True
      Settings                              : {}
    Extensions[1]                           :
      Name                                  : Microsoft.Azure.Geneva.GenevaMonitoring
      Publisher                             : Microsoft.Azure.Geneva
      Type                                  : GenevaMonitoring
      TypeHandlerVersion                    : 2.0
      AutoUpgradeMinorVersion               : True
      EnableAutomaticUpgrade                : True
      Settings                              : {}
  UserData                                  : dQBwAGQAYQB0AGUAIAB2AG0AcwBzAA==
```

Nilai UserData harus dikodekan Base64. Perintah ini mengasumsikan Anda telah membuat Vm dengan nilai UserData. 

## PARAMETERS

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

### -InstanceView
Menunjukkan bahwa cmdlet ini hanya mendapatkan tampilan instans dari set skala komputer virtual.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: FriendMethod
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OSUpgradeHistory
Menunjukkan bahwa cmdlet ini mencantumkan riwayat peningkatan os dari set skala komputer virtual.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: OSUpgradeHistoryMethodParameter
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama Grup Sumber Daya VMSS.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -UserData
UserData untuk Vmss, yang akan dikodekan base-64. Pelanggan tidak boleh meneruskan rahasia apa pun di sini.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: FriendMethod
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VMScaleSetName
Spesies nama VMSS.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Name

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet

## NOTES

## RELATED LINKS

[Baru-AzVmss](./New-AzVmss.md)

[Hapus-AzVmss](./Remove-AzVmss.md)

[Hidupkan ulang-AzVmss](./Restart-AzVmss.md)

[Set-AzVmss](./Set-AzVmss.md)

[Start-AzVmss](./Start-AzVmss.md)

[Stop-AzVmss](./Stop-AzVmss.md)

[Update-AzVmss](./Update-AzVmss.md)


