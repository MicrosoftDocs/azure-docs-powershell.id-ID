---
external help file: ''
Module Name: Az.VMware
online version: https://docs.microsoft.com/powershell/module/az.VMware/new-AzVMwareVmHostPlacementPolicyPropertiesObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/VMware/help/New-AzVMwareVmHostPlacementPolicyPropertiesObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/VMware/help/New-AzVMwareVmHostPlacementPolicyPropertiesObject.md
ms.openlocfilehash: baecf012513f669ce6f4d08cc644bf28b23f0b04
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142433387"
---
# New-AzVMwareVmHostPlacementPolicyPropertiesObject

## SYNOPSIS
Membuat objek dalam memori untuk VmHostPlacementPolicyProperties.

## SYNTAX

```
New-AzVMwareVmHostPlacementPolicyPropertiesObject -AffinityType <AffinityType> -HostMember <String[]>
 -Type <PlacementPolicyType> -VMMember <String[]> [-DisplayName <String>] [-State <PlacementPolicyState>]
 [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk VmHostPlacementPolicyProperties.

## EXAMPLES

### Contoh 1: Membuat objek dalam memori untuk VmHostPlacementPolicyProperties.
```powershell
New-AzVMwareVmHostPlacementPolicyPropertiesObject -AffinityType 'AntiAffinity' -HostMember @{"abc"="123"}  -Type 'VmHost' -VMMember @{"abc"="123"}
```
```output
DisplayName ProvisioningState State AffinityType HostMember                     VMMember
----------- ----------------- ----- ------------ ----------                     --------
                                    AntiAffinity {System.Collections.Hashtable} {System.Collections.Hashtable}
```

Membuat objek dalam memori untuk VmHostPlacementPolicyProperties.

## PARAMETERS

### -AffinityType
tipe afeinitas kebijakan penempatan.

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

### -HostMember
Daftar anggota host.

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

### -Negara Bagian
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

### -Tipe
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
Daftar anggota mesin virtual.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.VMware.Models.Api20211201.VMHostPlacementPolicyProperties

## CATATAN

ALIAS

## RELATED LINKS

