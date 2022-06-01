---
external help file: Microsoft.Azure.PowerShell.Cmdlets.KeyVault.dll-Help.xml
Module Name: Az.KeyVault
online version: https://docs.microsoft.com/powershell/module/az.keyvault/update-azkeyvaultnetworkruleset
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KeyVault/KeyVault/help/Update-AzKeyVaultNetworkRuleSet.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/KeyVault/KeyVault/help/Update-AzKeyVaultNetworkRuleSet.md
ms.openlocfilehash: 64772b99a5fcf720db91220df64070606a1b7c4f
ms.sourcegitcommit: 22f85a560177b7234f114dd21a108e3bc8b1608b
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/01/2022
ms.locfileid: "145972543"
---
# Update-AzKeyVaultNetworkRuleSet

## SYNOPSIS
Memperbarui seperangkat aturan jaringan pada brankas kunci.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.keyvault/update-azkeyvaultnetworkruleset) untuk informasi terbaru.

## SYNTAX

### ByVaultName (Default)
```
Update-AzKeyVaultNetworkRuleSet [-VaultName] <String> [[-ResourceGroupName] <String>]
 [-DefaultAction <PSKeyVaultNetworkRuleDefaultActionEnum>] [-Bypass <PSKeyVaultNetworkRuleBypassEnum>]
 [-IpAddressRange <String[]>] [-VirtualNetworkResourceId <String[]>] [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [-SubscriptionId <String>]
 [<CommonParameters>]
```

### ByInputObject
```
Update-AzKeyVaultNetworkRuleSet [-InputObject] <PSKeyVault>
 [-DefaultAction <PSKeyVaultNetworkRuleDefaultActionEnum>] [-Bypass <PSKeyVaultNetworkRuleBypassEnum>]
 [-IpAddressRange <String[]>] [-VirtualNetworkResourceId <String[]>] [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [-SubscriptionId <String>]
 [<CommonParameters>]
```

### ByResourceId
```
Update-AzKeyVaultNetworkRuleSet [-ResourceId] <String>
 [-DefaultAction <PSKeyVaultNetworkRuleDefaultActionEnum>] [-Bypass <PSKeyVaultNetworkRuleBypassEnum>]
 [-IpAddressRange <String[]>] [-VirtualNetworkResourceId <String[]>] [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [-SubscriptionId <String>]
 [<CommonParameters>]
```

## DESCRIPTION
Perintah **Update-AzKeyVaultNetworkRuleSet** memperbarui aturan jaringan yang berlaku pada brankas kunci yang ditentukan.

## EXAMPLES

### Contoh 1
```powershell
$frontendSubnet = New-AzVirtualNetworkSubnetConfig -Name frontendSubnet -AddressPrefix "10.0.1.0/24" -ServiceEndpoint Microsoft.KeyVault
$virtualNetwork = New-AzVirtualNetwork -Name myVNet -ResourceGroupName myRG -Location westus -AddressPrefix "10.0.0.0/16" -Subnet $frontendSubnet
$myNetworkResId = (Get-AzVirtualNetwork -Name myVNet -ResourceGroupName myRG).Subnets[0].Id
Update-AzKeyVaultNetworkRuleSet -VaultName 'myVault' -ResourceGroupName myRG -Bypass AzureServices -IpAddressRange "10.0.1.0/24" -VirtualNetworkResourceId $myNetworkResId -PassThru
```

