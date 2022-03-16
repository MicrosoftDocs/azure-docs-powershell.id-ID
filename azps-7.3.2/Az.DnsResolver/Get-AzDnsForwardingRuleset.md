---
external help file: ''
Module Name: Az.DnsResolver
online version: https://docs.microsoft.com/powershell/module/az.dnsresolver/get-azdnsforwardingruleset
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DnsResolver/help/Get-AzDnsForwardingRuleset.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DnsResolver/help/Get-AzDnsForwardingRuleset.md
ms.openlocfilehash: ce51ed8d5170d27831f0dbd4561e78183dade8b3
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140000941"
---
# Get-AzDnsForwardingRuleset

## SYNOPSIS
Mendapatkan properti aturan penerusan DNS.

## SYNTAX

### Daftar1 (Default)
```
Get-AzDnsForwardingRuleset [-SubscriptionId <String[]>] [-Top <Int32>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### Dapatkan
```
Get-AzDnsForwardingRuleset -Name <String> -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzDnsForwardingRuleset -InputObject <IDnsResolverIdentity> [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### Daftar
```
Get-AzDnsForwardingRuleset -ResourceGroupName <String> [-SubscriptionId <String[]>] [-Top <Int32>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Daftar2
```
Get-AzDnsForwardingRuleset -ResourceGroupName <String> -VirtualNetworkName <String>
 [-SubscriptionId <String[]>] [-Top <Int32>] [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan properti aturan penerusan DNS.

## EXAMPLES

### Contoh 1:  List all DNS forwarding rulesets in a subscription
```powershell
Get-AzDnsForwardingRuleset -SubscriptionId 0e5a46b1-de0b-4ec3-a5d7-dda908b4e076
```

```output
Location Name                                                            Type                                    Etag
-------- ----                                                            ----                                    ----
westus2  dnsForwardingRuleset                                            Microsoft.Network/dnsForwardingRulesets "04005592-0000-0800-0000-60e7ec170000"
westus2  pw-dnsForwardingRuleset                                         Microsoft.Network/dnsForwardingRulesets "08009ec9-0000-0800-0000-60e383b70000"
westus2  pw-dnsForwardingRuleset1                                        Microsoft.Network/dnsForwardingRulesets "08007ccc-0000-0800-0000-60e3846a0000"
eastus2  dnsforwardingruleset-test-eastus2-main-syn-outbound-primary-0   Microsoft.Network/dnsForwardingRulesets "4f006bb2-0000-0200-0000-60e7ef240000"
eastus2  dnsforwardingruleset-test-eastus2-main-syn-outbound-secondary-0 Microsoft.Network/dnsForwardingRulesets "4f006db2-0000-0200-0000-60e7ef240000"
```

Perintah ini mendapatkan semua aturan penerusan DNS di bawah langganan.

### Contoh 2: Dapatkan satu aturan penerusan DNS berdasarkan nama
```powershell
Get-AzDnsForwardingRuleset -Name dnsForwardingRuleset -ResourceGroupName sampleRG
```

```output
Location Name                 Type                                    Etag
-------- ----                 ----                                    ----
westus2  dnsForwardingRuleset Microsoft.Network/dnsForwardingRulesets "04005592-0000-0800-0000-60e7ec170000"
```

Perintah ini mendapatkan satu aturan penerusan DNS menurut nama.

### Contoh 3: Daftar semua aturan penerusan DNS di bawah grup sumber daya
```powershell
Get-AzDnsForwardingRuleset -ResourceGroupName sampleRG
```

```output
Location Name                     Type                                    Etag
-------- ----                     ----                                    ----
westus2  dnsForwardingRuleset     Microsoft.Network/dnsForwardingRulesets "04005592-0000-0800-0000-60e7ec170000"
westus2  pw-dnsForwardingRuleset  Microsoft.Network/dnsForwardingRulesets "08009ec9-0000-0800-0000-60e383b70000"
westus2  pw-dnsForwardingRuleset1 Microsoft.Network/dnsForwardingRulesets "08007ccc-0000-0800-0000-60e3846a0000"
```

Perintah ini mendapatkan semua kumpulan aturan penerusan DNS di bawah grup sumber daya.

### Contoh 4:  List all DNS forwarding ruleset under the virtual network
```powershell
Get-AzDnsForwardingRuleset -ResourceGroupName sampleRG -VirtualNetworkName virtualnetwork-test
```

```output
Location Name                     Type                                    Etag
-------- ----                     ----                                    ----
westus2  dnsForwardingRuleset     Microsoft.Network/dnsForwardingRulesets "04005592-0000-0800-0000-60e7ec170000"
```

Perintah ini mendapatkan semua aturan penerusan DNS di bawah jaringan virtual.

### Contoh 5: Membuat daftar semua aturan penerusan DNS di bawah Titik Akhir Keluar
```powershell
Get-AzDnsForwardingRuleset -ResourceGroupName sampleRG -DnsResolverName sampleDnsResolver -OutboundEndpointName sampleOutboundEndpoint
```

```output
Location Name                     Type                                    Etag
-------- ----                     ----                                    ----
westus2  dnsForwardingRuleset     Microsoft.Network/dnsForwardingRulesets "04005592-0000-0800-0000-60e7ec170000"
```

Perintah ini mendapatkan semua aturan penerusan DNS di bawah titik akhir keluar.

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

### -InputObject
Parameter Identitas Untuk membuat, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DnsResolver.Models.IDnsResolverIdentity
Parameter Sets: GetViaIdentity
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nama
Nama aturan penerusan DNS.

```yaml
Type: System.String
Parameter Sets: Get
Aliases: DnsForwardingRulesetName

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
Parameter Sets: Get, List, List2
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
Type: System.String[]
Parameter Sets: Get, List, List1, List2
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -Top
Jumlah maksimum hasil yang dikembalikan.
Jika tidak ditentukan, mengembalikan hingga 100 hasil.

```yaml
Type: System.Int32
Parameter Sets: List, List1, List2
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualNetworkName
Nama jaringan virtual.

```yaml
Type: System.String
Parameter Sets: List2
Aliases:

Required: True
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

### Microsoft.Azure.PowerShell.Cmdlets.DnsResolver.Models.IDnsResolverIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DnsResolver.Models.Api20200401Preview.IDnsForwardingRuleset

### Microsoft.Azure.PowerShell.Cmdlets.DnsResolver.Models.Api20200401Preview.IVirtualNetworkDnsForwardingRuleset

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IDnsResolverIdentity>: Parameter Identitas
  - `[DnsForwardingRulesetName <String>]`: Nama daftar aturan penerusan DNS.
  - `[DnsResolverName <String>]`: Nama resolver DNS.
  - `[ForwardingRuleName <String>]`: Nama aturan penerusan.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[InboundEndpointName <String>]`: Nama titik akhir masuk untuk resolver DNS.
  - `[OutboundEndpointName <String>]`: Nama titik akhir keluar untuk resolver DNS.
  - `[ResourceGroupName <String>]`: Nama grup sumber daya. Namanya peka huruf besar/huruf.
  - `[SubscriptionId <String>]`: ID langganan target.
  - `[VirtualNetworkLinkName <String>]`: Nama link jaringan virtual.
  - `[VirtualNetworkName <String>]`: Nama jaringan virtual.

## RELATED LINKS

