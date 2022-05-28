---
external help file: ''
Module Name: Az.DnsResolver
online version: https://docs.microsoft.com/powershell/module/az.dnsresolver/new-azdnsresolveroutboundendpoint
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DnsResolver/help/New-AzDnsResolverOutboundEndpoint.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DnsResolver/help/New-AzDnsResolverOutboundEndpoint.md
ms.openlocfilehash: 6813a5531456a607f5c9c0ea4763d97deb71762a
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145501266"
---
# New-AzDnsResolverOutboundEndpoint

## SYNOPSIS
Membuat atau memperbarui titik akhir keluar untuk pemecah masalah DNS.

## SYNTAX

```
New-AzDnsResolverOutboundEndpoint -DnsResolverName <String> -Name <String> -ResourceGroupName <String>
 -Location <String> [-SubscriptionId <String>] [-IfMatch <String>] [-IfNoneMatch <String>]
 [-SubnetId <String>] [-Tag <Hashtable>] [-DefaultProfile <PSObject>] [-AsJob] [-NoWait] [-Confirm] [-WhatIf]
 [<CommonParameters>]
```

## DESCRIPTION
Membuat atau memperbarui titik akhir keluar untuk pemecah masalah DNS.

## EXAMPLES

### Contoh 1: Membuat titik akhir keluar 
```powershell
New-AzDnsResolverOutboundEndpoint -DnsResolverName sampleResolver -Name sampleOutboundEndpoint -ResourceGroupName powershell-test-rg -SubscriptionId ea40042d-63d8-4d02-9261-fb31450e6c67 -SubnetId "/subscriptions/0e5a46b1-de0b-4ec3-a5d7-dda908b4e076/resourceGroups/powershell-test-08b4e076/resourceGroups/powershell-test-rg/providers/Microsoft.Network/virtualNetworks/psvirtualnetworkname16y71mjc/subnets/test-subnet" -Location westus2
```

```output
Location Name                   Type                                             Etag
-------- ----                   ----                                             ----
westus2  sampleOutboundEndpoint Microsoft.Network/dnsResolvers/outboundEndpoints "0a009902-0000-0800-0000-60e378030000"
```

Cmdlet ini membuat titik akhir keluar.

### Contoh 2: Membuat titik akhir keluar dengan tag 
```powershell
New-AzDnsResolverOutboundEndpoint -DnsResolverName sampleResolver -Name sampleOutboundEndpoint -ResourceGroupName powershell-test-rg -SubscriptionId ea40042d-63d8-4d02-9261-fb31450e6c67 -SubnetId "/subscriptions/0e5a46b1-de0b-4ec3-a5d7-dda908b4e076/resourceGroups/powershell-test-08b4e076/resourceGroups/powershell-test-rg/providers/Microsoft.Network/virtualNetworks/psvirtualnetworkname16y71mjc/subnets/test-subnet" -Location westus2 -Tag @{"key0" = "value0"}
```

```output
Location Name                   Type                                             Etag
-------- ----                   ----                                             ----
westus2  sampleOutboundEndpoint Microsoft.Network/dnsResolvers/outboundEndpoints "0a009902-0000-0800-0000-60e378030000"
```

Cmdlet ini membuat titik akhir keluar.

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

### -DnsResolverName
Nama pemecah masalah DNS.

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

### -Lokasi
Lokasi geografis tempat sumber daya berada

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

### -Name
Nama titik akhir keluar untuk pemecah masalah DNS.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: OutboundEndpointName

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
Nama tidak peka huruf besar/kecil.

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

### -SubnetId
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

### Microsoft.Azure.PowerShell.Cmdlets.DnsResolver.Models.Api20200401Preview.IOutboundEndpoint

## NOTES

ALIAS

## RELATED LINKS

