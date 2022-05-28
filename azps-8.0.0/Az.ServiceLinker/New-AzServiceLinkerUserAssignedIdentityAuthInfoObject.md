---
external help file: ''
Module Name: Az.ServiceLinker
online version: https://docs.microsoft.com/powershell/module/az.ServiceLinker/new-azservicelinkeruserassignedidentityauthinfoobject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceLinker/help/New-AzServiceLinkerUserAssignedIdentityAuthInfoObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceLinker/help/New-AzServiceLinkerUserAssignedIdentityAuthInfoObject.md
ms.openlocfilehash: d16e94829db853704dade3e92ce3925d9738da55
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145539936"
---
# New-AzServiceLinkerUserAssignedIdentityAuthInfoObject

## SYNOPSIS
Buat objek dalam memori untuk UserAssignedIdentityAuthInfo.

## SYNTAX

```
New-AzServiceLinkerUserAssignedIdentityAuthInfoObject [-ClientId <String>] [-SubscriptionId <String>]
 [<CommonParameters>]
```

## DESCRIPTION
Buat objek dalam memori untuk UserAssignedIdentityAuthInfo.

## EXAMPLES

### Contoh 1: membuat info autentikasi linker dengan jenis identitas yang ditetapkan pengguna
```powershell
New-AzServiceLinkerUserAssignedIdentityAuthInfoObject -ClientId 00000000-0000-0000-0000-000000000000 -SubscriptionId 00000000-0000-0000-0000-000000000000
```

```output
AuthType             ClientId                             SubscriptionId
--------             --------                             --------------
userAssignedIdentity 00000000-0000-0000-0000-000000000000 00000000-0000-0000-0000-0000… 
```

membuat info autentikasi linker dengan jenis identitas yang ditetapkan pengguna

## PARAMETERS

### -ClientId
Id Klien untuk userAssignedIdentity.

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

### -SubscriptionId
Id langganan untuk userAssignedIdentity.

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

### Microsoft.Azure.PowerShell.Cmdlets.ServiceLinker.Models.Api20220501.UserAssignedIdentityAuthInfo

## NOTES

ALIAS

## RELATED LINKS

