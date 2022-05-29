---
external help file: Microsoft.Azure.PowerShell.Cmdlets.NetAppFiles.dll-Help.xml
Module Name: Az.NetAppFiles
online version: https://docs.microsoft.com/powershell/module/az.netappfiles/new-aznetappfilessnapshotpolicy
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/NetAppFiles/NetAppFiles/help/New-AzNetAppFilesSnapshotPolicy.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/NetAppFiles/NetAppFiles/help/New-AzNetAppFilesSnapshotPolicy.md
ms.openlocfilehash: e595d22ecf4ee36ebe6a97c70fa7c3e8b6507cc7
ms.sourcegitcommit: 321c644cf2161807a71e1af318fc5c5311d22e25
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/25/2022
ms.locfileid: "145803390"
---
# New-AzNetAppFilesSnapshotPolicy

## SYNOPSIS
Membuat kebijakan rekam jepret Azure NetApp Files (ANF) baru untuk akun ANF.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.netappfiles/new-aznetappfilessnapshotpolicy) untuk informasi terbaru.

## SYNTAX

### ByFieldsParameterSet (Default)
```
New-AzNetAppFilesSnapshotPolicy -ResourceGroupName <String> -Location <String> -AccountName <String>
 -Name <String> [-Enabled] -HourlySchedule <PSNetAppFilesHourlySchedule>
 -DailySchedule <PSNetAppFilesDailySchedule> -WeeklySchedule <PSNetAppFilesWeeklySchedule>
 -MonthlySchedule <PSNetAppFilesMonthlySchedule> [-Tag <Hashtable>] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### ByParentObjectParameterSet
```
New-AzNetAppFilesSnapshotPolicy -Name <String> [-Enabled] -HourlySchedule <PSNetAppFilesHourlySchedule>
 -DailySchedule <PSNetAppFilesDailySchedule> -WeeklySchedule <PSNetAppFilesWeeklySchedule>
 -MonthlySchedule <PSNetAppFilesMonthlySchedule> [-Tag <Hashtable>] -AccountObject <PSNetAppFilesAccount>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzNetAppFilesActiveDirectory** membuat kebijakan rekam jepret baru untuk akun ANF.

## EXAMPLES

### Contoh 1
```powershell
$hourlySchedule = @{        
        Minute = 2
        SnapshotsToKeep = 6
    }
    $dailySchedule = @{
        Hour = 1
        Minute = 2
        SnapshotsToKeep = 6
    }
    $weeklySchedule = @{
        Minute = 2    
        Hour = 1                
        Day = "Sunday,Monday"
        SnapshotsToKeep = 6
    }
    $monthlySchedule = @{
        Minute = 2    
        Hour = 1        
        DaysOfMonth = "2,11,21"
        SnapshotsToKeep = 6
    }
New-AzNetAppFilesSnapshotPolicy -ResourceGroupName "MyRG" -l "westus2" -AccountName "MyAccount" -Name "MySnapshotPolicy" -Enabled -HourlySchedule $hourlySchedule -DailySchedule $dailySchedule -WeeklySchedule $weeklySchedule -MonthlySchedule $monthlySchedule
```

Perintah ini membuat kebijakan rekam jepret ANF baru untuk akun ANF bernama "MyAccount".

## PARAMETERS

### -AccountName
Nama akun ANF

```yaml
Type: System.String
Parameter Sets: ByFieldsParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -AccountObject
Akun untuk objek Kebijakan Rekam Jepret baru

```yaml
Type: Microsoft.Azure.Commands.NetAppFiles.Models.PSNetAppFilesAccount
Parameter Sets: ByParentObjectParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -DailySchedule
Array hashtable yang mewakili Jadwal harian

```yaml
Type: Microsoft.Azure.Commands.NetAppFiles.Models.PSNetAppFilesDailySchedule
Parameter Sets: (All)
Aliases:

Required: True
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

### -Diaktifkan
Properti untuk memutuskan kebijakan diaktifkan atau tidak

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

### -HourlySchedule
Array hashtable yang mewakili Jadwal per jam

```yaml
Type: Microsoft.Azure.Commands.NetAppFiles.Models.PSNetAppFilesHourlySchedule
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lokasi
Lokasi sumber daya

```yaml
Type: System.String
Parameter Sets: ByFieldsParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MonthlySchedule
Array hashtable yang mewakili Jadwal montly

```yaml
Type: Microsoft.Azure.Commands.NetAppFiles.Models.PSNetAppFilesMonthlySchedule
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Nama kebijakan rekam jepret ANF

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: SnapshotPolicyName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Grup sumber daya akun ANF

```yaml
Type: System.String
Parameter Sets: ByFieldsParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tag
Array hashtable yang mewakili tag sumber daya

```yaml
Type: System.Collections.Hashtable
Parameter Sets: (All)
Aliases: Tags

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WeeklySchedule
Array hashtable yang mewakili Jadwal montly

```yaml
Type: Microsoft.Azure.Commands.NetAppFiles.Models.PSNetAppFilesWeeklySchedule
Parameter Sets: (All)
Aliases:

Required: True
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

### Microsoft.Azure.Commands.NetAppFiles.Models.PSNetAppFilesAccount

## OUTPUTS

### Microsoft.Azure.Commands.NetAppFiles.Models.PSNetAppFilesSnapshotPolicy

## NOTES

## RELATED LINKS
