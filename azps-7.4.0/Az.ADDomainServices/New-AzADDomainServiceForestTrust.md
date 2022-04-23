---
external help file: ''
Module Name: Az.ADDomainServices
online version: https://docs.microsoft.com/powershell/module/az.ADDomainServices/new-AzADDomainServiceForestTrust
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ADDomainServices/help/New-AzADDomainServiceForestTrust.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ADDomainServices/help/New-AzADDomainServiceForestTrust.md
ms.openlocfilehash: 90c03a02e5e91a908d25ba236fe3751e2052ec1f
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143321534"
---
# New-AzADDomainServiceForestTrust

## SYNOPSIS
Membuat objek dalam memori untuk ForestTrust

## SYNTAX

```
New-AzADDomainServiceForestTrust [-FriendlyName <String>] [-RemoteDnsIP <String>] [-TrustDirection <String>]
 [-TrustedDomainFqdn <String>] [-TrustPassword <SecureString>] [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk ForestTrust

## EXAMPLES

### Contoh 1: Create ServiceForestTrust untuk ADDomain
```powershell
New-AzADDomainServiceForestTrust -FriendlyName FriendlyNameTest
```

```output
FriendlyName     RemoteDnsIP TrustDirection TrustPassword TrustedDomainFqdn
------------     ----------- -------------- ------------- -----------------
FriendlyNameTest
```

Membuat ServiceForestTrust untuk ADDomain

## PARAMETERS

### -FriendlyName
Nama yang mudah dikenali.

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

### -RemoteDnsIP
Ip Dns Jarak Jauh.

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

### -TrustDirection
Arah Kepercayaan.

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

### -TrustedDomainFqdn
FQDN Domain Tepercaya.

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

### -TrustPassword
Percayai Kata Sandi.

```yaml
Type: System.Security.SecureString
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

### Microsoft.Azure.PowerShell.Cmdlets.ADDomainServices.Models.Api202001.ForestTrust

## NOTES

ALIAS

## RELATED LINKS

