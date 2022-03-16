---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Network.dll-Help.xml
Module Name: Az.Network
online version: https://docs.microsoft.com/powershell/module/az.network/new-azfirewallpolicy
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzFirewallPolicy.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Network/Network/help/New-AzFirewallPolicy.md
ms.openlocfilehash: b97d5d3f05148174ae40e03cec90c2ad90dc0a6f
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140197639"
---
# New-AzFirewallPolicy

## SYNOPSIS
Membuat Kebijakan Azure Firewall baru

## SYNTAX

```
New-AzFirewallPolicy -Name <String> -ResourceGroupName <String> -Location <String> [-ThreatIntelMode <String>]
 [-ThreatIntelWhitelist <PSAzureFirewallPolicyThreatIntelWhitelist>] [-BasePolicy <String>]
 [-DnsSetting <PSAzureFirewallPolicyDnsSettings>] [-SqlSetting <PSAzureFirewallPolicySqlSetting>]
 [-Tag <Hashtable>] [-Force] [-AsJob] [-IntrusionDetection <PSAzureFirewallPolicyIntrusionDetection>]
 [-TransportSecurityName <String>] [-TransportSecurityKeyVaultSecretId <String>] [-SkuTier <String>]
 [-UserAssignedIdentityId <String>] [-Identity <PSManagedServiceIdentity>] [-PrivateRange <String[]>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzFirewallPolicy** membuat Kebijakan Azure Firewall.

## EXAMPLES

### Contoh 1: 1. Membuat kebijakan kosong
```powershell
PS C:\> New-AzFirewallPolicy -Name fp1 -ResourceGroupName TestRg
```

Contoh ini membuat kebijakan firewall Azure

### Contoh 2: 2. Membuat kebijakan kosong dengan Mode ThreatIntel
```powershell
PS C:\> New-AzFirewallPolicy -Name fp1 -ResourceGroupName TestRg -ThreatIntelMode "Deny"
```

Contoh ini membuat kebijakan firewall Azure dengan mode threat intel

### Contoh 3: 3. Membuat kebijakan kosong dengan ThreatIntel Whitelist
```powershell
PS C:\> $threatIntelWhitelist = New-AzFirewallPolicyThreatIntelWhitelist -IpAddress 23.46.72.91,192.79.236.79 -FQDN microsoft.com
PS C:\> New-AzFirewallPolicy -Name fp1 -ResourceGroupName TestRg -ThreatIntelWhitelist $threatIntelWhitelist
```

Contoh ini membuat kebijakan firewall Azure dengan daftar putih intel ancaman

### Contoh 4: 4. Membuat kebijakan dengan deteksi penyusup, identitas, dan keamanan transportasi
```powershell
PS C:\> $bypass = New-AzFirewallPolicyIntrusionDetectionBypassTraffic -Name "bypass-setting" -Protocol "TCP" -DestinationPort "80" -SourceAddress "10.0.0.0" -DestinationAddress
PS C:\> $signatureOverride = New-AzFirewallPolicyIntrusionDetectionSignatureOverride -Id "123456798" -Mode "Deny"
PS C:\> $intrusionDetection = New-AzFirewallPolicyIntrusionDetection -Mode "Alert" -SignatureOverride $signatureOverride -BypassTraffic $bypass
PS C:\> $userAssignedIdentity = '/subscriptions/9e223dbe-3399-4e19-88eb-0975f02ac87f/resourcegroups/TestRg/providers/Microsoft.ManagedIdentity/userAssignedIdentities/user-assign-identity'
PS C:\> New-AzFirewallPolicy -Name fp1 -Location "westus2" -ResourceGroup TestRg -SkuTier "Premium" -IntrusionDetection $intrusionDetection -TransportSecurityName tsName -TransportSecurityKeyVaultSecretId "https://<keyvaultname>.vault.azure.net/secrets/cacert"  -UserAssignedIdentityId $userAssignedIdentity
```

Contoh ini membuat kebijakan firewall Azure dengan deteksi penyusup dalam pemberitahuan mode, identitas yang ditetapkan pengguna, dan keamanan transpor

### Contoh 5: 5. Membuat Kebijakan Firewall kosong dengan penyetelan rentang privat yang dikustomisasi
```powershell
PS C:\> New-AzFirewallPolicy -Name fp1 -ResourceGroupName TestRg -PrivateRange @("99.99.99.0/24", "66.66.0.0/16")
```

Contoh ini membuat Firewall yang memperlakukan "99.99.99.0/24" dan "66.66.0.0/16" sebagai rentang ip privat dan tidak akan melakukan lalu lintas ke alamat tersebut

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

### -BasePolicy
Kebijakan dasar yang diwariskan

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

### -DnsSetting
Pengaturan DNS

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSAzureFirewallPolicyDnsSettings
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Force
Jangan minta konfirmasi jika Anda ingin menimpa sumber daya

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

### -Identity
Identitas Kebijakan Firewall akan ditetapkan ke Kebijakan Firewall.

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSManagedServiceIdentity
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IntrusionDetection
Pengaturan deteksi penyusup

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSAzureFirewallPolicyIntrusionDetection
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lokasi
lokasi.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nama
Nama sumber daya.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ResourceName

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -PrivateRange
Rentang IP privat yang lalu lintasnya tidak akan menjadi SNAT

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

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -SkuTier
Kebijakan firewall sku tier

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Standard, Premium

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SqlSetting
Pengaturan SQL terkait

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSAzureFirewallPolicySqlSetting
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tag
Hashtable yang mewakili tag sumber daya.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ThreatIntelMode
Mode operasi untuk Threat Intelligence.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Alert, Deny, Off

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ThreatIntelGoldlist
Daftar putih untuk Threat Intelligence

```yaml
Type: Microsoft.Azure.Commands.Network.Models.PSAzureFirewallPolicyThreatIntelWhitelist
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TransportSecurityKeyVaultSecretId
Id Rahasia dari (base-64 encoded unencrypted pfx) 'Secret' atau 'Certificate' object stored in KeyVault

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

### -TransportSecurityName
Nama keamanan transpor

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

### -UserAssignedIdentityId
ResourceId identitas yang ditetapkan pengguna untuk ditetapkan ke Kebijakan Firewall.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: UserAssignedIdentity

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

### System.Collections.Hashtable

## OUTPUTS

### Microsoft.Azure.Commands.Network.Models.PSAzureFirewall

## CATATAN

## RELATED LINKS
