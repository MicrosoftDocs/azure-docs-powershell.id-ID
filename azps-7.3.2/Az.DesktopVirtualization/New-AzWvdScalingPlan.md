---
external help file: ''
Module Name: Az.DesktopVirtualization
online version: https://docs.microsoft.com/powershell/module/az.desktopvirtualization/new-azwvdscalingplan
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DesktopVirtualization/help/New-AzWvdScalingPlan.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DesktopVirtualization/help/New-AzWvdScalingPlan.md
ms.openlocfilehash: cada9a36e50422dd2f4357d885b5e749148891d1
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143337491"
---
# New-AzWvdScalingPlan

## SYNOPSIS
Membuat atau memperbarui paket penskalakan.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.desktopvirtualization/new-azwvdscalingplan) untuk informasi terbaru.

## SYNTAX

```
New-AzWvdScalingPlan -Name <String> -ResourceGroupName <String> [-SubscriptionId <String>]
 [-Description <String>] [-ExclusionTag <String>] [-FriendlyName <String>]
 [-HostPoolReference <IScalingHostPoolReference[]>] [-HostPoolType <HostPoolType>]
 [-IdentityType <ResourceIdentityType>] [-Kind <String>] [-Location <String>] [-ManagedBy <String>]
 [-PlanName <String>] [-PlanProduct <String>] [-PlanPromotionCode <String>] [-PlanPublisher <String>]
 [-PlanVersion <String>] [-Schedule <IScalingSchedule[]>] [-SkuCapacity <Int32>] [-SkuFamily <String>]
 [-SkuName <String>] [-SkuSize <String>] [-SkuTier <SkuTier>] [-Tag <Hashtable>] [-TimeZone <String>]
 [-DefaultProfile <PSObject>] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Membuat atau memperbarui paket penskalakan.

## EXAMPLES

### Contoh 1: Membuat Windows Paket Penskalhan Desktop Virtual
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

Perintah ini membuat Windows Rencana Penskalhan Desktop Virtual baru dalam Grup Sumber Daya.

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
Nama paket penskalaan yang mudah dikenali.

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
Untuk membangun, lihat bagian CATATAN untuk properti HOSTPOOLREFERENCE dan membuat tabel hash.

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

### -IdentityType
Tipe identitas.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DesktopVirtualization.Support.ResourceIdentityType
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Jenis
Metadata yang digunakan oleh portal/tooling/etc untuk menyajikan pengalaman UX yang berbeda untuk sumber daya dengan tipe yang sama; misalnya ApiApps adalah jenis tipe Microsoft.Web/sites.
Jika didukung, penyedia sumber daya harus memvalidasi dan tetap memiliki nilai ini.

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

### -Lokasi
Lokasi geografis tempat sumber daya berada

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

### -ManagedBy
ID sumber daya yang sepenuhnya memenuhi syarat dari sumber daya yang mengelola sumber daya ini.
Menunjukkan apakah sumber daya ini dikelola oleh sumber daya Azure lainnya.
Jika ada, penyebaran mode lengkap tidak akan menghapus sumber daya jika dihapus dari templat karena dikelola oleh sumber daya lain.

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

### -Nama
Nama paket penskalaan.

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

### -PlanName
Pengguna mendefinisikan nama Artefak Pihak ke-3 yang sedang diakui.

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

### -PlanProduct
Artefak Partai ke-3 yang sedang dijadikan pengadaan.
Misalnya.
NewRelic.
Peta produk untuk OfferID yang ditentukan untuk artefak pada saat onboarding Data Market.

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

### -PlanPromotionCode
Penerbit menyediakan kode promosi sebagaimana ditetapkan di Pasar Data untuk produk/artefak tersebut.

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

### -PlanPublisher
Penerbit Artefak Pihak ke-3 yang sedang dibeli.
Misalnya.
NewRelic

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

### -PlanVersion
Versi produk/artefak yang diinginkan.

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

### -ResourceGroupName
Nama grup sumber daya.
Nama ini tidak peka huruf besar kecil.

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

### -Jadwal
Daftar definisi ScalingSchedule.
Untuk membangun, lihat bagian CATATAN untuk properti SCHEDULE dan membuat tabel hash.

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

### -SkuCapacity
Jika SKU mendukung penskalaan keluar/masuk maka bilangan bulat kapasitas harus disertakan.
Jika skala keluar/masuk tidak dimungkinkan untuk sumber daya ini mungkin dihilangkan.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SkuFamily
Jika layanan memiliki generasi perangkat keras yang berbeda, untuk SKU yang sama, maka yang dapat ditangkap di sini.

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

### -SkuName
Nama SKU.
Bekas - P3.
Biasanya berupa kode huruf+angka

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

### -Skusize
Ukuran SKU.
Ketika bidang nama adalah kombinasi tingkat dan beberapa nilai lainnya, ini akan menjadi kode mandiri.

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

### -SkuTier
Bidang ini diperlukan untuk diterapkan oleh Penyedia Sumber Daya jika layanan memiliki lebih dari satu tingkat, tetapi tidak diperlukan pada PUT.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.DesktopVirtualization.Support.SkuTier
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

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DesktopVirtualization.Models.Api20210712.IScalingPlan

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


HOSTPOOLREFERENCE <IScalingHostPoolReference[]>: Daftar definisi ScalingHostPoolReference.
  - `[HostPoolArmPath <String>]`: Jalur lengan hostpool yang dirujuk.
  - `[ScalingPlanEnabled <Boolean?>]`: Apakah paket penskalaan diaktifkan untuk hostpool ini.

JADWAL <IScalingSchedule[]>: Daftar definisi ScalingSchedule.
  - `[DaysOfWeek <String[]>]`: Kumpulan hari dalam seminggu di mana jadwal ini aktif.
  - `[Name <String>]`: Nama jadwal penskalaan.
  - `[OffPeakLoadBalancingAlgorithm <SessionHostLoadBalancingAlgorithm?>]`: Algoritma keseimbangan beban untuk periode off-peak.
  - `[OffPeakStartTime <DateTime?>]`: Waktu mulai untuk periode off-peak.
  - `[PeakLoadBalancingAlgorithm <SessionHostLoadBalancingAlgorithm?>]`: Algoritma penyeimbangan beban untuk periode puncak.
  - `[PeakStartTime <DateTime?>]`: Waktu mulai untuk periode puncak.
  - `[RampDownCapacityThresholdPct <Int32?>]`: Ambang batas kapasitas untuk periode ramp down.
  - `[RampDownForceLogoffUser <Boolean?>]`: Jika pengguna harus keluar secara paksa dari host.
  - `[RampDownLoadBalancingAlgorithm <SessionHostLoadBalancingAlgorithm?>]`: Algoritma penyeimbangan beban untuk periode ramp down.
  - `[RampDownMinimumHostsPct <Int32?>]`: Persentase host minimum untuk periode ramp down.
  - `[RampDownNotificationMessage <String>]`: Pesan pemberitahuan untuk pengguna selama periode ramp down.
  - `[RampDownStartTime <DateTime?>]`: Waktu mulai untuk periode ramp down.
  - `[RampDownStopHostsWhen <StopHostsWhen?>]`: Menentukan kapan menghentikan host selama periode ramp down.
  - `[RampDownWaitTimeMinute <Int32?>]`: Jumlah menit untuk menunggu untuk menghentikan host selama periode ramp down.
  - `[RampUpCapacityThresholdPct <Int32?>]`: Ambang batas kapasitas untuk periode peningkatan.
  - `[RampUpLoadBalancingAlgorithm <SessionHostLoadBalancingAlgorithm?>]`: Algoritma load balancing untuk periode ramp up.
  - `[RampUpMinimumHostsPct <Int32?>]`: Persentase host minimum untuk periode naik.
  - `[RampUpStartTime <DateTime?>]`: Waktu mulai untuk periode ramp up.

## RELATED LINKS

