---
external help file: ''
Module Name: Az.DnsResolver
online version: https://docs.microsoft.com/powershell/module/az.dnsresolver/new-azdnsforwardingruleset
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DnsResolver/help/New-AzDnsForwardingRuleset.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DnsResolver/help/New-AzDnsForwardingRuleset.md
ms.openlocfilehash: 37f13caff2320f0be340ecebf113e002019a8be8
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140394335"
---
# New-AzDnsForwardingRuleset

## SYNOPSIS
Membuat atau memperbarui perangkat aturan penerusan DNS.

## SYNTAX

```
New-AzDnsForwardingRuleset -Name <String> -ResourceGroupName <String> -Location <String>
 [-SubscriptionId <String>] [-IfMatch <String>] [-IfNoneMatch <String>]
 [-DnsResolverOutboundEndpoint <ISubResource[]>] [-Tag <Hashtable>] [-DefaultProfile <PSObject>] [-AsJob]
 [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Membuat atau memperbarui perangkat aturan penerusan DNS.

## EXAMPLES

### Contoh 1: Membuat perangkat aturan penerusan DNS
```powershell
New-AzDnsResolverOutboundEndpoint -DnsResolverName sampleResolver -Name sampleOutboundEndpoint -ResourceGroupName sampleRG -SubscriptionId ea40042d-63d8-4d02-9261-fb31450e6c67 -SubnetId "/subscriptions/0e5a46b1-de0b-4ec3-a5d7-dda908b4e076/resourceGroups/powershell-test-08b4e076/resourceGroups/sampleRG/providers/Microsoft.Network/virtualNetworks/psvirtualnetworkname16y71mjc/subnets/test-subnet" -Location westus2
New-AzDnsForwardingRuleset -Name dnsForwardingRuleset -ResourceGroupName sampleRG -Location westus2 -DnsResolverOutboundEndpoint  @{id = "/subscriptions/ea40042d-63d8-4d02-9261-fb31450e6c64/resourceGroups/sampleRG/providers/Microsoft.Network/dnsResolvers/sampleResolver/outboundEndpoints/sampleOutboundEndpoint";}
```

```output
Location Name                 Type                                    Etag
-------- ----                 ----                                    ----
westus2  dnsForwardingRuleset Microsoft.Network/dnsForwardingRulesets "04005592-0000-0800-0000-60e7ec170000"
```

Cmdlet ini membuatet aturan penerusan DNS.

### Contoh 2: Membuat aturan penerusan DNS dengan tag
```powershell
New-AzDnsResolverOutboundEndpoint -DnsResolverName sampleResolver -Name sampleOutboundEndpoint -ResourceGroupName sampleRG -SubscriptionId ea40042d-63d8-4d02-9261-fb31450e6c67 -SubnetId "/subscriptions/0e5a46b1-de0b-4ec3-a5d7-dda908b4e076/resourceGroups/powershell-test-08b4e076/resourceGroups/sampleRG/providers/Microsoft.Network/virtualNetworks/psvirtualnetworkname16y71mjc/subnets/test-subnet" -Location westus2
New-AzDnsForwardingRuleset -Name dnsForwardingRuleset -ResourceGroupName sampleRG -Location westus2 -DnsResolverOutboundEndpoint  @{id = "/subscriptions/ea40042d-63d8-4d02-9261-fb31450e6c64/resourceGroups/sampleRG/providers/Microsoft.Network/dnsResolvers/sampleResolver/outboundEndpoints/sampleOutboundEndpoint";} -Tag @{"key0" = "value0"}
```

```output
Location Name                 Type                                    Etag
-------- ----                 ----                                    ----
westus2  dnsForwardingRuleset Microsoft.Network/dnsForwardingRulesets "04005592-0000-0800-0000-60e7ec170000"
```

Cmdlet ini membuat aturan penerusan DNS.}

## PARAMETERS

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

### -DnsResolverOutboundEndpoint
Referensi ke titik akhir keluar resolver DNS yang digunakan untuk merutekan kueri DNS yang cocok dengan aturan penerusan dalam ruleset ke server DNS target.
Untuk membuat, lihat bagian CATATAN untuk properti DNSRESOLVEROUTBOUNDENDPOINT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DnsResolver.Models.Api20200401Preview.ISubResource[]
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

### -Lokasi
Lokasi geo-location di mana sumber daya berada

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

### -Nama
Nama aturan penerusan DNS.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: DnsForwardingRulesetName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoWait
Menjalankan perintah secara asinkron

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

### Microsoft.Azure.PowerShell.Cmdlets.DnsResolver.Models.Api20200401Preview.IDnsForwardingRuleset

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


DNSRESOLVEROUTBOUNDENDPOINT <ISubResource[]>: Referensi ke titik akhir keluar resolver DNS yang digunakan untuk merutekan kueri DNS yang cocok dengan aturan penerusan diet aturan ke server DNS target.
  - `[Id <String>]`: ID Sumber Daya.

## RELATED LINKS

