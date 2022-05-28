---
external help file: ''
Module Name: Az.ServiceLinker
online version: https://docs.microsoft.com/powershell/module/az.ServiceLinker/new-azservicelinkerazureresourceobject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceLinker/help/New-AzServiceLinkerAzureResourceObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ServiceLinker/help/New-AzServiceLinkerAzureResourceObject.md
ms.openlocfilehash: 6069a1443c9782ae837eaaabecfa0157718647e1
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145524502"
---
# New-AzServiceLinkerAzureResourceObject

## SYNOPSIS
Buat objek dalam memori untuk AzureResource.

## SYNTAX

```
New-AzServiceLinkerAzureResourceObject -Id <String> [-ConnectAsKubernetesCsiDriver <Boolean>]
 [<CommonParameters>]
```

## DESCRIPTION
Buat objek dalam memori untuk AzureResource.

## EXAMPLES

### Contoh 1: Membuat objek sumber daya target untuk sumber daya azure
```powershell
New-AzServiceLinkerAzureResourceObject -Id /subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/servicelinker-test-group/providers/Microsoft.KeyVault/vaults/servicelinker-test-kv -ConnectAsKubernetesCsiDriver 1
```

```output
Id
--
/subscriptions/00000000-0000-0000-0000-000000000000/resourceGroups/servicelinker-test-… 

```

Membuat AzureResourceObject sebagai param `-TargetService`

## PARAMETERS

### -ConnectAsKubernetesCsiDriver
True jika terhubung melalui Driver CSI Kubernetes.
Sumber harus AKS dan target harus KeyVault.

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

### -Id
Id sumber daya azure.

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

### Microsoft.Azure.PowerShell.Cmdlets.ServiceLinker.Models.Api20220501.AzureResource

## NOTES

ALIAS

## RELATED LINKS

