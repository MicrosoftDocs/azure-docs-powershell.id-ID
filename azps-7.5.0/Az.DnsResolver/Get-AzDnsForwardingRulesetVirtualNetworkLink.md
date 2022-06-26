---
external help file: ''
Module Name: Az.DnsResolver
online version: https://docs.microsoft.com/powershell/module/az.dnsresolver/get-azdnsforwardingrulesetvirtualnetworklink
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DnsResolver/help/Get-AzDnsForwardingRulesetVirtualNetworkLink.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DnsResolver/help/Get-AzDnsForwardingRulesetVirtualNetworkLink.md
ms.openlocfilehash: 063c7394f09dc4ae6953cdb1a1ae87cb86dac1b2
ms.sourcegitcommit: 5df8b100721844736630242c724da453a2168434
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/26/2022
ms.locfileid: "146589540"
---
# Get-AzDnsForwardingRulesetVirtualNetworkLink

## SYNOPSIS
Mendapatkan properti tautan jaringan virtual ke set aturan penerusan DNS.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.dnsresolver/get-azdnsforwardingrulesetvirtualnetworklink) untuk informasi terbaru.

## SYNTAX

### Daftar (Default)
```
Get-AzDnsForwardingRulesetVirtualNetworkLink -DnsForwardingRulesetName <String> -ResourceGroupName <String>
 [-SubscriptionId <String[]>] [-Top <Int32>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Dapatkan
```
Get-AzDnsForwardingRulesetVirtualNetworkLink -DnsForwardingRulesetName <String> -Name <String>
 -ResourceGroupName <String> [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzDnsForwardingRulesetVirtualNetworkLink -InputObject <IDnsResolverIdentity> [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan properti tautan jaringan virtual ke set aturan penerusan DNS.

## EXAMPLES

### Contoh 1: Mencantumkan tautan jaringan virtual di bawah set aturan penerusan DNS
```powershell
Get-AzDnsForwardingRulesetVirtualNetworkLink -DnsForwardingRulesetName pstestdnsresolvername -ResourceGroupName powershell-test-rg
```

```output
Name                   Type                                            Etag
----                   ----                                            ----
samplevnetLink1  Microsoft.Network/dnsForwardingRuleset/virtualNetworkLinks "0b008451-0000-0800-0000-60402b960000"
samplevnetLink2  Microsoft.Network/dnsForwardingRuleset/virtualNetworkLinks "0b0071aa-0000-0800-0000-60406a2d0000"
```

Perintah ini mendapatkan semua tautan jaringan virtual berdasarkan nama

### Contoh 2: Dapatkan tautan jaringan virtual tunggal berdasarkan nama
```powershell
Get-AzDnsResolverVirtualNetworkLink -DnsForwardingRulesetName pstestdnsresolvername -Name samplevnetLink1 -ResourceGroupName powershell-test-rg
```

```output
Name                  Type                                            Etag
----                  ----                                            ----
samplevnetLink1 Microsoft.Network/dnsForwardingRuleset/virtualNetworkLinks "0b008451-0000-0800-0000-60402b960000"
```

Perintah ini mendapatkan tautan jaringan virtual tunggal berdasarkan nama

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
Nama kumpulan aturan penerusan DNS.

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
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

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

### -Name
Nama tautan jaringan virtual.

```yaml
Type: System.String
Parameter Sets: Get
Aliases: VirtualNetworkLinkName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.
Nama tidak peka huruf besar/kecil.

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

### -Atas
Jumlah maksimum hasil yang akan dikembalikan.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DnsResolver.Models.IDnsResolverIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DnsResolver.Models.Api20200401Preview.IVirtualNetworkLink

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT `<IDnsResolverIdentity>`: Parameter Identitas
  - `[DnsForwardingRulesetName <String>]`: Nama kumpulan aturan penerusan DNS.
  - `[DnsResolverName <String>]`: Nama pemecah masalah DNS.
  - `[ForwardingRuleName <String>]`: Nama aturan penerusan.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[InboundEndpointName <String>]`: Nama titik akhir masuk untuk pemecah masalah DNS.
  - `[OutboundEndpointName <String>]`: Nama titik akhir keluar untuk pemecah masalah DNS.
  - `[ResourceGroupName <String>]`: Nama grup sumber daya. Nama tidak peka huruf besar/kecil.
  - `[SubscriptionId <String>]`: ID langganan target.
  - `[VirtualNetworkLinkName <String>]`: Nama tautan jaringan virtual.
  - `[VirtualNetworkName <String>]`: Nama jaringan virtual.

## RELATED LINKS

