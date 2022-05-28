---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
online version: https://docs.microsoft.com/powershell/module/az.compute/get-azcapacityreservation
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Get-AzCapacityReservation.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Get-AzCapacityReservation.md
ms.openlocfilehash: bd29d5e517a66b291f80dc250ad93a6a7f43a608
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145529674"
---
# Get-AzCapacityReservation

## SYNOPSIS
Mendapatkan properti sumber daya Reservasi Kapasitas dari Grup Reservasi Kapasitas

## SYNTAX

```
Get-AzCapacityReservation -ResourceGroupName <String> -ReservationGroupName <String> [-Name <String>]
 [-InstanceView] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzCapacityReservation** mendapatkan properti sumber daya Reservasi Kapasitas dari Grup Reservasi Kapasitas

## EXAMPLES

### Contoh 1
```powershell
Get-AzCapacityReservation -ResourceGroupName $rgname -ReservationGroupName "CRGroup1"
```

Ini akan mengambil semua sumber daya Reservasi Kapasitas dari Grup Reservasi Kapasitas bernama "CRGroup1".

### Contoh 2
```powershell
Get-AzCapacityReservation -ResourceGroupName $rgname -ReservationGroupName "CRGroup1" -Name "resource1" -InstanceView
```

Ini akan mengambil sumber daya Reservasi Kapasitas bernama "resource1" dengan informasi tampilan instansnya dari Grup Reservasi Kapasitas bernama "CRGroup1".

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
Dapatkan Tampilan Instans Reservasi Kapasitas.

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

### -Name
Menentukan nama sumber daya reservasi kapasitas.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: CapacityReservationName

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -ReservationGroupName
Nama Grup Reservasi Kapasitas tempat sumber daya reservasi kapasitas berada.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: CapacityReservationGroupName

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### -ResourceGroupName
Menentukan nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

### System.Management.Automation.SwitchParameter

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Automation.Models.PSCapacityReservation

## NOTES

## RELATED LINKS
