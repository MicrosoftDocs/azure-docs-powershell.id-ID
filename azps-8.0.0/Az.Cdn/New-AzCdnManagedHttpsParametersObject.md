---
external help file: ''
Module Name: Az.Cdn
online version: https://docs.microsoft.com/powershell/module/az.Cdn/new-AzCdnManagedHttpsParametersObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/help/New-AzCdnManagedHttpsParametersObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/help/New-AzCdnManagedHttpsParametersObject.md
ms.openlocfilehash: cb9434e647261e8a8e263654ca0f263a6d71f718
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145536307"
---
# New-AzCdnManagedHttpsParametersObject

## SYNOPSIS
Buat objek dalam memori untuk CdnManagedHttpsParameters.

## SYNTAX

```
New-AzCdnManagedHttpsParametersObject -CertificateSource <CertificateSource>
 -CertificateSourceParameterCertificateType <CertificateType> -ProtocolType <ProtocolType>
 [-MinimumTlsVersion <MinimumTlsVersion>] [<CommonParameters>]
```

## DESCRIPTION
Buat objek dalam memori untuk CdnManagedHttpsParameters.

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

### -CertificateSource
Menentukan sumber sertifikat SSL.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Support.CertificateSource
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -CertificateSourceParameterCertificateType
Jenis sertifikat yang digunakan.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Support.CertificateType
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
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Support.MinimumTlsVersion
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProtocolType
Menentukan protokol ekstensi TLS yang digunakan untuk pengiriman yang aman.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Support.ProtocolType
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

### Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.Api20210601.CdnManagedHttpsParameters

## NOTES

ALIAS

## RELATED LINKS

