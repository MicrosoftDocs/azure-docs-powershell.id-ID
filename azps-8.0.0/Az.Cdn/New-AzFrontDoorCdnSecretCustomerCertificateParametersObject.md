---
external help file: ''
Module Name: Az.Cdn
online version: https://docs.microsoft.com/powershell/module/az.Cdn/new-AzFrontDoorCdnSecretCustomerCertificateParametersObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/help/New-AzFrontDoorCdnSecretCustomerCertificateParametersObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/help/New-AzFrontDoorCdnSecretCustomerCertificateParametersObject.md
ms.openlocfilehash: 3b5f7b58c236c5955ea956d90e45b36811252faf
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145552634"
---
# New-AzFrontDoorCdnSecretCustomerCertificateParametersObject

## SYNOPSIS
Buat objek dalam memori untuk CustomerCertificateParameters.

## SYNTAX

```
New-AzFrontDoorCdnSecretCustomerCertificateParametersObject -Type <SecretType> [-SecretSourceId <String>]
 [-SecretVersion <String>] [-SubjectAlternativeName <String[]>] [-UseLatestVersion <Boolean>]
 [<CommonParameters>]
```

## DESCRIPTION
Buat objek dalam memori untuk CustomerCertificateParameters.

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

### -SecretSourceId
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

### -SecretVersion
Versi rahasia yang akan digunakan.

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

### -SubjectAlternativeName
Daftar WAN.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Type
Jenis sumber daya rahasia.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Support.SecretType
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseLatestVersion
Apakah akan menggunakan versi terbaru untuk sertifikat.

```yaml
Type: System.Boolean
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

### Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.Api20210601.CustomerCertificateParameters

## NOTES

ALIAS

## RELATED LINKS

