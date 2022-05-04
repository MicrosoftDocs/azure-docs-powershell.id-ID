---
external help file: ''
Module Name: Az.DnsResolver
online version: https://docs.microsoft.com/powershell/module/az.dnsresolver/get-azdnsresolveroutboundendpoint
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DnsResolver/help/Get-AzDnsResolverOutboundEndpoint.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DnsResolver/help/Get-AzDnsResolverOutboundEndpoint.md
ms.openlocfilehash: 4e3f8b00c6fb36ff5b10e89e3dba54cfef9a2fe7
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144622398"
---
# Get-AzDnsResolverOutboundEndpoint

## SYNOPSIS
Mendapatkan properti titik akhir keluar untuk pemecah masalah DNS.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.dnsresolver/get-azdnsresolveroutboundendpoint) untuk informasi terbaru.

## SYNTAX

### Daftar (Default)
```
Get-AzDnsResolverOutboundEndpoint -DnsResolverName <String> -ResourceGroupName <String>
 [-SubscriptionId <String[]>] [-Top <Int32>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### Dapatkan
```
Get-AzDnsResolverOutboundEndpoint -DnsResolverName <String> -Name <String> -ResourceGroupName <String>
 [-SubscriptionId <String[]>] [-DefaultProfile <PSObject>] [<CommonParameters>]
```

### GetViaIdentity
```
Get-AzDnsResolverOutboundEndpoint -InputObject <IDnsResolverIdentity> [-DefaultProfile <PSObject>]
 [<CommonParameters>]
```

## DESCRIPTION
Mendapatkan properti titik akhir keluar untuk pemecah masalah DNS.

## EXAMPLES

### Contoh 1: Mencantumkan semua titik akhir keluar di bawah pemecah masalah DNS dalam grup sumber daya 
```powershell
Get-AzDnsResolverOutboundEndpoint -DnsResolverName sampleResolver -ResourceGroupName sampleResouceGroup
```

```output
Name         Type                                             Etag
----         ----                                             ----
sampleOutbound Microsoft.Network/dnsResolvers/outboundEndpoints "0a001a28-0000-0800-0000-60e3846a0000"
sampleOutbound2 Microsoft.Network/dnsResolvers/outboundEndpoints "0a001a27-0000-0800-0000-60e3846a0000"
```
Perintah ini mendapatkan semua titik akhir keluar di bawah pemecah masalah DNS dalam grup sumber daya.

### Contoh 2: Mendapatkan titik akhir keluar tunggal menurut nama 
```powershell
Get-AzDnsResolverOutboundEndpoint -DnsResolverName sampleResolver -Name sampleOutbound -ResourceGroupName sampleResouceGroup
```

```output
Name         Type                                             Etag
----         ----                                             ----
sampleOutbound Microsoft.Network/dnsResolvers/outboundEndpoints "0a001a28-0000-0800-0000-60e3846a0000"
```

Perintah ini mendapatkan titik akhir keluar di bawah pemecah masalah DNS dalam grup sumber daya.

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

### -DnsResolverName
Nama pemecah masalah DNS.

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
Nama titik akhir keluar untuk pemecah masalah DNS.

```yaml
Type: System.String
Parameter Sets: Get
Aliases: OutboundEndpointName

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

### Microsoft.Azure.PowerShell.Cmdlets.DnsResolver.Models.Api20200401Preview.IOutboundEndpoint

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


INPUTOBJECT <IDnsResolverIdentity>: Parameter Identitas
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

