---
external help file: ''
Module Name: Az.ConfidentialLedger
online version: https://docs.microsoft.com/powershell/module/az.ConfidentialLedger/new-AzConfidentialLedgerAADBasedSecurityPrincipalObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConfidentialLedger/help/New-AzConfidentialLedgerAADBasedSecurityPrincipalObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ConfidentialLedger/help/New-AzConfidentialLedgerAADBasedSecurityPrincipalObject.md
ms.openlocfilehash: b1bb2cfe4d98687d797f11349dd3e25b352b988d
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144238780"
---
# New-AzConfidentialLedgerAADBasedSecurityPrincipalObject

## SYNOPSIS
Buat objek dalam memori untuk AADBasedSecurityPrincipal.

## SYNTAX

```
New-AzConfidentialLedgerAADBasedSecurityPrincipalObject [-LedgerRoleName <LedgerRoleName>]
 [-PrincipalId <String>] [-TenantId <String>] [<CommonParameters>]
```

## DESCRIPTION
Buat objek dalam memori untuk AADBasedSecurityPrincipal.

## EXAMPLES

### Contoh 1: Pembuatan objek
```powershell
PS C:\> New-AzConfidentialLedgerAadBasedSecurityPrincipalObject `
  -LedgerRoleName "Administrator" `
  -PrincipalId "34621747-6fc8-4771-a2eb-72f31c461f2e" `
  -TenantId "bce123b9-2b7b-4975-8360-5ca0b9b1cd08"

LedgerRoleName PrincipalId                          TenantId
-------------- -----------                          --------
Administrator  34621747-6fc8-4771-a2eb-72f31c461f2e bce123b9-2b7b-4975-8360-5ca0b9b1cd08
```

Membuat AadBasedSecurityPrincipalObject yang dapat digunakan untuk `Az.ConfidentialLedger` perintah.

## PARAMETERS

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

### -PrincipalId
Id Utama berbasis UUID/GUID dari Perwakilan Keamanan.

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

### -TenantId
Id Penyewa berbasis UUID/GUID dari Perwakilan Keamanan.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ConfidentialLedger.Models.Api20210513Preview.AadBasedSecurityPrincipal

## NOTES

ALIAS

## RELATED LINKS