```output
Vault Name                       : myVault
Resource Group Name              : myRG
Location                         : West US
Resource ID                      : /subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxxx/resourceGroups/myrg/providers
                                   /Microsoft.KeyVault/vaults/myvault
Vault URI                        : https://myvault.vault.azure.net/
Tenant ID                        : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxxx
SKU                              : Standard
Enabled For Deployment?          : False
Enabled For Template Deployment? : False
Enabled For Disk Encryption?     : False
Soft Delete Enabled?             :
Access Policies                  :
                                   Tenant ID                                  : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxxx
                                   Object ID                                  : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxxx
                                   Application ID                             :
                                   Display Name                               : User Name (username@microsoft.com)
                                   Permissions to Keys                        : get, create, delete, list, update,
                                   import, backup, restore, recover
                                   Permissions to Secrets                     : get, list, set, delete, backup,
                                   restore, recover
                                   Permissions to Certificates                : get, delete, list, create, import,
                                   update, deleteissuers, getissuers, listissuers, managecontacts, manageissuers,
                                   setissuers, recover, backup, restore
                                   Permissions to (Key Vault Managed) Storage : delete, deletesas, get, getsas, list,
                                   listsas, regeneratekey, set, setsas, update, recover, backup, restore


Network Rule Set                 :
                                   Default Action                             : Allow
                                   Bypass                                     : AzureServices
                                   IP Rules                                   : 10.0.1.0/24
                                   Virtual Network Rules                      : /subscriptions/xxxxxxxx-xxxx-xxxx-xxxx-
                                   xxxxxxxxxxxxx/resourcegroups/myrg/providers/microsoft.network/virtualnetworks/myvn
                                   et/subnets/frontendsubnet

Tags                             :
```

Perintah ini memperbarui set aturan jaringan pada vault bernama 'myVault' untuk rentang IP dan jaringan virtual yang ditentukan, memungkinkan melewati aturan jaringan untuk layanan Azure.

### Contoh 2

Memperbarui seperangkat aturan jaringan pada brankas kunci. (dibuat otomatis)

<!-- Aladdin Generated Example -->
```powershell
Update-AzKeyVaultNetworkRuleSet -DefaultAction Allow -VaultName 'myVault'
```

## PARAMETERS

### -Bypass
Menentukan bypass aturan jaringan.

```yaml
Type: System.Nullable`1[Microsoft.Azure.Commands.KeyVault.Models.PSKeyVaultNetworkRuleBypassEnum]
Parameter Sets: (All)
Aliases:
Accepted values: None, AzureServices

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DefaultAction
Menentukan tindakan default aturan jaringan.

```yaml
Type: System.Nullable`1[Microsoft.Azure.Commands.KeyVault.Models.PSKeyVaultNetworkRuleDefaultActionEnum]
Parameter Sets: (All)
Aliases:
Accepted values: Allow, Deny

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -InputObject
Objek KeyVault

```yaml
Type: Microsoft.Azure.Commands.KeyVault.Models.PSKeyVault
Parameter Sets: ByInputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -IpAddressRange
Menentukan rentang alamat IP jaringan yang diizinkan dari aturan jaringan.

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

### -PassThru
Cmdlet ini tidak mengembalikan objek secara default.
Jika sakelar ini ditentukan, maka akan mengembalikan objek brankas kunci yang diperbarui.

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
Menentukan nama grup sumber daya yang terkait dengan brankas kunci yang aturan jaringannya sedang dimodifikasi.

```yaml
Type: System.String
Parameter Sets: ByVaultName
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
Id Sumber Daya KeyVault

```yaml
Type: System.String
Parameter Sets: ByResourceId
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SubscriptionId
ID langganan.
Secara default, cmdlet dijalankan dalam langganan yang diatur dalam konteks saat ini. Jika pengguna menentukan langganan lain, cmdlet saat ini dijalankan dalam langganan yang ditentukan oleh pengguna.
Mengambil alih langganan hanya berlaku selama siklus hidup cmdlet saat ini. Ini tidak mengubah langganan dalam konteks, dan tidak memengaruhi cmdlet berikutnya.

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

### -VaultName
Menentukan nama brankas kunci yang aturan jaringannya sedang dimodifikasi.

```yaml
Type: System.String
Parameter Sets: ByVaultName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualNetworkResourceId
Menentukan pengidentifikasi sumber daya jaringan virtual yang diizinkan dari aturan jaringan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.Commands.KeyVault.Models.PSKeyVault

### System.String

### System.Nullable'1[[Microsoft.Azure.Commands.KeyVault.Models.PSKeyVaultNetworkRuleDefaultActionEnum, Microsoft.Azure.PowerShell.Cmdlets.KeyVault, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null]]

### System.Nullable'1[[Microsoft.Azure.Commands.KeyVault.Models.PSKeyVaultNetworkRuleBypassEnum, Microsoft.Azure.PowerShell.Cmdlets.KeyVault, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null]]

## OUTPUTS

### Microsoft.Azure.Commands.KeyVault.Models.PSKeyVault

## NOTES

## RELATED LINKS
