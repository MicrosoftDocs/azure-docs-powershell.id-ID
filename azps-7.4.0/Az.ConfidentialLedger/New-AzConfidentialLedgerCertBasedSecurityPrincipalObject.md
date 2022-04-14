---
external help file: ''
Module Name: Az.ConfidentialLedger
online version: https://docs.microsoft.com/powershell/module/az.ConfidentialLedger/new-AzConfidentialLedgerCertBasedSecurityPrincipalObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConfidentialLedger/help/New-AzConfidentialLedgerCertBasedSecurityPrincipalObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConfidentialLedger/help/New-AzConfidentialLedgerCertBasedSecurityPrincipalObject.md
ms.openlocfilehash: d85825763ccf1ddbba17d857d0813a4d1a4e94a4
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141839987"
---
# New-AzConfidentialLedgerCertBasedSecurityPrincipalObject

## SYNOPSIS
Membuat objek dalam memori untuk CertBasedSecurityPrincipal.

## SYNTAX

```
New-AzConfidentialLedgerCertBasedSecurityPrincipalObject [-Cert <String>] [-LedgerRoleName <LedgerRoleName>]
 [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk CertBasedSecurityPrincipal.

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

Membuat AadBasedSecurityPrincipalObject yang mungkin digunakan untuk `Az.ConfidentialLedger` perintah.

## PARAMETERS

### -Cert
Kunci publik dari user cert (.pem atau .cer).

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
LedgerRole terkait dengan Security Principal of Ledger.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ConfidentialLedger.Models.Api20210513Preview.CertBasedSecurityPrincipal

## CATATAN

ALIAS

## RELATED LINKS

