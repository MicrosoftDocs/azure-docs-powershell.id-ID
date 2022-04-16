---
external help file: ''
Module Name: Az.Databricks
online version: https://docs.microsoft.com/powershell/module/az.databricks/new-azdatabricksworkspace
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Databricks/help/New-AzDatabricksWorkspace.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Databricks/help/New-AzDatabricksWorkspace.md
ms.openlocfilehash: a447e26ae4d6d16fc7b2d3132b388ef722142324
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142471985"
---
# New-AzDatabricksWorkspace

## SYNOPSIS
Membuat ruang kerja baru.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.databricks/new-azdatabricksworkspace) untuk informasi terbaru.

## SYNTAX

```
New-AzDatabricksWorkspace -Name <String> -ResourceGroupName <String> -Location <String>
 [-SubscriptionId <String>] [-AmlWorkspaceId <String>] [-EnableNoPublicIP] [-EncryptionKeyName <String>]
 [-EncryptionKeySource <KeySource>] [-EncryptionKeyVaultUri <String>] [-EncryptionKeyVersion <String>]
 [-LoadBalancerBackendPoolName <String>] [-LoadBalancerId <String>] [-ManagedResourceGroupName <String>]
 [-NatGatewayName <String>] [-PrepareEncryption] [-PrivateSubnetName <String>] [-PublicIPName <String>]
 [-PublicNetworkAccess <PublicNetworkAccess>] [-PublicSubnetName <String>]
 [-RequiredNsgRule <RequiredNsgRules>] [-RequireInfrastructureEncryption] [-Sku <String>] [-SkuTier <String>]
 [-StorageAccountName <String>] [-StorageAccountSku <String>] [-Tag <Hashtable>] [-VirtualNetworkId <String>]
 [-VnetAddressPrefix <String>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
Membuat ruang kerja baru.

## EXAMPLES

### Contoh 1: Membuat ruang kerja Databricks
```powershell
PS C:\> New-AzDatabricksWorkspace -Name workspace3miaeb -ResourceGroupName databricks-rg-rqb2yo -Location eastus -ManagedResourceGroupName databricks-group -Sku standard

Name            ResourceGroupName    Location Managed Resource Group ID
----            -----------------    -------- -------------------------
workspace3miaeb databricks-rg-rqb2yo eastus   /subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/databricks-rg-workspace3miaeb-3c0s2mbgrqv9k
```

Perintah ini membuat ruang kerja Databricks.

### Contoh 2: Membuat ruang kerja Databricks dengan jaringan virtual yang dikustomisasi
```powershell
PS C:\> $dlg = New-AzDelegation -Name dbrdl -ServiceName "Microsoft.Databricks/workspaces"
PS C:\> $rdpRule = New-AzNetworkSecurityRuleConfig -Name rdp-rule -Description "Allow RDP" -Access Allow -Protocol Tcp -Direction Inbound -Priority 100 -SourceAddressPrefix Internet -SourcePortRange * -DestinationAddressPrefix * -DestinationPortRange 3389
PS C:\> $networkSecurityGroup = New-AzNetworkSecurityGroup -ResourceGroupName databricks-rg-rqb2yo -Location eastus -Name nsg-test -SecurityRules $rdpRule
PS C:\> $privSubnet = New-AzVirtualNetworkSubnetConfig -Name priv-sub -AddressPrefix "10.0.1.0/24" -NetworkSecurityGroup $networkSecurityGroup -Delegation $dlg
PS C:\> $pubSubnet = New-AzVirtualNetworkSubnetConfig -Name pub-sub  -AddressPrefix "10.0.2.0/24" -NetworkSecurityGroup $networkSecurityGroup -Delegation $dlg
PS C:\> $testVN = New-AzVirtualNetwork -Name testvn -ResourceGroupName databricks-rg-rqb2yo -Location eastus -AddressPrefix "10.0.0.0/16" -Subnet $privSubnet,$pubSubnet
PS C:\> New-AzDatabricksWorkspace -Name workspace3miaeb-with-custom-vn -ResourceGroupName databricks-rg-rqb2yo -Location eastus -VirtualNetworkId $testVN.Id -PrivateSubnetName $privSubnet.Name -PublicSubnetName $privSubnet.Name -Sku standard

