---
external help file: ''
Module Name: Az.DesktopVirtualization
online version: https://docs.microsoft.com/powershell/module/az.desktopvirtualization/new-azwvdscalingplan
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DesktopVirtualization/help/New-AzWvdScalingPlan.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DesktopVirtualization/help/New-AzWvdScalingPlan.md
ms.openlocfilehash: f85c4e4ae0e797747261fd03b2a9c82523da2d03
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136185066"
---
# New-AzWvdScalingPlan

## SYNOPSIS
Membuat atau memperbarui rencana penskalaan.

## SYNTAX

```
New-AzWvdScalingPlan -Name <String> -ResourceGroupName <String> -Location <String> [-SubscriptionId <String>]
 [-Description <String>] [-ExclusionTag <String>] [-FriendlyName <String>]
 [-HostPoolReference <IScalingHostPoolReference[]>] [-HostPoolType <HostPoolType>]
 [-Schedule <IScalingSchedule[]>] [-Tag <Hashtable>] [-TimeZone <String>] [-DefaultProfile <PSObject>]
 [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Membuat atau memperbarui rencana penskalaan.

## EXAMPLES

### Contoh 1: Membuat Windows Skala Desktop Virtual
```powershell
PS C:\> New-AzWvdScalingPlan `
            -ResourceGroupName ResourceGroupName `
            -Name 'scalingPlan1' `
            -Location 'westcentralus' `
            -Description 'Description' `
            -FriendlyName 'Friendly Name' `
            -HostPoolType 'Pooled' `
            -TimeZone '(UTC-08:00) Pacific Time (US & Canada)' `
            -Schedule @(
                @{
                    'name'                           = 'Work Week';
                    'daysOfWeek'                     = @('Monday', 'Tuesday', 'Wednesday', 'Thursday', 'Friday');
                    'rampUpStartTime'                = '1900-01-01T06:00:00Z';
                    'rampUpLoadBalancingAlgorithm'   = 'BreadthFirst';
                    'rampUpMinimumHostsPct'          = 20;
                    'rampUpCapacityThresholdPct'     = 20;
                    'peakStartTime'                  = '1900-01-01T08:00:00Z';
                    'peakLoadBalancingAlgorithm'     = 'DepthFirst';
                    'RampDownStartTime'              = '1900-01-01T18:00:00Z';
                    'rampDownLoadBalancingAlgorithm' = 'BreadthFirst';
                    'rampDownMinimumHostsPct'        = 20;
                    'rampDownCapacityThresholdPct'   = 20;
                    'rampDownForceLogoffUser'        = $true;
                    'rampDownWaitTimeMinute'         = 30;
                    'rampDownNotificationMessage'    = 'Log out now, please.';
                    'rampDownStopHostsWhen'          = 'ZeroSessions';
                    'offPeakStartTime'               = '1900-01-01T20:00:00Z';
                    'offPeakLoadBalancingAlgorithm'  = 'DepthFirst';
                }
            ) `
            -HostPoolReference @(
                @{
                    'hostPoolArmPath' = '/subscriptions/SubscriptionId/resourceGroups/ResourceGroupName/providers/Microsoft.DesktopVirtualization/hostPools/HostPoolName';
                    'scalingPlanEnabled' = $false;
                }
            )

Location      Name         Type
--------      ----         ----
westcentralus scalingPlan1 Microsoft.DesktopVirtualization/scalingplans 
```

Perintah ini membuat rencana Windows Skala Desktop Virtual baru dalam Grup Sumber Daya.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases: AzureRMContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Deskripsi
Deskripsi rencana skala.

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

### -ExclusionTag
Tag pengecualian untuk paket penskalaan.

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

### -FriendlyName
Nama rencana skala yang ramah pengguna.

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

### -HostPoolReference
Daftar definisi ScalingHostPoolReference.
Untuk membuat, lihat bagian CATATAN untuk properti HOSTPOOLREFERENCE dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DesktopVirtualization.Models.Api20210201Preview.IScalingHostPoolReference[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HostPoolType
Tipe HostPool untuk desktop.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DesktopVirtualization.Support.HostPoolType
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Lokasi
Lokasi geo-location di mana sumber daya berada

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama rencana skala.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ScalingPlanName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.
Namanya peka huruf besar/huruf.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Schedule
Daftar definisi ScalingSchedule.
Untuk membuat, lihat bagian CATATAN untuk properti JADWAL dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DesktopVirtualization.Models.Api20210201Preview.IScalingSchedule[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
ID langganan target.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
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
Accept pipeline input: False
Accept wildcard characters: False
```

### -Zona Waktu
Zona waktu rencana skala.

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

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DesktopVirtualization.Models.Api20210201Preview.IScalingPlan

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


HOSTPOOLREFERENCE <IScalingHostPoolReference[]>: Daftar definisi ScalingHostPoolReference.
  - `[HostPoolArmPath <String>]`: Jalur arm dari hostpool yang dirujuk.
  - `[ScalingPlanEnabled <Boolean?>]`: Adalah rencana skala yang diaktifkan untuk hostpool ini.

SCHEDULE <IScalingSchedule[]>: Daftar definisi ScalingSchedule.
  - `[DaysOfWeek <String[]>]`: Kumpulan hari dalam seminggu saat jadwal ini aktif.
  - `[Name <String>]`: Nama jadwal penskalaan.
  - `[OffPeakLoadBalancingAlgorithm <SessionHostLoadBalancingAlgorithm?>]`: Memuat menyeimbangkan algoritma untuk periode di luar puncak.
  - `[OffPeakStartTime <DateTime?>]`: Waktu mulai di luar periode sibuk.
  - `[PeakLoadBalancingAlgorithm <SessionHostLoadBalancingAlgorithm?>]`: Memuat algoritma keseimbangan untuk periode puncak.
  - `[PeakStartTime <DateTime?>]`: Waktu mulai untuk periode puncak.
  - `[RampDownCapacityThresholdPct <Int32?>]`: Ambang batas kapasitas untuk periode peningkatan.
  - `[RampDownForceLogoffUser <Boolean?>]`: Sebaiknya pengguna keluar secara paksa dari host.
  - `[RampDownLoadBalancingAlgorithm <SessionHostLoadBalancingAlgorithm?>]`: Memuat menyeimbangkan algoritma untuk periode waktu turun.
  - `[RampDownMinimumHostsPct <Int32?>]`: Persentase host minimum untuk periode penurunan tingkat.
  - `[RampDownNotificationMessage <String>]`: Pesan pemberitahuan untuk pengguna selama periode penurunan.
  - `[RampDownStartTime <DateTime?>]`: Waktu mulai untuk periode penurunan jalan.
  - `[RampDownStopHostsWhen <StopHostsWhen?>]`: Menentukan kapan untuk menghentikan host selama periode penurunan sementara.
  - `[RampDownWaitTimeMinute <Int32?>]`: Jumlah menit untuk menunggu untuk menghentikan host selama periode penurunan sementara.
  - `[RampUpCapacityThresholdPct <Int32?>]`: Ambang batas kapasitas untuk periode peningkatan.
  - `[RampUpLoadBalancingAlgorithm <SessionHostLoadBalancingAlgorithm?>]`: Memuat menyeimbangkan algoritma untuk periode waktu yang lama.
  - `[RampUpMinimumHostsPct <Int32?>]`: Persentase host minimum untuk periode meningkatkan tingkat.
  - `[RampUpStartTime <DateTime?>]`: Waktu mulai untuk periode meningkatkan jalan.

## RELATED LINKS

