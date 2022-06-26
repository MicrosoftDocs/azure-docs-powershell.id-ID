---
external help file: ''
Module Name: Az.DesktopVirtualization
online version: https://docs.microsoft.com/powershell/module/az.desktopvirtualization/update-azwvdscalingplan
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DesktopVirtualization/help/Update-AzWvdScalingPlan.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DesktopVirtualization/help/Update-AzWvdScalingPlan.md
ms.openlocfilehash: c2af9c255dbb0083863d14028e9f6c110f96094c
ms.sourcegitcommit: 5df8b100721844736630242c724da453a2168434
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/26/2022
ms.locfileid: "146636716"
---
# Update-AzWvdScalingPlan

## SYNOPSIS
Memperbarui rencana penskalakan.

## SYNTAX

### UpdateExpanded (Default)
```
Update-AzWvdScalingPlan -Name <String> -ResourceGroupName <String> [-SubscriptionId <String>]
 [-Description <String>] [-ExclusionTag <String>] [-FriendlyName <String>]
 [-HostPoolReference <IScalingHostPoolReference[]>] [-HostPoolType <HostPoolType>]
 [-Schedule <IScalingSchedule[]>] [-Tag <Hashtable>] [-TimeZone <String>] [-DefaultProfile <PSObject>]
 [-Confirm] [-WhatIf] [<CommonParameters>]
```

### UpdateViaIdentityExpanded
```
Update-AzWvdScalingPlan -InputObject <IDesktopVirtualizationIdentity> [-Description <String>]
 [-ExclusionTag <String>] [-FriendlyName <String>] [-HostPoolReference <IScalingHostPoolReference[]>]
 [-HostPoolType <HostPoolType>] [-Schedule <IScalingSchedule[]>] [-Tag <Hashtable>] [-TimeZone <String>]
 [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Memperbarui rencana penskalakan.

## EXAMPLES

### Contoh 1: Memperbarui Windows Virtual Desktop Scaling Plan berdasarkan nama
```powershell
Update-AzWvdScalingPlan `
            -ResourceGroupName ResourceGroupName `
            -Name 'scalingPlan1' `
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
                    'hostPoolArmPath' = '/subscriptions/SubscriptionId/resourceGroups/ResourceGroupName/providers/Microsoft.DesktopVirtualization/hostPools/HostPoolName1';
                    'scalingPlanEnabled' = $false;
                },
                @{
                    'hostPoolArmPath' = '/subscriptions/SubscriptionId/resourceGroups/ResourceGroupName/providers/Microsoft.DesktopVirtualization/hostPools/HostPoolName2';
                    'scalingPlanEnabled' = $false;
                }

            )
```

```output
Location      Name         Type
--------      ----         ----
westcentralus scalingPlan1 Microsoft.DesktopVirtualization/scalingplans
```

