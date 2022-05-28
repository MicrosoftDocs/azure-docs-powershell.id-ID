---
external help file: ''
Module Name: Az.Cdn
online version: https://docs.microsoft.com/powershell/module/az.Cdn/new-AzFrontDoorCdnCustomDomainTlsSettingParametersObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/help/New-AzFrontDoorCdnCustomDomainTlsSettingParametersObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/help/New-AzFrontDoorCdnCustomDomainTlsSettingParametersObject.md
ms.openlocfilehash: 0f561ca35aa10c4955e95361cf8fd0728918d0e2
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145501630"
---
# New-AzFrontDoorCdnCustomDomainTlsSettingParametersObject

## SYNOPSIS
Buat objek dalam memori untuk AFDDomainHttpsParameters.

## SYNTAX

```
New-AzFrontDoorCdnCustomDomainTlsSettingParametersObject -CertificateType <AfdCertificateType>
 [-MinimumTlsVersion <AfdMinimumTlsVersion>] [-Secret <IResourceReference>] [<CommonParameters>]
```

## DESCRIPTION
Buat objek dalam memori untuk AFDDomainHttpsParameters.

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

### -CertificateType
Menentukan sumber sertifikat SSL.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Support.AfdCertificateType
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MinimumTlsVersion
Versi protokol TLS yang akan digunakan untuk Https.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Support.AfdMinimumTlsVersion
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Rahasia
Referensi sumber daya ke rahasia.
Ie. subs/rg/profile/secret.
Untuk membuat, lihat bagian CATATAN untuk properti SECRET dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.Api20210601.IResourceReference
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

### Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.Api20210601.AfdDomainHttpsParameters

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


RAHASIA <IResourceReference>: Referensi sumber daya ke rahasia. Ie. subs/rg/profile/secret.
  - `[Id <String>]`: ID Sumber Daya.

## RELATED LINKS

