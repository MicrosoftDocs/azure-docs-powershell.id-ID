---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Storage.Management.dll-Help.xml
Module Name: Az.Storage
online version: https://docs.microsoft.com/powershell/module/az.storage/add-azstorageaccountnetworkrule
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Add-AzStorageAccountNetworkRule.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Storage/Storage.Management/help/Add-AzStorageAccountNetworkRule.md
ms.openlocfilehash: c50362e3ab6f9fbfaf3b5e640fb994b551f27105
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144193891"
---
# Add-AzStorageAccountNetworkRule

## SYNOPSIS
 Menambahkan IpRules atau VirtualNetworkRules ke properti NetworkRule dari akun Storage

## SYNTAX

### NetWorkRuleString (Default)
```
Add-AzStorageAccountNetworkRule [-ResourceGroupName] <String> [-Name] <String>
 -VirtualNetworkResourceId <String[]> [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### IpRuleObject
```
Add-AzStorageAccountNetworkRule [-ResourceGroupName] <String> [-Name] <String> -IPRule <PSIpRule[]> [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### NetworkRuleObject
```
Add-AzStorageAccountNetworkRule [-ResourceGroupName] <String> [-Name] <String>
 -VirtualNetworkRule <PSVirtualNetworkRule[]> [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### ResourceAccessRuleObject
```
Add-AzStorageAccountNetworkRule [-ResourceGroupName] <String> [-Name] <String>
 -ResourceAccessRule <PSResourceAccessRule[]> [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### IpRuleString
```
Add-AzStorageAccountNetworkRule [-ResourceGroupName] <String> [-Name] <String> -IPAddressOrRange <String[]>
 [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ResourceAccessRuleString
```
Add-AzStorageAccountNetworkRule [-ResourceGroupName] <String> [-Name] <String> -TenantId <String>
 -ResourceId <String> [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Add-AzStorageAccountNetworkRule** menambahkan IpRules atau VirtualNetworkRules ke properti NetworkRule dari akun Storage

## EXAMPLES

### Contoh 1: Menambahkan beberapa IpRules dengan IPAddressOrRange
```
PS C:\>Add-AzStorageAccountNetworkRule -ResourceGroupName "myResourceGroup" -Name "mystorageaccount" -IPAddressOrRange "10.0.0.0/7","28.2.0.0/16"
```

Perintah ini menambahkan beberapa IpRules dengan IPAddressOrRange.

### Contoh 2: Menambahkan VirtualNetworkRule dengan VirtualNetworkResourceID
```
PS C:\>$subnet = Get-AzVirtualNetwork -ResourceGroupName "myResourceGroup" -Name "myvirtualnetwork" | Get-AzVirtualNetworkSubnetConfig
PS C:\>Add-AzStorageAccountNetworkRule -ResourceGroupName "myResourceGroup" -Name "mystorageaccount" -VirtualNetworkResourceId $subnet[0].Id
```

Perintah ini menambahkan VirtualNetworkRule dengan VirtualNetworkResourceID.

### Contoh 3: Menambahkan VirtualNetworkRules dengan VirtualNetworkRule Objects dari akun lain
```
PS C:\> $networkrule = Get-AzStorageAccountNetworkRuleSet -ResourceGroupName "myResourceGroup" -Name "mystorageaccount1"
PS C:\> Add-AzStorageAccountNetworkRule -ResourceGroupName "myResourceGroup" -Name "mystorageaccount2" -VirtualNetworkRule $networkrule.VirtualNetworkRules
```

Perintah ini menambahkan VirtualNetworkRules dengan VirtualNetworkRule Objects dari akun lain.

### Contoh 4: Tambahkan beberapa IpRule dengan objek IpRule, masukkan dengan JSON
```
PS C:\>Add-AzStorageAccountNetworkRule -ResourceGroupName "myResourceGroup" -Name "mystorageaccount" -IPRule (@{IPAddressOrRange="10.0.0.0/7";Action="allow"},@{IPAddressOrRange="28.2.0.0/16";Action="allow"})
```

Perintah ini menambahkan beberapa IpRule dengan objek IpRule, input dengan JSON.

### Contoh 5: Menambahkan aturan akses sumber daya
```
PS C:\>Add-AzStorageAccountNetworkRule -ResourceGroupName "myResourceGroup" -Name "mystorageaccount" -TenantId $tenantId -ResourceId $ResourceId
```

Perintah ini menambahkan aturan akses sumber daya dengan TenantId dan ResourceId.

### Contoh 6: Menambahkan semua aturan akses sumber daya dari satu akun penyimpanan ke akun penyimpanan lain
```
PS C:\> (Get-AzStorageAccountNetworkRuleSet -ResourceGroupName "myResourceGroup" -Name "mystorageaccount1").ResourceAccessRules | Add-AzStorageAccountNetworkRule -ResourceGroupName "myResourceGroup" -Name "mystorageaccount2"
```

Perintah ini mendapatkan semua aturan akses sumber daya dari satu akun penyimpanan, dan menambahkannya ke akun penyimpanan lain.

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

### -IPAddressOrRange
Array IpAddressOrRange, tambahkan IpRules dengan input IpAddressOrRange dan Tindakan default Izinkan ke Properti NetworkRule.

```yaml
Type: System.String[]
Parameter Sets: IpRuleString
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IPRule
Array objek IpRule untuk ditambahkan ke Properti NetworkRule.

```yaml
Type: Microsoft.Azure.Commands.Management.Storage.Models.PSIpRule[]
Parameter Sets: IpRuleObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Menentukan nama akun Storage.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: StorageAccountName, AccountName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceAccessRule
Storage Account NetworkRule ResourceAccessRules.

```yaml
Type: Microsoft.Azure.Commands.Management.Storage.Models.PSResourceAccessRule[]
Parameter Sets: ResourceAccessRuleObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya berisi akun Storage.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceId
Storage ResourceAccessRule ResourceId Akun dalam string.

```yaml
Type: System.String
Parameter Sets: ResourceAccessRuleString
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TenantId
Storage Account ResourceAccessRule TenantId dalam string.

```yaml
Type: System.String
Parameter Sets: ResourceAccessRuleString
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualNetworkResourceId
Array VirtualNetworkResourceId, akan menambahkan VirtualNetworkRule dengan input VirtualNetworkResourceId dan Tindakan default Izinkan ke Properti NetworkRule.

```yaml
Type: System.String[]
Parameter Sets: NetWorkRuleString
Aliases: SubnetId, VirtualNetworkId

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualNetworkRule
Array objek VirtualNetworkRule untuk ditambahkan ke Properti NetworkRule.

```yaml
Type: Microsoft.Azure.Commands.Management.Storage.Models.PSVirtualNetworkRule[]
Parameter Sets: NetworkRuleObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
Cmdlet tidak dijalankan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Azure.Commands.Management. Storage. Models.PSIpRule[]

### Microsoft.Azure.Commands.Management. Storage. Models.PSVirtualNetworkRule[]

## OUTPUTS

### Microsoft.Azure.Commands.Management. Storage. Models.PSVirtualNetworkRule

### Microsoft.Azure.Commands.Management. Storage. Models.PSIpRule

## NOTES

## RELATED LINKS
