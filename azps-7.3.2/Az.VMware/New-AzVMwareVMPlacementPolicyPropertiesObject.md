---
external help file: ''
Module Name: Az.VMware
online version: https://docs.microsoft.com/powershell/module/az.VMware/new-AzVMwareVMPlacementPolicyPropertiesObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/VMware/help/New-AzVMwareVMPlacementPolicyPropertiesObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/VMware/help/New-AzVMwareVMPlacementPolicyPropertiesObject.md
ms.openlocfilehash: ce22b1f79fcf13ea340286bdc070370c9aed9327
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143235233"
---
# New-AzVMwareVMPlacementPolicyPropertiesObject

## SYNOPSIS
Membuat objek dalam memori untuk VMPlacementPolicyProperties.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.vmware/new-azvmwarevmplacementpolicypropertiesobject) untuk informasi terbaru.

## SYNTAX

```
New-AzVMwareVMPlacementPolicyPropertiesObject -AffinityType <AffinityType> -Type <PlacementPolicyType>
 -VMMember <String[]> [-DisplayName <String>] [-State <PlacementPolicyState>] [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk VMPlacementPolicyProperties.

## EXAMPLES

### Contoh 1: Membuat objek dalam memori untuk VMPlacementPolicyProperties.
```powershell
PS C:\> New-AzVMwareVMPlacementPolicyPropertiesObject -AffinityType 'Affinity' -Type 'VmVm' -VMMember @{"abc"="123"}

DisplayName ProvisioningState State AffinityType VMMember
----------- ----------------- ----- ------------ --------
                                    Affinity     {System.Collections.Hashtable}
```

Membuat objek dalam memori untuk VMPlacementPolicyProperties.

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

### Microsoft.Azure.PowerShell.Cmdlets.VMware.Models.Api20211201.VMPlacementPolicyProperties

## NOTES

ALIAS

## RELATED LINKS

