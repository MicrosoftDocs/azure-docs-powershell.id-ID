---
external help file: ''
Module Name: Az.DnsResolver
online version: https://docs.microsoft.com/powershell/module/az.dnsresolver/get-azdnsforwardingrulesetforwardingrule
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DnsResolver/help/Get-AzDnsForwardingRulesetForwardingRule.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DnsResolver/help/Get-AzDnsForwardingRulesetForwardingRule.md
ms.openlocfilehash: 93d61cbf420be846cbb2a4e9f8c78f11c4605760
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140187021"
---
# Get-AzDnsForwardingRulesetForwardingRule

## SYNOPSIS
Mendapatkan properti aturan penerusan dalamet aturan penerusan DNS.

## SYNTAX

### Daftar (Default)
```
Get-AzDnsForwardingRulesetForwardingRule -DnsForwardingRulesetName <String> -ResourceGroupName <String>
 [-SubscriptionId <String[]>] [-Top <Int32>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Dapatkan
```
Get-AzDnsForwardingRulesetForwardingRule -DnsForwardingRulesetName <String> -Name <String>
 -ResourceGroupName <String> [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzDnsForwardingRulesetForwardingRule -InputObject <IDnsResolverIdentity> [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan properti aturan penerusan dalamet aturan penerusan DNS.

## EXAMPLES

### Contoh 1: Mencantumkan semua aturan penerusan di bawah sumber daya
```powershell
Get-AzDnsForwardingRulesetForwardingRule -DnsForwardingRulesetName DnsResolverName -ResourceGroupName sampleRG
```

```output
Location Name                                                            Type                                                Etag
-------- ----                                                            ----                                                ----
westus2  dnsForwardingRule                                            Microsoft.Network/dnsForwardingRulesets/forwardingRule "04005592-0000-0800-0000-60e7ec170000"
westus2  pw-dnsForwardingRule                                         Microsoft.Network/dnsForwardingRulesets/forwardingRule "08009ec9-0000-0800-0000-60e383b70000"
```

Perintah ini mendapatkan semua aturan penerusan di bawah sumber daya.

### Contoh 1: Mendapatkan penerusan aturan menurut nama
```powershell
Get-AzDnsForwardingRulesetForwardingRule -DnsForwardingRulesetName DnsResolverName -ResourceGroupName sampleRG -Name forwardingRule
```

```output
Location Name                                                            Type                                                Etag
-------- ----                                                            ----                                                ----
westus2  dnsForwardingRule                                            Microsoft.Network/dnsForwardingRulesets/forwardingRule "04005592-0000-0800-0000-60e7ec170000"
```

Perintah ini mendapatkan aturan penerusan menurut nama.

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
Parameter Sets: Get, List
Aliases:

Required: True
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
Nama aturan penerusan.

```yaml
Type: System.String
Parameter Sets: Get
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
Parameter Sets: Get, List
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
Parameter Sets: Get, List
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
Parameter Sets: List
Aliases:

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

### Microsoft.Azure.PowerShell.Cmdlets.DnsResolver.Models.Api20200401Preview.IForwardingRule

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

