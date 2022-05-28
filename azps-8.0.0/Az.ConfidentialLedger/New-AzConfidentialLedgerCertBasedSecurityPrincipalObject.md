---
external help file: ''
Module Name: Az.ConfidentialLedger
online version: https://docs.microsoft.com/powershell/module/az.ConfidentialLedger/new-AzConfidentialLedgerCertBasedSecurityPrincipalObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConfidentialLedger/help/New-AzConfidentialLedgerCertBasedSecurityPrincipalObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConfidentialLedger/help/New-AzConfidentialLedgerCertBasedSecurityPrincipalObject.md
ms.openlocfilehash: d85825763ccf1ddbba17d857d0813a4d1a4e94a4
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145526410"
---
# New-AzConfidentialLedgerCertBasedSecurityPrincipalObject

## SYNOPSIS
Buat objek dalam memori untuk CertBasedSecurityPrincipal.

## SYNTAX

```
New-AzConfidentialLedgerCertBasedSecurityPrincipalObject [-Cert <String>] [-LedgerRoleName <LedgerRoleName>]
 [<CommonParameters>]
```

## DESCRIPTION
Buat objek dalam memori untuk CertBasedSecurityPrincipal.

## EXAMPLES

### Contoh 1: Pembuatan objek
```powershell
PS C:\> New-AzConfidentialLedgerCertBasedSecurityPrincipalObject `
  -Cert "-----BEGIN CERTIFICATE-----********************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************************-----END CERTIFICATE-----" `
  -LedgerRoleName "Reader"

Cert
----
-----BEGIN CERTIFICATE-----MIIBsjCCATigAwIBAgIUZWIbyG79TniQLd2UxJuU74tqrKcwCgYIKoZIzj0EAwMwEDEOMAwGA1UEAwwFdXNlcjAwHhc…
```

Membuat AadBasedSecurityPrincipalObject yang dapat digunakan untuk `Az.ConfidentialLedger` perintah.

## PARAMETERS

### -Cert
Kunci umum sertifikat pengguna (.pem atau .cer).

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

### -LedgerRoleName
LedgerRole yang terkait dengan Perwakilan Keamanan Ledger.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ConfidentialLedger.Support.LedgerRoleName
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

### Microsoft.Azure.PowerShell.Cmdlets.ConfidentialLedger.Models.Api20210513Preview.CertBasedSecurityPrincipal

## NOTES

ALIAS

## RELATED LINKS

