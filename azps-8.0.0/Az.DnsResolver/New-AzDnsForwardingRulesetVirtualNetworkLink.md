---
external help file: ''
Module Name: Az.DnsResolver
online version: https://docs.microsoft.com/powershell/module/az.dnsresolver/new-azdnsforwardingrulesetvirtualnetworklink
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DnsResolver/help/New-AzDnsForwardingRulesetVirtualNetworkLink.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DnsResolver/help/New-AzDnsForwardingRulesetVirtualNetworkLink.md
ms.openlocfilehash: fb5d82c9befb0f3a2616ad88165b574a3a406e7d
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145538085"
---
# New-AzDnsForwardingRulesetVirtualNetworkLink

## SYNOPSIS
Membuat atau memperbarui tautan jaringan virtual ke set aturan penerusan DNS.

## SYNTAX

```
New-AzDnsForwardingRulesetVirtualNetworkLink -DnsForwardingRulesetName <String> -Name <String>
 -ResourceGroupName <String> [-SubscriptionId <String>] [-IfMatch <String>] [-IfNoneMatch <String>]
 [-Metadata <Hashtable>] [-VirtualNetworkId <String>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait]
 [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Membuat atau memperbarui tautan jaringan virtual ke set aturan penerusan DNS.

## EXAMPLES

### Contoh 1: Membuat tautan jaringan virtual
```powershell
New-AzDnsForwardingRulesetVirtualNetworkLink -DnsForwardingRulesetName dnsForwardingRuleset -Name sampleVnetLink -ResourceGroupName sampleRG -VirtualNetworkId "/subscriptions/ea40042d-63d8-4d02-9261-fb31450e6c64/resourceGroups/sampleRG/providers/Microsoft.Network/virtualNetworks/vnet-hub"
```

```output
Location Name                   Type                                             Etag
-------- ----                   ----                                             ----
westus2  sampleVnetLink Microsoft.Network/dnsForwardingRulesets/virtualNetworkLinks "0a009902-0000-0800-0000-60e378030000"
```

Cmdlet ini membuat tautan jaringan virtual.

### Contoh 2: Membuat tautan jaringan virtual dengan metadata
```powershell
New-AzDnsForwardingRulesetVirtualNetworkLink -DnsForwardingRulesetName dnsForwardingRuleset -Name sampleVnetLink -ResourceGroupName sampleRG -VirtualNetworkId "/subscriptions/ea40042d-63d8-4d02-9261-fb31450e6c64/resourceGroups/sampleRG/providers/Microsoft.Network/virtualNetworks/vnet-hub" -Metadata @{"key0" = "value0"}
```

```output
Location Name                   Type                                             Etag
-------- ----                   ----                                             ----
westus2  sampleVnetLink Microsoft.Network/dnsForwardingRulesets/virtualNetworkLinks "0a009902-0000-0800-0000-60e378030000"
```

Cmdlet ini membuat tautan jaringan virtual dengan metadata.

## PARAMETERS

### -AsJob
Jalankan perintah sebagai pekerjaan

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

### -DnsForwardingRulesetName
Nama set aturan penerusan DNS.

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

### -IfMatch
ETag sumber daya.
Hilangkan nilai ini untuk selalu menimpa sumber daya saat ini.
Tentukan nilai ETag yang terakhir dilihat untuk mencegah penimpaan perubahan bersamaan secara tidak sengaja.

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
Atur ke '*' untuk mengizinkan sumber daya baru dibuat, tetapi untuk mencegah pembaruan sumber daya yang ada.
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
Metadata yang dilampirkan ke tautan jaringan virtual.

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

### -Name
Nama tautan jaringan virtual.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: VirtualNetworkLinkName

Required: True
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

### -ResourceGroupName
Nama grup sumber daya.
Nama ini tidak peka huruf besar/kecil.

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

### -VirtualNetworkId
ID Sumber Daya.

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

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DnsResolver.Models.Api20200401Preview.IVirtualNetworkLink

## NOTES

ALIAS

## RELATED LINKS

