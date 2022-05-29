---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
online version: https://docs.microsoft.com/powershell/module/az.compute/repair-azvmssservicefabricupdatedomain
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Repair-AzVmssServiceFabricUpdateDomain.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Repair-AzVmssServiceFabricUpdateDomain.md
ms.openlocfilehash: aed909f2fe1bac5218c3e91470f76eaceb3c74d3
ms.sourcegitcommit: 321c644cf2161807a71e1af318fc5c5311d22e25
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/25/2022
ms.locfileid: "145778447"
---
# Repair-AzVmssServiceFabricUpdateDomain

## SYNOPSIS
Domain pembaruan platform manual berjalan untuk memperbarui komputer virtual dalam set skala komputer virtual service fabric.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.compute/repair-azvmssservicefabricupdatedomain) untuk informasi terbaru.

## SYNTAX

### DefaultParameter (Default)
```
Repair-AzVmssServiceFabricUpdateDomain [-ResourceGroupName] <String> [-VMScaleSetName] <String>
 [-PlatformUpdateDomain] <Int32> [-Zone <String>] [-PlacementGroupId <String>] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ResourceIdParameter
```
Repair-AzVmssServiceFabricUpdateDomain [-PlatformUpdateDomain] <Int32> [-Zone <String>]
 [-PlacementGroupId <String>] [-ResourceId] <String> [-AsJob] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ObjectParameter
```
Repair-AzVmssServiceFabricUpdateDomain [-PlatformUpdateDomain] <Int32> [-Zone <String>]
 [-PlacementGroupId <String>] [-VirtualMachineScaleSet] <PSVirtualMachineScaleSet> [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Paksa domain pembaruan platform manual berjalan untuk memperbarui komputer virtual dalam set skala komputer virtual service fabric.

## EXAMPLES

### Contoh 1
```powershell
Repair-AzVmssServiceFabricUpdateDomain -ResourceGroupName $rgname -VMScaleSetName $vmssName -PlatformUpdateDomain 0
```

Perintah ini memaksa pembaruan service fabric berjalan pada UD 0 untuk set skala komputer virtual yang ditentukan oleh nama grup sumber daya dan nama set skala.

### Contoh 2
```powershell
$vmss = Get-AzVmss -ResourceGroupName $rgname -VMScaleSetName $vmssName
Repair-AzVmssServiceFabricUpdateDomain -VirtualMachineScaleSet $vmss -PlatformUpdateDomain 1
```

Perintah ini memaksa pembaruan service fabric berjalan pada UD 1 untuk set skala komputer virtual yang ditentukan oleh objek set skala VM.

### Contoh: 3
```powershell
Repair-AzVmssServiceFabricUpdateDomain -ResourceId $resourceId  -PlatformUpdateDomain 2;
```

Perintah ini memaksa pembaruan service fabric berjalan pada UD 2 untuk set skala komputer virtual yang ditentukan oleh id sumber daya.

## PARAMETERS

### -AsJob
Jalankan cmdlet di latar belakang

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PlacementGroupId
Id Grup Penempatan Vm

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

### -PlatformUpdateDomain
Domain pembaruan platform tempat panduan pemulihan manual diminta.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: DefaultParameter
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceId
Id sumber daya untuk set skala komputer virtual.

```yaml
Type: System.String
Parameter Sets: ResourceIdParameter
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -VirtualMachineScaleSet
Objek set skala komputer virtual lokal

```yaml
Type: Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet
Parameter Sets: ObjectParameter
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -VMScaleSetName
Nama set skala komputer virtual

```yaml
Type: System.String
Parameter Sets: DefaultParameter
Aliases: Name

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Zona
Zona Vm

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

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
Cmdlet tidak dijalankan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

### Microsoft.Azure.Commands.Compute.Automation.Models.PSVirtualMachineScaleSet

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Automation.Models.PSRecoveryWalkResponse

## NOTES

## RELATED LINKS
