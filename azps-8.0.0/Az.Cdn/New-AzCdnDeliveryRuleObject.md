---
external help file: ''
Module Name: Az.Cdn
online version: https://docs.microsoft.com/powershell/module/az.Cdn/new-AzCdnDeliveryRuleObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/help/New-AzCdnDeliveryRuleObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/help/New-AzCdnDeliveryRuleObject.md
ms.openlocfilehash: 5130b5ce51ef42e88522eda8af97a98dcf41e722
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145518886"
---
# New-AzCdnDeliveryRuleObject

## SYNOPSIS
Buat objek dalam memori untuk DeliveryRule.

## SYNTAX

```
New-AzCdnDeliveryRuleObject -Action <IDeliveryRuleAction1[]> -Order <Int32>
 [-Condition <IDeliveryRuleCondition[]>] [-Name <String>] [<CommonParameters>]
```

## DESCRIPTION
Buat objek dalam memori untuk DeliveryRule.

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

### -Tindakan
Daftar tindakan yang dijalankan ketika semua kondisi aturan terpenuhi.
Untuk membuat, lihat bagian CATATAN untuk properti ACTION dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.Api20210601.IDeliveryRuleAction1[]
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Kondisi
Daftar kondisi yang harus dicocokkan agar tindakan dijalankan.
Untuk membuat, lihat bagian CATATAN untuk properti CONDITION dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.Api20210601.IDeliveryRuleCondition[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Nama aturan.

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

### -Pesanan
Urutan di mana aturan diterapkan untuk titik akhir.
Nilai yang mungkin {0,1,2,3,.........}.
Aturan dengan urutan yang lebih rendah akan diterapkan sebelum aturan dengan urutan yang lebih besar.
Aturan dengan urutan 0 adalah aturan khusus.
Ini tidak memerlukan kondisi dan tindakan apa pun yang tercantum di dalamnya akan selalu diterapkan.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.Api20210601.DeliveryRule

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


ACTION <IDeliveryRuleAction1[]>: Daftar tindakan yang dijalankan ketika semua kondisi aturan terpenuhi.
  - `Name <DeliveryRuleAction>`: Nama tindakan untuk aturan pengiriman.

CONDITION <IDeliveryRuleCondition[]>: Daftar kondisi yang harus dicocokkan agar tindakan dijalankan.
  - `Name <MatchVariable>`: Nama kondisi untuk aturan pengiriman.

## RELATED LINKS

