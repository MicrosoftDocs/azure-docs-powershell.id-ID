---
external help file: ''
Module Name: Az.DnsResolver
online version: https://docs.microsoft.com/powershell/module/az.dnsresolver/new-azdnsforwardingrulesetforwardingrule
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DnsResolver/help/New-AzDnsForwardingRulesetForwardingRule.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DnsResolver/help/New-AzDnsForwardingRulesetForwardingRule.md
ms.openlocfilehash: 9d09e7177b9eacc64c6cf6749f13d6799949858b
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140000926"
---
# New-AzDnsForwardingRulesetForwardingRule

## SYNOPSIS
Membuat atau memperbarui aturan penerusan dalam perangkat aturan penerusan DNS.

## SYNTAX

```
New-AzDnsForwardingRulesetForwardingRule -DnsForwardingRulesetName <String> -Name <String>
 -ResourceGroupName <String> [-SubscriptionId <String>] [-IfMatch <String>] [-IfNoneMatch <String>]
 [-DomainName <String>] [-ForwardingRuleState <ForwardingRuleState>] [-Metadata <Hashtable>]
 [-TargetDnsServer <ITargetDnsServer[]>] [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
Membuat atau memperbarui aturan penerusan dalam perangkat aturan penerusan DNS.

## EXAMPLES

### Contoh 1: Membuat aturan penerusan.
```powershell
$targetIPConfig = New-AzDnsResolverIPConfigurationObject -PrivateIPAddress 10.0.0.3 -PrivateIPAllocationMethod Dynamic -SubnetId /subscriptions/ea40042d-63d8-4d02-9261-fb31450e6c67/resourceGroups/sampleRG/providers/Microsoft.Network/virtualNetworks/vnet-hub/subnets/test-subnet
New-AzDnsForwardingRulesetForwardingRule -DnsForwardingRulesetName dnsForwardingRuleset -Name sampleForwardingRule -ResourceGroupName sampleRG -TargetDnsServer $targetIPConfig
```

```output
Name                  Type                                            Etag
----                  ----                                            ----
sampleForwardingRule Microsoft.Network/dnsForwardingRuleset/forwardingRule "0b008451-0000-0800-0000-60402b960000"
```

Cmdlet ini membuat aturan penerusan.

### Contoh 2: Membuat aturan penerusan dengan tag
```powershell
$targetIPConfig = New-AzDnsResolverIPConfigurationObject -PrivateIPAddress 10.0.0.3 -PrivateIPAllocationMethod Dynamic -SubnetId /subscriptions/ea40042d-63d8-4d02-9261-fb31450e6c67/resourceGroups/sampleRG/providers/Microsoft.Network/virtualNetworks/vnet-hub/subnets/test-subnet
New-AzDnsForwardingRulesetForwardingRule -DnsForwardingRulesetName dnsForwardingRuleset -Name sampleForwardingRule -ResourceGroupName sampleRG -TargetDnsServer $targetIPConfig -Metadata @{"key0" = "value0"}
```

```output
Name                  Type                                            Etag
----                  ----                                            ----
sampleForwardingRule Microsoft.Network/dnsForwardingRuleset/forwardingRule "0b008451-0000-0800-0000-60402b960000"
```

Cmdlet ini membuat aturan penerusan dengan tag.

## PARAMETERS

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

### -DnsForwardingRulesetName
Nama aturan penerusan DNS.

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

### -DomainName
Nama domain untuk aturan penerusan.

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

### -ForwardingRuleState
Status aturan penerusan.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DnsResolver.Support.ForwardingRuleState
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IfMatch
ETag sumber daya.
Menghilangkan nilai ini agar selalu menimpa sumber daya saat ini.
Tentukan nilai ETag yang terakhir dilihat untuk mencegah secara tidak sengaja menimpa perubahan konklar apa pun.

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

### -IfNoneMatch
Atur ke '*' untuk memungkinkan sumber daya baru dibuat, tetapi untuk mencegah pembaruan sumber daya yang sudah ada.
Nilai lain akan diabaikan.

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

### -Metadata
Metadata yang dilampirkan ke aturan penerusan.

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

### -Nama
Nama aturan penerusan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ForwardingRuleName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.
Namanya peka huruf besar/huruf.

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

### -TargetDnsServer
Server DNS untuk meneruskan kueri DNS.
Untuk membuat, lihat bagian CATATAN untuk properti TARGETDNSSERVER dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DnsResolver.Models.Api20200401Preview.ITargetDnsServer[]
Parameter Sets: (All)
Aliases:

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

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DnsResolver.Models.Api20200401Preview.IForwardingRule

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


TARGETDNSSERVER <ITargetDnsServer[]>: Server DNS untuk meneruskan kueri DNS.
  - `[IPAddress <String>]`: Alamat IP server DNS.
  - `[Port <Int32?>]`: Port server DNS.

## RELATED LINKS

