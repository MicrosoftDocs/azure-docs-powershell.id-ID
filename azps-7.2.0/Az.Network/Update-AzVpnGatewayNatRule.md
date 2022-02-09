---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/update-azvpngatewaynatrule
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Update-AzVpnGatewayNatRule.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/Update-AzVpnGatewayNatRule.md
ms.openlocfilehash: eeb112cbdf77fc6d823a18ea387dfabc96189e27
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138311100"
---
# Update-AzVpnGatewayNatRule

## SYNOPSIS
Memperbarui aturan NAT yang terkait dengan VpnGateway.

## SYNTAX

### ByVpnGatewayNatRuleName (Default)
```
Update-AzVpnGatewayNatRule -ResourceGroupName <String> -ParentResourceName <String> -Name <String>
 [-Type <String>] [-Mode <String>] [-InternalMapping <String[]>] [-ExternalMapping <String[]>]
 [-InternalPortRange <String[]>] [-ExternalPortRange <String[]>] [-IpConfigurationId <String>] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByVpnGatewayNatRuleResourceId
```
Update-AzVpnGatewayNatRule -ResourceId <String> [-Type <String>] [-Mode <String>] [-InternalMapping <String[]>]
 [-ExternalMapping <String[]>] [-InternalPortRange <String[]>] [-ExternalPortRange <String[]>]
 [-IpConfigurationId <String>] [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### ByVpnGatewayNatRuleObject
```
Update-AzVpnGatewayNatRule -InputObject <PSVpnGatewayNatRule> [-Type <String>] [-Mode <String>]
 [-InternalMapping <String[]>] [-ExternalMapping <String[]>] [-InternalPortRange <String[]>]
 [-ExternalPortRange <String[]>] [-IpConfigurationId <String>] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Update-AzVpnGatewayNatRule** memperbarui aturan NAT yang terkait dengan VpnGateway.

## EXAMPLES

### Contoh

```powershell
PS C:\> New-AzResourceGroup -Location "West US" -Name "testRG"
PS C:\> $virtualWan = New-AzVirtualWan -ResourceGroupName testRG -Name myVirtualWAN -Location "West US"
PS C:\> $virtualHub = New-AzVirtualHub -VirtualWan $virtualWan -ResourceGroupName "testRG" -Name "westushub" -AddressPrefix "10.0.0.1/24"
PS C:\> New-AzVpnGateway -ResourceGroupName "testRG" -Name "testvpngw" -VirtualHubId $virtualHub.Id -BGPPeeringWeight 10 -VpnGatewayScaleUnit 2
PS C:\> $vpnGateway = Get-AzVpnGateway -ResourceGroupName "testRG" -Name "testvpngw"
PS C:\> New-AzVpnGatewayNatRule -ResourceGroupName $vpnGateway.ResourceGroupName -ParentResourceName $vpnGateway.Name -Name "testNatRule" -Type Static -Mode EgressSnat -InternalMapping "10.0.0.1/26" -ExternalMapping "192.168.0.0/26"
PS C:\> $natRule = Update-AzVpnGatewayNatRule -InputObject $vpnConnection -IpSecPolicy $ipsecPolicy
PS C:\> Update-AzVpnGatewayNatRule -InputObject $natRule -Type Dynamic -Mode IngressSnat

Type                      : Dynamic
Mode                      : IngressSnat
VpnConnectionProtocolType : IKEv2
InternalMappings          : 10.0.0.1/26
ExternalMappings          : 192.168.0.0/26
IpConfigurationId         :
IngressVpnSiteLinkConnections : [Microsoft.Azure.Commands.Network.Models.PSResourceId]
EgressVpnSiteLinkConnections  : [Microsoft.Azure.Commands.Network.Models.PSResourceId]
ProvisioningState         : Provisioned
Name                      : ps9709
Etag                      : W/"4580a2e2-2fab-4cff-88eb-92013a76b5a8"
Id                        : /subscriptions/{subscriptionId}/resourceGroups/testRg/providers/Microsoft.Network/vpnGateways/testvpngw/natRules/testNatRule
```

Opsi di atas akan membuat grup sumber daya, Virtual WAN, Virtual Network, Virtual Hub. Lalu, kami akan membuat VpnGateway di bawah Virtual Hub tersebut. Lalu, buat aturan NAT baru yang terkait dengan VpnGateway yang dibuat.
Menggunakan perintah ini: Update-AzVpnGatewayNatRule, perbarui aturan NAT.

## PARAMETERS

### -AsJob
Jalankan cmdlet di latar belakang

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

### -ExternalMapping
Daftar pemetaan eksternal subnet alamat IP privat untuk NAT

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ExternalPortRange
Daftar pemetaan rentang port eksternal untuk subnet NAT

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Objek VpnGatewayNatRule yang akan diperbarui.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSVpnGatewayNatRule
Parameter Sets: ByVpnGatewayNatRuleObject
Aliases: VpnGatewayNatRule

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -InternalMapping
Daftar pemetaan internal subnet alamat IP privat untuk NAT

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InternalPortRange
Daftar pemetaan rentang port internal untuk subnet NAT

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IpConfigurationId
ID Konfigurasi IP aturan NAT ini berlaku untuk

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

### -Mode
Arah NAT Sumber dari VPN NAT

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: EgressSnat, IngressSnat

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama sumber daya.

```yaml
Type: System.String
Parameter Sets: ByVpnGatewayNatRuleName
Aliases: ResourceName, VpnGatewayNatRuleName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ParentResourceName
Nama sumber daya induk.

```yaml
Type: System.String
Parameter Sets: ByVpnGatewayNatRuleName
Aliases: ParentVpnGatewayName, VpnGatewayName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: ByVpnGatewayNatRuleName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
Id sumber daya objek VpnGatewayNatRule yang akan dihapus.

```yaml
Type: System.String
Parameter Sets: ByVpnGatewayNatRuleResourceId
Aliases: VpnGatewayNatRuleResourceId

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tipe
Tipe aturan NAT untuk VPN NAT

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Static, Dynamic

Required: False
Position: Named
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
Default value: None
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Azure.Commands.Network.Models.PSVpnGatewayNatRule

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSVpnGatewayNatRule

## CATATAN

## RELATED LINKS
