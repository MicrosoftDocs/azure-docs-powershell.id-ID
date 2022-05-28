---
external help file: ''
Module Name: Az.Cdn
online version: https://docs.microsoft.com/powershell/module/az.cdn/update-azfrontdoorcdnorigingroup
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/help/Update-AzFrontDoorCdnOriginGroup.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/help/Update-AzFrontDoorCdnOriginGroup.md
ms.openlocfilehash: 318c7697701dca4ac106cacb8c5c005f4a8b34de
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145618179"
---
# Update-AzFrontDoorCdnOriginGroup

## SYNOPSIS
Memperbarui grup asal yang ada dalam profil.

## SYNTAX

### UpdateExpanded (Default)
```
Update-AzFrontDoorCdnOriginGroup -OriginGroupName <String> -ProfileName <String> -ResourceGroupName <String>
 [-SubscriptionId <String>] [-HealthProbeSetting <IHealthProbeParameters>]
 [-LoadBalancingSetting <ILoadBalancingSettingsParameters>] [-SessionAffinityState <EnabledState>]
 [-TrafficRestorationTimeToHealedOrNewEndpointsInMinute <Int32>] [-DefaultProfile <PSObject>] [-AsJob]
 [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

### UpdateViaIdentityExpanded
```
Update-AzFrontDoorCdnOriginGroup -InputObject <ICdnIdentity> [-HealthProbeSetting <IHealthProbeParameters>]
 [-LoadBalancingSetting <ILoadBalancingSettingsParameters>] [-SessionAffinityState <EnabledState>]
 [-TrafficRestorationTimeToHealedOrNewEndpointsInMinute <Int32>] [-DefaultProfile <PSObject>] [-AsJob]
 [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Memperbarui grup asal yang ada dalam profil.

## EXAMPLES

### Contoh 1: {{ Tambahkan judul di sini }}
```powershell
{{ Add code here }}
```

```output
{{ Add output here }}
```

{{ Tambahkan deskripsi di sini }}

### Contoh 2: {{ Tambahkan judul di sini }}
```powershell
{{ Add code here }}
```

```output
{{ Add output here }}
```

{{ Tambahkan deskripsi di sini }}

## PARAMETERS

### -AsJob
Jalankan perintah sebagai pekerjaan

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
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases: AzureRMContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -HealthProbeSetting
Pengaturan pemeriksaan kesehatan ke asal yang digunakan untuk menentukan kesehatan asal.
Untuk membuat, lihat bagian CATATAN untuk properti HEALTHPROBESETTING dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.Api20210601.IHealthProbeParameters
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Parameter Identitas Untuk membangun, lihat bagian CATATAN untuk properti INPUTOBJECT dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.ICdnIdentity
Parameter Sets: UpdateViaIdentityExpanded
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -LoadBalancingSetting
Pengaturan penyeimbangan beban untuk kumpulan backend Untuk membangun, lihat bagian CATATAN untuk PROPERTI LOADBALANCINGSETTING dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.Api20210601.ILoadBalancingSettingsParameters
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -NoWait
Jalankan perintah secara asinkron

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

### -OriginGroupName
Nama grup asal yang unik dalam profil.

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

### -ProfileName
Nama profil Premium Azure Front Door Standard atau Azure Front Door yang unik dalam grup sumber daya.

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

### -ResourceGroupName
Nama grup Sumber Daya dalam langganan Azure.

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

### -SessionAffinityState
Apakah akan mengizinkan afinitas sesi pada host ini.
Opsi yang valid adalah 'Diaktifkan' atau 'Dinonaktifkan'

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Support.EnabledState
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SubscriptionId
ID Langganan Azure.

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

### -TrafficRestorationTimeToHealedOrNewEndpointsInMinute
Waktu dalam menit untuk mengalihkan lalu lintas ke titik akhir secara bertahap ketika titik akhir yang tidak sehat sehat atau titik akhir baru ditambahkan.
Defaultnya adalah 10 menit.
Properti ini saat ini tidak didukung.

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

### Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.ICdnIdentity

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.Api20210601.IAfdOriginGroup

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


HEALTHPROBESETTING <IHealthProbeParameters>: Pengaturan pemeriksaan kesehatan ke asal yang digunakan untuk menentukan kesehatan asal.
  - `[ProbeIntervalInSecond <Int32?>]`: Jumlah detik antara pemeriksaan kesehatan. Defaultnya adalah 240 detik.
  - `[ProbePath <String>]`: Jalur relatif terhadap asal yang digunakan untuk menentukan kesehatan asal.
  - `[ProbeProtocol <ProbeProtocol?>]`: Protokol yang digunakan untuk pemeriksaan kesehatan.
  - `[ProbeRequestType <HealthProbeRequestType?>]`: Jenis permintaan pemeriksaan kesehatan yang dibuat.

INPUTOBJECT <ICdnIdentity>: Parameter Identitas
  - `[CustomDomainName <String>]`: Nama domain di bawah profil yang unik secara global.
  - `[EndpointName <String>]`: Nama titik akhir di bawah profil yang unik secara global.
  - `[Id <String>]`: Jalur identitas sumber daya
  - `[OriginGroupName <String>]`: Nama grup asal yang unik dalam titik akhir.
  - `[OriginName <String>]`: Nama asal yang unik dalam profil.
  - `[ProfileName <String>]`: Nama profil Azure Front Door Standard atau Azure Front Door Premium atau CDN yang unik dalam grup sumber daya.
  - `[ResourceGroupName <String>]`: Nama grup Sumber Daya dalam langganan Azure.
  - `[RouteName <String>]`: Nama aturan perutean.
  - `[RuleName <String>]`: Nama aturan pengiriman yang unik dalam titik akhir.
  - `[RuleSetName <String>]`: Nama seperangkat aturan di bawah profil yang unik secara global.
  - `[SecretName <String>]`: Nama Rahasia di bawah profil.
  - `[SecurityPolicyName <String>]`: Nama kebijakan keamanan di bawah profil.
  - `[SubscriptionId <String>]`: ID Langganan Azure.

LOADBALANCINGSETTING <ILoadBalancingSettingsParameters>: Pengaturan penyeimbangan beban untuk kumpulan backend
  - `[AdditionalLatencyInMillisecond <Int32?>]`: Latensi tambahan dalam milidetik untuk pemeriksaan jatuh ke dalam wadah latensi terendah
  - `[SampleSize <Int32?>]`: Jumlah sampel yang perlu dipertimbangkan untuk keputusan penyeimbangan beban
  - `[SuccessfulSamplesRequired <Int32?>]`: Jumlah sampel dalam periode sampel yang harus berhasil

## RELATED LINKS

