---
external help file: ''
Module Name: Az.Cdn
online version: https://docs.microsoft.com/powershell/module/az.Cdn/new-AzCdnResponseBasedOriginErrorDetectionParametersObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/help/New-AzCdnResponseBasedOriginErrorDetectionParametersObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/help/New-AzCdnResponseBasedOriginErrorDetectionParametersObject.md
ms.openlocfilehash: 3fe5a905eea4cb4fbf0c825f6a12e1f552aa332d
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145516546"
---
# New-AzCdnResponseBasedOriginErrorDetectionParametersObject

## SYNOPSIS
Buat objek dalam memori untuk ResponseBasedOriginErrorDetectionParameters.

## SYNTAX

```
New-AzCdnResponseBasedOriginErrorDetectionParametersObject [-HttpErrorRange <IHttpErrorRangeParameters[]>]
 [-ResponseBasedDetectedErrorType <ResponseBasedDetectedErrorTypes>]
 [-ResponseBasedFailoverThresholdPercentage <Int32>] [<CommonParameters>]
```

## DESCRIPTION
Buat objek dalam memori untuk ResponseBasedOriginErrorDetectionParameters.

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

### -HttpErrorRange
Daftar rentang kode status Http yang dianggap sebagai kesalahan server untuk asal dan ditandai sebagai tidak sehat.
Untuk membuat, lihat bagian CATATAN untuk properti HTTPERRORRANGE dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.Api20210601.IHttpErrorRangeParameters[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResponseBasedDetectedErrorType
Jenis kesalahan respons untuk permintaan pengguna nyata yang asalnya akan dianggap tidak sehat.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Support.ResponseBasedDetectedErrorTypes
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResponseBasedFailoverThresholdPercentage
Persentase permintaan yang gagal dalam sampel di mana failover harus dipicu.

```yaml
Type: System.Int32
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

### Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.Api20210601.ResponseBasedOriginErrorDetectionParameters

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


HTTPERRORRANGE <IHttpErrorRangeParameters[]>: Daftar rentang kode status Http yang dianggap sebagai kesalahan server untuk asal dan ditandai sebagai tidak sehat.
  - `[Begin <Int32?>]`: Awal inklusif dari rentang kode status http.
  - `[End <Int32?>]`: Akhir inklusif dari rentang kode status http.

## RELATED LINKS

