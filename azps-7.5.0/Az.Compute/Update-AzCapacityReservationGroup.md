---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
online version: https://docs.microsoft.com/powershell/module/az.compute/update-azcapacityreservationgroup
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Update-AzCapacityReservationGroup.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Update-AzCapacityReservationGroup.md
ms.openlocfilehash: e1908cbbd7ddae9cfe32ecba61b12254b76c13ef
ms.sourcegitcommit: 82b4008b76d035e4aee733727371765b0d853bed
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145732348"
---
# Update-AzCapacityReservationGroup

## SYNOPSIS
Perbarui Grup Reservasi Kapasitas.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.compute/update-azcapacityreservationgroup) untuk informasi terbaru.

## SYNTAX

### DefaultParameter (Default)
```
Update-AzCapacityReservationGroup [-AsJob] [-Tag <Hashtable>] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### DefaultParameterSet
```
Update-AzCapacityReservationGroup -ResourceGroupName <String> -Name <String> [-AsJob] [-Tag <Hashtable>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObjectParameterSet
```
Update-AzCapacityReservationGroup -CapacityReservationGroup <PSCapacityReservationGroup> [-AsJob]
 [-Tag <Hashtable>] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ResourceIDParameterSet
```
Update-AzCapacityReservationGroup -ResourceId <String> [-AsJob] [-Tag <Hashtable>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Perbarui Grup Reservasi Kapasitas.

## EXAMPLES

### Contoh 1
```powershell
Update-AzCapacityReservationGroup -ResourceGroupName $rgname -Name $capResGroup -Tag @{ CreatedBy = "John" }
```

Memperbarui tag Grup Reservasi Kapasitas.

### Contoh 2
```powershell
Get-AzCapacityReservationGroup -ResourceGroupName $rgname -Name $capResGroup | Update-AzCapacityReservationGroup -Tag @{ CreatedBy = "John" }
```

Memperbarui tag Grup Reservasi Kapasitas menggunakan set parameter InputObject. 

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

### -CapacityReservationGroup
Objek PSCapacityReservationGroup untuk diperbarui.

```yaml
Type: Microsoft.Azure.Commands.Compute.Automation.Models.PSCapacityReservationGroup
Parameter Sets: InputObjectParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
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

### -Name
Nama Grup Reservasi Kapasitas.

```yaml
Type: System.String
Parameter Sets: DefaultParameterSet
Aliases: CapacityReservationGroupName

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: DefaultParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceId
ID Sumber Daya untuk Grup Reservasi Kapasitas Anda.

```yaml
Type: System.String
Parameter Sets: ResourceIDParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tag
Tag sumber daya.

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### Microsoft.Azure.Commands.Compute.Automation.Models.PSCapacityReservationGroup

### System.Collections.Hashtable

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Automation.Models.PSCapacityReservationGroup

## NOTES

## RELATED LINKS
