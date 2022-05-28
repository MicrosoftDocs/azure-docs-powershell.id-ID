---
external help file: ''
Module Name: Az.Cdn
online version: https://docs.microsoft.com/powershell/module/az.Cdn/new-AzCdnUrlRedirectActionObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/help/New-AzCdnUrlRedirectActionObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/help/New-AzCdnUrlRedirectActionObject.md
ms.openlocfilehash: 6b2857d3f2c86adf3cf6b011409c38ff49287463
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145620595"
---
# New-AzCdnUrlRedirectActionObject

## SYNOPSIS
Buat objek dalam memori untuk UrlRedirectAction.

## SYNTAX

```
New-AzCdnUrlRedirectActionObject -Name <DeliveryRuleAction> -ParameterRedirectType <RedirectType>
 [-ParameterCustomFragment <String>] [-ParameterCustomHostname <String>] [-ParameterCustomPath <String>]
 [-ParameterCustomQueryString <String>] [-ParameterDestinationProtocol <DestinationProtocol>]
 [<CommonParameters>]
```

## DESCRIPTION
Buat objek dalam memori untuk UrlRedirectAction.

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

### -ParameterCustomFragment
Fragmen untuk ditambahkan ke URL pengalihan.
Fragmen adalah bagian dari URL yang muncul setelah #.
Jangan sertakan #.

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

### -ParameterCustomHostname
Host untuk dialihkan.
Biarkan kosong untuk menggunakan host masuk sebagai host tujuan.

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

### -ParameterCustomPath
Jalur lengkap untuk mengalihkan.
Jalur tidak boleh kosong dan harus dimulai dengan /.
Biarkan kosong untuk menggunakan jalur masuk sebagai jalur tujuan.

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

### -ParameterCustomQueryString
Kumpulan string kueri yang akan ditempatkan di URL pengalihan.
Mengatur nilai ini akan menggantikan string kueri yang ada; biarkan kosong untuk mempertahankan string kueri masuk.
String kueri harus dalam \<key\>=\<value\> format.
? dan & akan ditambahkan secara otomatis sehingga jangan sertakan.

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

### -ParameterDestinationProtocol
Protokol yang digunakan untuk pengalihan.
Nilai defaultnya adalah MatchRequest.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Support.DestinationProtocol
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ParameterRedirectType
Jenis pengalihan yang akan digunakan aturan saat mengalihkan lalu lintas.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Support.RedirectType
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

### Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.Api20210601.UrlRedirectAction

## NOTES

ALIAS

## RELATED LINKS