Name            ResourceGroupName    Location Managed Resource Group ID
----            -----------------    -------- -------------------------
workspace3miaeb databricks-rg-rqb2yo eastus   /subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/databricks-rg-workspace3miaeb-3c0s2mbgrqv9k
```

Perintah ini membuat ruang kerja Databricks dengan jaringan virtual yang dikustomisasi dalam grup sumber daya.

### Contoh 3: Membuat ruang kerja Databricks dengan mengaktifkan enkripsi
```powershell
PS C:\> New-AzDatabricksWorkspace -Name workspace3miaeb -ResourceGroupName databricks-rg-rqb2yo -PrepareEncryption -Location "East US 2 EUAP" -Sku premium

Name            ResourceGroupName    Location Managed Resource Group ID
----            -----------------    -------- -------------------------
workspace3miaeb databricks-rg-rqb2yo eastus   /subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/databricks-rg-workspace3miaeb-3c0s2mbgrqv9k
```

Perintah ini membuat ruang kerja Databricks dan mengaturnya untuk mempersiapkan enkripsi.
Silakan lihat contoh Update-AzDatabricksWorkspace untuk pengaturan lainnya ke enkripsi.

## PARAMETERS

### -AmlWorkspaceId
Nilai yang harus digunakan untuk bidang ini.

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

### -AsJob
Menjalankan perintah sebagai pekerjaan

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
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases: AzureRMContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnableNoPublicIP
Nilai yang harus digunakan untuk bidang ini.

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

### -EncryptionKeyName
Nama kunci KeyVault.

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

### -EncryptionKeySource
Kunci enkripsiSource (penyedia).
Kemungkinan nilai (tidak peka huruf besar kecil): Default, Microsoft.Keyvault

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Databricks.Support.KeySource
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EncryptionKeyVaultUri
Uri dari KeyVault.

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

### -EncryptionKeyVersion
Versi kunci KeyVault.

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

### -LoadBalancerBackendPoolName
Nilai yang harus digunakan untuk bidang ini.

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

### -LoadBalancerId
Nilai yang harus digunakan untuk bidang ini.

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

### -Lokasi
Lokasi geografis tempat sumber daya berada

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ManagedResourceGroupName
Id grup sumber daya terkelola.

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

### -Nama
Nama ruang kerja.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: WorkspaceName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NatGatewayName
Nilai yang harus digunakan untuk bidang ini.

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

### -NoWait
Jalankan perintah secara asinkron

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

### -PrepareEncryption
Nilai yang harus digunakan untuk bidang ini.

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

### -PrivateSubnetName
Nilai yang harus digunakan untuk bidang ini.

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

### -PublicIPName
Nilai yang harus digunakan untuk bidang ini.

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

### -PublicNetworkAccess
Tipe akses jaringan untuk mengakses ruang kerja.
Atur nilai ke dinonaktifkan untuk mengakses ruang kerja hanya melalui tautan privat.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Databricks.Support.PublicNetworkAccess
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PublicSubnetName
Nilai yang harus digunakan untuk bidang ini.

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

### -RequiredNsgRule
Mendapatkan atau mengatur nilai yang mengindikasikan apakah bidang data (kluster) untuk mengontrol komunikasi pesawat terjadi melalui titik akhir privat.
Nilai yang didukung adalah 'AllRules' dan 'NoAzureDatabricksRules'.
Nilai 'NoAzureServiceRules' hanya untuk penggunaan internal.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Databricks.Support.RequiredNsgRules
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RequireInfrastructureEncryption
Nilai yang harus digunakan untuk bidang ini.

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

### -ResourceGroupName
Nama grup sumber daya.
Nama ini tidak peka huruf besar kecil.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Sku
Nama SKU.

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

### -SkuTier
Tingkat SKU.

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

### -StorageAccountName
Nilai yang harus digunakan untuk bidang ini.

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

### -StorageAccountsku
Nilai yang harus digunakan untuk bidang ini.

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

### -SubscriptionId
ID langganan target.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tag
Tag sumber daya.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualNetworkId
Nilai yang harus digunakan untuk bidang ini.

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

### -VnetAddressPrefix
Nilai yang harus digunakan untuk bidang ini.

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

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Databricks.Models.Api20210401Preview.IWorkspace

## CATATAN

ALIAS

## RELATED LINKS

