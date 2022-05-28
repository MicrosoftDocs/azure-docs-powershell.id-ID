---
external help file: ''
Module Name: Az.ServiceLinker
online version: https://docs.microsoft.com/powershell/module/az.ServiceLinker/new-azservicelinkerserviceprincipalsecretauthinfoobject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceLinker/help/New-AzServiceLinkerServicePrincipalSecretAuthInfoObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceLinker/help/New-AzServiceLinkerServicePrincipalSecretAuthInfoObject.md
ms.openlocfilehash: 50d6e18852ab79e0b1a781ba78295371df6b3f18
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145532905"
---
# New-AzServiceLinkerServicePrincipalSecretAuthInfoObject

## SYNOPSIS
Buat objek dalam memori untuk ServicePrincipalSecretAuthInfo.

## SYNTAX

```
New-AzServiceLinkerServicePrincipalSecretAuthInfoObject -ClientId <String> -PrincipalId <String>
 -Secret <String> [<CommonParameters>]
```

## DESCRIPTION
Buat objek dalam memori untuk ServicePrincipalSecretAuthInfo.

## EXAMPLES

### Contoh 1: Membuat AuthInfo dari jenis rahasia perwakilan layanan
```powershell
New-AzServiceLinkerServicePrincipalSecretAuthInfoObject -ClientId 00000000-0000-0000-0000-000000000000 -PrincipalId 00000000-0000-0000-0000-000000000000 -Secret secret
```

```output

AuthType               ClientId                             PrincipalId
--------               --------                             -----------
servicePrincipalSecret 00000000-0000-0000-0000-000000000000 00000000-0000-0000-0000-00…

```

Membuat AuthInfo dari jenis rahasia perwakilan layanan

## PARAMETERS

### -ClientId
ClientId aplikasi ServicePrincipal untuk autentikasi servicePrincipal.

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

### -PrincipalId
Id Utama untuk autentikasi servicePrincipal.

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

### -Rahasia
Rahasia untuk servicePrincipal auth.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ServiceLinker.Models.Api20220501.ServicePrincipalSecretAuthInfo

## NOTES

ALIAS

## RELATED LINKS