Perintah ini memperbarui Windows Virtual Desktop Scaling Plan dalam Grup Sumber Daya.

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
Deskripsi rencana penskalaan.

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
Tag pengecualian untuk rencana penskalaan.

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
Nama paket penskalaan yang mudah digunakan.

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
Untuk membuat, lihat bagian CATATAN untuk properti HOSTPOOLREFERENCE dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DesktopVirtualization.Models.Api20210712.IScalingHostPoolReference[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HostPoolType
Jenis HostPool untuk desktop.

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

### -InputObject
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DesktopVirtualization.Models.IDesktopVirtualizationIdentity
Parameter Sets: UpdateViaIdentityExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Nama rencana penskalaan.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases: ScalingPlanName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.
Nama tidak peka huruf besar/kecil.

```yaml
Type: System.String
Parameter Sets: UpdateExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Jadwal
Daftar definisi ScalingSchedule.
Untuk membuat, lihat bagian CATATAN untuk properti SCHEDULE dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DesktopVirtualization.Models.Api20210712.IScalingSchedule[]
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
Parameter Sets: UpdateExpanded
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tag
tag yang akan diperbarui

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
Zona waktu rencana penskalaan.

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

### Microsoft.Azure.PowerShell.Cmdlets.DesktopVirtualization.Models.IDesktopVirtualizationIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DesktopVirtualization.Models.Api20210712.IScalingPlan

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


HOSTPOOLREFERENCE <IScalingHostPoolReference[]>: Daftar definisi ScalingHostPoolReference.
  - `[HostPoolArmPath <String>]`: Jalur arm hostpool yang dirujuk.
  - `[ScalingPlanEnabled <Boolean?>]`: Apakah rencana penskalaan diaktifkan untuk hostpool ini.

INPUTOBJECT `<IDesktopVirtualizationIdentity>`: Parameter Identitas
  - `[ApplicationGroupName <String>]`: Nama grup aplikasi
  - `[ApplicationName <String>]`: Nama aplikasi dalam grup aplikasi yang ditentukan
  - `[DesktopName <String>]`: Nama desktop dalam grup desktop yang ditentukan
  - `[HostPoolName <String>]`: Nama kumpulan host dalam grup sumber daya yang ditentukan
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[MsixPackageFullName <String>]`: Nama lengkap paket spesifik versi dari paket MSIX dalam hostpool yang ditentukan
  - `[ResourceGroupName <String>]`: Nama grup sumber daya. Nama tidak peka huruf besar/kecil.
  - `[ScalingPlanName <String>]`: Nama rencana penskalaan.
  - `[SessionHostName <String>]`: Nama host sesi dalam kumpulan host yang ditentukan
  - `[SubscriptionId <String>]`: ID langganan target.
  - `[UserSessionId <String>]`: Nama sesi pengguna dalam host sesi yang ditentukan
  - `[WorkspaceName <String>]`: Nama ruang kerja

SCHEDULE <IScalingSchedule[]>: Daftar definisi ScalingSchedule.
  - `[DaysOfWeek <String[]>]`: Set hari dalam seminggu di mana jadwal ini aktif.
  - `[Name <String>]`: Nama jadwal penskalaan.
  - `[OffPeakLoadBalancingAlgorithm <SessionHostLoadBalancingAlgorithm?>]`: Algoritma penyeimbangan beban untuk periode di luar puncak.
  - `[OffPeakStartTime <DateTime?>]`: Waktu mulai untuk periode di luar puncak.
  - `[PeakLoadBalancingAlgorithm <SessionHostLoadBalancingAlgorithm?>]`: Algoritma penyeimbangan beban untuk periode puncak.
  - `[PeakStartTime <DateTime?>]`: Waktu mulai untuk periode puncak.
  - `[RampDownCapacityThresholdPct <Int32?>]`: Ambang batas kapasitas untuk periode penurunan.
  - `[RampDownForceLogoffUser <Boolean?>]`: Haruskah pengguna dicatat secara paksa dari host.
  - `[RampDownLoadBalancingAlgorithm <SessionHostLoadBalancingAlgorithm?>]`: Algoritma penyeimbangan beban untuk periode penurunan.
  - `[RampDownMinimumHostsPct <Int32?>]`: Persentase host minimum untuk periode penurunan.
  - `[RampDownNotificationMessage <String>]`: Pesan pemberitahuan untuk pengguna selama periode penurunan.
  - `[RampDownStartTime <DateTime?>]`: Waktu mulai untuk periode penurunan.
  - `[RampDownStopHostsWhen <StopHostsWhen?>]`: Menentukan kapan harus menghentikan host selama periode penurunan.
  - `[RampDownWaitTimeMinute <Int32?>]`: Jumlah menit untuk menunggu menghentikan host selama periode penurunan.
  - `[RampUpCapacityThresholdPct <Int32?>]`: Ambang batas kapasitas untuk periode peningkatan.
  - `[RampUpLoadBalancingAlgorithm <SessionHostLoadBalancingAlgorithm?>]`: Algoritma penyeimbangan beban untuk periode peningkatan.
  - `[RampUpMinimumHostsPct <Int32?>]`: Persentase host minimum untuk periode peningkatan.
  - `[RampUpStartTime <DateTime?>]`: Waktu mulai untuk periode peningkatan.

## RELATED LINKS

