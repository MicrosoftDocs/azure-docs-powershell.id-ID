---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
online version: https://docs.microsoft.com/powershell/module/az.compute/get-azcapacityreservationgroup
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Get-AzCapacityReservationGroup.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Get-AzCapacityReservationGroup.md
ms.openlocfilehash: 4a567196691a3fd7330610bd47fffef2b3349435
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136538813"
---
# Get-AzCapacityReservationGroup

## SYNOPSIS
Mendapatkan properti Grup Reservasi Kapasitas

## SYNTAX

### DefaultParameterSet (Default)
```
Get-AzCapacityReservationGroup [-ResourceGroupName <String>] [-Name <String>] [-InstanceView]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ResourceIDParameterSet
```
Get-AzCapacityReservationGroup -ResourceId <String> [-InstanceView] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzCapacityReservationGroup** mendapatkan properti sumber daya Reservasi Kapasitas dari Grup Reservasi Kapasitas

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Get-AzCapacityReservationGroup -ResourceGroupName $rgname -Name "CRGroup1" -InstanceView
```

Langkah ini akan mengambil Grup Reservasi Kapasitas bernama "CRGroup1" dengan informasi tampilan instansnya.

### Contoh 2
```powershell
PS C:\> Get-AzCapacityReservationGroup -ResourceGroupName $rgname
```

Ini akan mengambil semua informasi Grup Reservasi Kapasitas dari grup sumber daya.

## PARAMETERS

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

### -InstanceView
Dapatkan Tampilan Contoh Grup Reservasi Kapasitas.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nama
Menentukan nama grup reservasi kapasitas.

```yaml
Type: System.String
Parameter Sets: DefaultParameterSet
Aliases: CapacityReservationGroupName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -ResourceGroupName
Menentukan nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: DefaultParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -ResourceId
ID Sumber Daya untuk grup reservasi kapasitas.

```yaml
Type: System.String
Parameter Sets: ResourceIDParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.Management.Automation.SwitchParameter

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Automation.Models.PSCapacityReservationGroup

## CATATAN

## RELATED LINKS
