---
external help file: ''
Module Name: Az.Cdn
online version: https://docs.microsoft.com/powershell/module/az.Cdn/new-AzFrontDoorCdnSecretUrlSigningKeyParametersObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/help/New-AzFrontDoorCdnSecretUrlSigningKeyParametersObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/help/New-AzFrontDoorCdnSecretUrlSigningKeyParametersObject.md
ms.openlocfilehash: 52762ffb46233c895d7187d37daea0e0b01f2138
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145523239"
---
# New-AzFrontDoorCdnSecretUrlSigningKeyParametersObject

## SYNOPSIS
Buat objek dalam memori untuk UrlSigningKeyParameters.

## SYNTAX

```
New-AzFrontDoorCdnSecretUrlSigningKeyParametersObject -KeyId <String> -Type <SecretType>
 [-SecretSourceId <String>] [-SecretVersion <String>] [<CommonParameters>]
```

## DESCRIPTION
Buat objek dalam memori untuk UrlSigningKeyParameters.

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

### -KeyId
Menentukan Id kunci yang ditentukan pelanggan. Id ini akan ada dalam permintaan masuk untuk menunjukkan kunci yang digunakan untuk membentuk hash.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.Api20210601.UrlSigningKeyParameters

## NOTES

ALIAS

## RELATED LINKS

