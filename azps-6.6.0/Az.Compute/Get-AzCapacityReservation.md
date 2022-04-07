---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Compute.dll-Help.xml
Module Name: Az.Compute
online version: https://docs.microsoft.com/powershell/module/az.compute/get-azcapacityreservation
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Get-AzCapacityReservation.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Compute/Compute/help/Get-AzCapacityReservation.md
ms.openlocfilehash: 54bfc82db0a54738915a4092ac137f31fdf25c70
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140336093"
---
# Get-AzCapacityReservation

## SYNOPSIS
Mendapatkan properti sumber daya Reservasi Kapasitas dari Grup Reservasi Kapasitas

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.compute/get-azcapacityreservation) untuk informasi terkini.

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
PS C:\> Get-AzCapacityReservation -ResourceGroupName $rgname -ReservationGroupName "CRGroup1"
```

Ini akan mengambil semua sumber daya Reservasi Kapasitas dari Grup Reservasi Kapasitas bernama "CRGroup1".

### Contoh 2
```powershell
PS C:\> Get-AzCapacityReservation -ResourceGroupName $rgname -ReservationGroupName "CRGroup1" -Name "resource1" -InstanceView
```

Ini akan mengambil sumber daya Reservasi Kapasitas yang dinamai "resource1" dengan informasi tampilan contoh dari Grup Reservasi Kapasitas bernama "CRGroup1".

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
Dapatkan Tampilan Contoh Reservasi Kapasitas.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.Management.Automation.SwitchParameter

## OUTPUTS

### Microsoft.Azure.Commands.Compute.Automation.Models.PSCapacityReservation

## CATATAN

## RELATED LINKS
