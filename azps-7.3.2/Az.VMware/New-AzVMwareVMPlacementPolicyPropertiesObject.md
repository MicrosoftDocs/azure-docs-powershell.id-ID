---
external help file: ''
Module Name: Az.VMware
online version: https://docs.microsoft.com/powershell/module/az.VMware/new-AzVMwareVMPlacementPolicyPropertiesObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/VMware/help/New-AzVMwareVMPlacementPolicyPropertiesObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/VMware/help/New-AzVMwareVMPlacementPolicyPropertiesObject.md
ms.openlocfilehash: f7804bb8048a0d74fdab0ee07020428af288106a
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140182596"
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
PS C:\> New-AzVMwareVMPlacementPolicyPropertiesObject -AffinityType 'Affinity' -Type 'VmVm' -VMMember @{"abc"="123"}

DisplayName ProvisioningState State AffinityType VMMember
----------- ----------------- ----- ------------ --------
                                    Affinity     {System.Collections.Hashtable}
```

Buat objek dalam memori untuk VMPlacementPolicyProperties.

## PARAMETERS

### -AffinityType
tipe afiliasi kebijakan penempatan.

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
tipe kebijakan penempatan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.VMware.Models.Api20211201.VMPlacementPolicyProperties

## CATATAN

ALIAS

## RELATED LINKS

