---
external help file: ''
Module Name: Az.Cdn
online version: https://docs.microsoft.com/powershell/module/az.Cdn/new-AzFrontDoorCdnRuleRouteConfigurationOverrideActionObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/help/New-AzFrontDoorCdnRuleRouteConfigurationOverrideActionObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/help/New-AzFrontDoorCdnRuleRouteConfigurationOverrideActionObject.md
ms.openlocfilehash: f98f5eea2262e85fbc656156ca42ab672884f58a
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145549579"
---
# New-AzFrontDoorCdnRuleRouteConfigurationOverrideActionObject

## SYNOPSIS
Buat objek dalam memori untuk DeliveryRuleRouteConfigurationOverrideAction.

## SYNTAX

```
New-AzFrontDoorCdnRuleRouteConfigurationOverrideActionObject -Name <DeliveryRuleAction>
 [-CacheConfigurationCacheBehavior <RuleCacheBehavior>] [-CacheConfigurationCacheDuration <String>]
 [-CacheConfigurationIsCompressionEnabled <RuleIsCompressionEnabled>]
 [-CacheConfigurationQueryParameter <String>]
 [-CacheConfigurationQueryStringCachingBehavior <RuleQueryStringCachingBehavior>] [-OriginGroupId <String>]
 [-OriginGroupOverrideForwardingProtocol <ForwardingProtocol>] [<CommonParameters>]
```

## DESCRIPTION
Buat objek dalam memori untuk DeliveryRuleRouteConfigurationOverrideAction.

## EXAMPLES

### Contoh 1: {{ Tambahkan judul di sini }}
```powershell
{{ Add code here }}
```

```output
{{ Add output here }}
```

{{ Tambahkan deskripsi di sini }}

### Contoh 2: {{ Tambahkan judul di sini }}
```powershell
{{ Add code here }}
```

```output
{{ Add output here }}
```

{{ Tambahkan deskripsi di sini }}

## PARAMETERS

### -CacheConfigurationCacheBehavior
Perilaku penembolokan untuk permintaan.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Support.RuleCacheBehavior
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CacheConfigurationCacheDuration
Durasi konten perlu di-cache.
Format yang diizinkan adalah [d.]hh:mm:ss.

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

### -CacheConfigurationIsCompressionEnabled
Menunjukkan apakah pemadatan konten diaktifkan.
Jika pemadatan diaktifkan, konten akan disajikan sebagai dikompresi jika pengguna meminta versi terkompresi.
Konten tidak akan dikompresi di AzureFrontDoor saat konten yang diminta lebih kecil dari 1 byte atau lebih besar dari 1 MB.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Support.RuleIsCompressionEnabled
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CacheConfigurationQueryParameter
parameter kueri untuk disertakan atau dikecualikan (dipisahkan koma).

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

### -CacheConfigurationQueryStringCachingBehavior
Menentukan bagaimana Frontdoor menyimpan permintaan yang menyertakan string kueri.
Anda dapat mengabaikan string kueri apa pun saat penembolokan, mengabaikan string kueri tertentu, menyimpan cache setiap permintaan dengan URL unik, atau menyimpan string kueri tertentu.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Support.RuleQueryStringCachingBehavior
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Nama tindakan untuk aturan pengiriman.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Support.DeliveryRuleAction
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OriginGroupId
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

### -OriginGroupOverrideForwardingProtocol
Protokol yang akan digunakan aturan ini saat meneruskan lalu lintas ke backend.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Support.ForwardingProtocol
Parameter Sets: (All)
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

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.Api20210601.DeliveryRuleRouteConfigurationOverrideAction

## NOTES

ALIAS

## RELATED LINKS

