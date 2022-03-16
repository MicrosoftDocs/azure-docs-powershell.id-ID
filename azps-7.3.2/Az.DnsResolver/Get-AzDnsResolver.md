---
external help file: ''
Module Name: Az.DnsResolver
online version: https://docs.microsoft.com/powershell/module/az.dnsresolver/get-azdnsresolver
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DnsResolver/help/Get-AzDnsResolver.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DnsResolver/help/Get-AzDnsResolver.md
ms.openlocfilehash: d51b1556c26d8b3f7dc771e6ee6ca66e7f53fbc1
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140179629"
---
# Get-AzDnsResolver

## SYNOPSIS
Mendapatkan properti untuk resolver DNS.

## SYNTAX

### Daftar1 (Default)
```
Get-AzDnsResolver [-SubscriptionId <String[]>] [-Top <Int32>] [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

### Dapatkan
```
Get-AzDnsResolver -Name <String> -ResourceGroupName <String> [-SubscriptionId <String[]>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzDnsResolver -InputObject <IDnsResolverIdentity> [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Daftar
```
Get-AzDnsResolver -ResourceGroupName <String> [-SubscriptionId <String[]>] [-Top <Int32>]
 [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Daftar2
```
Get-AzDnsResolver -ResourceGroupName <String> -VirtualNetworkName <String> [-SubscriptionId <String[]>]
 [-Top <Int32>] [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan properti untuk resolver DNS.

## EXAMPLES

### Contoh 1:  List all DNS Resolvers under the subscription 
```powershell
Get-AzDnsResolver -SubscriptionId 0e5a46b1-de0b-4ec3-a5d7-dda908b4e076
```

```output
Location Name                        Type                           Etag
-------- ----                        ----                           ----
westus2  dnsresolvertestresolver2422 Microsoft.Network/dnsResolvers "8b002671-0000-0800-0000-60386dc10000"
westus2  dnsresolvertestresolver2654 Microsoft.Network/dnsResolvers "8b000f71-0000-0800-0000-60386cc40000"
westus2  dnsresolvertestresolver8416 Microsoft.Network/dnsResolvers "94008a5e-0000-0800-0000-603972f20000"
westus2  dnsresolvertestresolver5036 Microsoft.Network/dnsResolvers "8b002f71-0000-0800-0000-60386df80000"
westus2  dnsresolvertestresolver3718 Microsoft.Network/dnsResolvers "00009b95-0000-0800-0000-603e8b210000"
westus2  dnsresolvertestresolver2758 Microsoft.Network/dnsResolvers "8b00da70-0000-0800-0000-60386b4f0000"
westus2  dnsresolvertestresolver7108 Microsoft.Network/dnsResolvers "00008e95-0000-0800-0000-603e8aee0000"
westus2  dnsresolvertestresolver7639 Microsoft.Network/dnsResolvers "8b00b670-0000-0800-0000-60386b010000"
westus2  dnsresolvertestresolver5912 Microsoft.Network/dnsResolvers "8a00557f-0000-0800-0000-603853bc0000"
westus2  dnsresolvertestguli01       Microsoft.Network/dnsResolvers "48009f1b-0000-0800-0000-60302ec40000"
westus2  dnsresolvertestresolver9892 Microsoft.Network/dnsResolvers "47008640-0000-0800-0000-60300f220000"
```

Perintah ini akan mendapatkan semua Dns Resolvers di bawah langganan.

### Contoh 2:  List all DNS Resolvers under the resource group 
```powershell
Get-AzDnsResolver -ResourceGroupName powershell-test-rg
```

```output
Location Name                      Type                           Etag
-------- ----                      ----                           ----
westus2  psdnsresolvername33nmy1fz Microsoft.Network/dnsResolvers "0000c2d4-0000-0800-0000-604013880000"
westus2  psdnsresolvername34dp19g6 Microsoft.Network/dnsResolvers "0000c9d4-0000-0800-0000-604013990000"
westus2  psdnsresolvername35m3jf0n Microsoft.Network/dnsResolvers "0000d0d4-0000-0800-0000-604013a80000"
```

Perintah ini mendapatkan semua Resolver DNS di bawah grup sumber daya.

### Contoh 3: Dapatkan satu Resolver DNS berdasarkan nama 
```powershell
Get-AzDnsResolver -ResourceGroupName powershell-test-rg -Name  psdnsresolvername33nmy1fz
```

```output
Location Name                      Type                           Etag
-------- ----                      ----                           ----
westus2  psdnsresolvername33nmy1fz Microsoft.Network/dnsResolvers "0000c2d4-0000-0800-0000-604013880000"
```

Perintah ini mendapatkan satu Dns Resolver berdasarkan nama.

### Contoh 4:  List all DNS Resolvers under the virtual network 
```powershell
Get-AzDnsResolver -ResourceGroupName powershell-test-rg -VirtualNetworkName virtualnetwork-test
```

```output
Location Name                      Type                           Etag
-------- ----                      ----                           ----
westus2  psdnsresolvername33nmy1fz Microsoft.Network/dnsResolvers "0000c2d4-0000-0800-0000-604013880000"
```

Perintah ini mendapatkan satu Dns Resolver dari jaringan virtual.

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
Nama resolver DNS.

```yaml
Type: System.String
Parameter Sets: Get
Aliases: DnsResolverName

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

### Microsoft.Azure.PowerShell.Cmdlets.DnsResolver.Models.Api20200401Preview.IDnsResolver

### Microsoft.Azure.PowerShell.Cmdlets.DnsResolver.Models.Api20200401Preview.ISubResource

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

