---
external help file: ''
Module Name: Az.VMware
online version: https://docs.microsoft.com/powershell/module/az.VMware/new-AzVMwareVMPlacementPolicyPropertiesObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/VMware/help/New-AzVMwareVMPlacementPolicyPropertiesObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/VMware/help/New-AzVMwareVMPlacementPolicyPropertiesObject.md
ms.openlocfilehash: 0cb05819dd1aa00b4d8798404663c0892ac05006
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144234552"
---
# New-AzVMwareVMPlacementPolicyPropertiesObject

## SYNOPSIS
Buat objek dalam memori untuk VMPlacementPolicyProperties.

## SYNTAX

```
New-AzVMwareVMPlacementPolicyPropertiesObject -AffinityType <AffinityType> -Type <PlacementPolicyType>
 -VMMember <String[]> [-DisplayName <String>] [-State <PlacementPolicyState>] [<CommonParameters>]
```

## DESCRIPTION
Buat objek dalam memori untuk VMPlacementPolicyProperties.

## EXAMPLES

### Contoh 1: Buat objek dalam memori untuk VMPlacementPolicyProperties.
```powershell
New-AzVMwareVMPlacementPolicyPropertiesObject -AffinityType 'Affinity' -Type 'VmVm' -VMMember @{"abc"="123"}
```
```output
DisplayName ProvisioningState State AffinityType VMMember
----------- ----------------- ----- ------------ --------
                                    Affinity     {System.Collections.Hashtable}
```

Buat objek dalam memori untuk VMPlacementPolicyProperties.

## PARAMETERS

### -AffinityType
jenis afinitas kebijakan penempatan.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.VMware.Support.AffinityType
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisplayName
Nama tampilan kebijakan penempatan.

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

### -State
Apakah kebijakan penempatan diaktifkan atau dinonaktifkan.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.VMware.Support.PlacementPolicyState
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Type
jenis kebijakan penempatan.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.VMware.Support.PlacementPolicyType
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VMMember
Daftar anggota komputer virtual.

```yaml
Type: System.String[]
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

### Microsoft.Azure.PowerShell.Cmdlets.VMware.Models.Api20211201.VMPlacementPolicyProperties

## NOTES

ALIAS

## RELATED LINKS

