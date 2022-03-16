---
external help file: ''
Module Name: Az.DesktopVirtualization
online version: https://docs.microsoft.com/powershell/module/az.desktopvirtualization/new-azwvdscalingplan
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DesktopVirtualization/help/New-AzWvdScalingPlan.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/DesktopVirtualization/help/New-AzWvdScalingPlan.md
ms.openlocfilehash: 7a56ca6c941398770c7767a8b420648af8f34668
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140200550"
---
# New-AzWvdScalingPlan

## SYNOPSIS
Membuat atau memperbarui rencana penskalaan.

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

### -Kind
Metadata digunakan oleh portal/tooling/etc untuk menyajikan pengalaman UX yang berbeda untuk sumber daya dengan tipe yang sama; mis. ApiApps merupakan jenis jenis Microsoft.Web/sites.
Jika didukung, penyedia sumber daya harus memvalidasi dan mempertahankan nilai ini.

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
Lokasi geo-location di mana sumber daya berada

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
Menunjukkan apakah sumber daya ini dikelola oleh sumber daya Azure lain.
Jika ada, penyebaran mode lengkap tidak akan menghapus sumber daya jika sumber daya dihapus dari templat karena dikelola oleh sumber daya lain.

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

### -PlanName
Pengguna menentukan nama Artifak Pihak Ke-3 yang sedang di pengadaan.

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
Artifak Pihak Ke-3 yang sedang di pengadaan.
Misalnya
NewRelic.
Peta produk ke OfferID yang ditentukan untuk artifak pada saat onboarding Pasar Data.

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
Penerbit menyediakan kode promosi seperti yang disediakan di Pasar Data untuk produk/artifak yang dikatakan.

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
Penerbit Artifak Pihak Ketiga yang sedang dibeli.
Misalnya
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
Versi produk/artifak yang diinginkan.

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
Jika SKU mendukung skala keluar/masuk maka bilangan bulat kapasitas akan disertakan.
Jika skala/in tidak dimungkinkan untuk sumber daya, hal ini mungkin dihilangkan.

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
Jika layanan memiliki beberapa generasi perangkat keras, untuk SKU yang sama, fitur tersebut dapat diambil di sini.

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
Misalnya - P3.
Kode ini biasanya adalah kode huruf+angka

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

### -SkuSize
Ukuran SKU.
Jika bidang nama merupakan kombinasi tingkatan dan beberapa nilai lain, ini akan menjadi kode mandiri.

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
Bidang ini harus diterapkan oleh Penyedia Sumber Daya jika layanan memiliki lebih dari satu tingkatan, tetapi tidak diperlukan pada PUT.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.DesktopVirtualization.Models.Api20210712.IScalingPlan

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


HOSTPOOLREFERENCE <IScalingHostPoolReference[]>: Daftar definisi ScalingHostPoolReference.
  - `[HostPoolArmPath <String>]`: Jalur arm dari hostpool yang dirujuk.
  - `[ScalingPlanEnabled <Boolean?>]`: Adalah rencana skala yang diaktifkan untuk hostpool ini.

JADWAL <IScalingSchedule[]>: Daftar definisi ScalingSchedule.
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

