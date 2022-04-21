---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/get-azloadbalancerbackendaddressinboundnatruleportmapping
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzLoadBalancerBackendAddressInboundNatRulePortMapping.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Get-AzLoadBalancerBackendAddressInboundNatRulePortMapping.md
ms.openlocfilehash: 5fe55b1b6ab012564b7b7e0d8411c0a413bd127c
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142699300"
---
# Get-AzLoadBalancerBackendAddressInboundNatRulePortMapping

## SYNOPSIS
Get-AzLoadBalancerBackendAddressInboundNatRulePortMapping mengambil daftar pemetaan port aturan nat masuk untuk satu alamat backend.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.network/get-azloadbalancerbackendaddressinboundnatruleportmapping) untuk informasi terbaru.

## SYNTAX

### GetByNameParameterSet
```
Get-AzLoadBalancerBackendAddressPool -ResourceGroupName <String> -LoadBalancerName <String> [-Name <String>] [-IpAddress <String>]
 [-NetworkInterfaceIpConfigurationId <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### GetByParentObjectParameterSet
```
Get-AzLoadBalancerBackendAddressPool [-Name <String>] -LoadBalancer <PSLoadBalancer> [-IpAddress <String>]
 [-NetworkInterfaceIpConfigurationId <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### GetByResourceIdParameterSet
```
Get-AzLoadBalancerBackendAddressPool -ResourceId <String> [-IpAddress <String>]
 [-NetworkInterfaceIpConfigurationId <String>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Get-AzLoadBalancerBackendAddressPool mengambil daftar pemetaan port aturan nat masuk untuk satu alamat backend.

## EXAMPLES

### Contoh 1
```powershell
## Get inbound nat rule port mapping by NIC id
PS C:\>Get-AzLoadBalancerBackendAddressInboundNatRulePortMapping -ResourceGroupName $rgname -LoadBalancerName $lbName -NetworkInterfaceIpConfigurationId $ipconfig.Id -Name pool1
```

### Contoh 2
```powershell
## Get inbound nat rule port mapping by ip address
PS C:\>$testIpAddress1 = "10.0.0.5"
PS C:\>Get-AzLoadBalancerBackendAddressInboundNatRulePortMapping -ResourceGroupName $rgname -LoadBalancerName $lbName -Name $backendAddressPoolName -IpAddress $testIpAddress1
```

### Contoh 3
```powershell
## Get inbound nat rule port mapping by ip address and load balancer object
PS C:\>$slb = Get-AzLoadBalancer -Name "MyLoadBalancer" -ResourceGroupName "MyResourceGroup"
PS C:\>Get-AzLoadBalancerBackendAddressInboundNatRulePortMapping -LoadBalancer $slb -Name $backendAddressPoolName -IpAddress $testIpAddress1
```

### Contoh 4
```powershell
## Get inbound nat rule port mapping by ip address and backend pool id
PS C:\> Get-AzLoadBalancerBackendAddressInboundNatRulePortMapping -ResourceId $backendPool1.Id -IpAddress $testIpAddress1
```

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LoadBalancer
Menentukan penyeimbang muatan yang memiliki kumpulan alamat backend

```yaml
Type: PSLoadBalancer
Parameter Sets: GetByParentObjectParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -LoadBalancerName
Nama penyeimbang beban.

```yaml
Type: String
Parameter Sets: GetByNameParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama kumpulan alamat backend.

```yaml
Type: String
Parameter Sets: GetByNameParameterSet, GetByParentObjectParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya penyeimbang muat.

```yaml
Type: String
Parameter Sets: GetByNameParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId

```yaml
Type: String
Parameter Sets: GetByResourceIdParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IpAddress

```yaml
Type: String
Parameter Sets:
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -NetworkInterfaceIpConfigurationId

```yaml
Type: String
Parameter Sets:
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

### Microsoft.Azure.Commands.Network.Models.PSLoadBalancer

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSInboundNatRulePortMapping

## NOTES

## RELATED LINKS

[Get-AzLoadBalancer](./Get-AzLoadBalancer.md)
