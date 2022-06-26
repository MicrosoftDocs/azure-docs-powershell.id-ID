---
external help file: ''
Module Name: Az.Cdn
online version: https://docs.microsoft.com/powershell/module/az.cdn/new-azfrontdoorcdnorigingroup
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/help/New-AzFrontDoorCdnOriginGroup.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/help/New-AzFrontDoorCdnOriginGroup.md
ms.openlocfilehash: ff8eef678c5568e3ba7a3e152114eb86e2b4e898
ms.sourcegitcommit: 5df8b100721844736630242c724da453a2168434
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/26/2022
ms.locfileid: "146619148"
---
# New-AzFrontDoorCdnOriginGroup

## SYNOPSIS
Membuat grup asal baru dalam profil yang ditentukan.

## SYNTAX

```
New-AzFrontDoorCdnOriginGroup -OriginGroupName <String> -ProfileName <String> -ResourceGroupName <String>
 [-SubscriptionId <String>] [-HealthProbeSetting <IHealthProbeParameters>]
 [-LoadBalancingSetting <ILoadBalancingSettingsParameters>] [-SessionAffinityState <EnabledState>]
 [-TrafficRestorationTimeToHealedOrNewEndpointsInMinute <Int32>] [-DefaultProfile <PSObject>] [-AsJob]
 [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Membuat grup asal baru dalam profil yang ditentukan.

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

### -LoadBalancingSetting
Pengaturan penyeimbangan beban untuk kumpulan backend Untuk membangun, lihat bagian CATATAN untuk properti LOADBALANCINGSETTING dan buat tabel hash.

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
Nama grup asal yang unik dalam titik akhir.

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

### -ProfileName
Nama profil Premium Azure Front Door Standard atau Azure Front Door yang unik dalam grup sumber daya.

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

### -ResourceGroupName
Nama grup Sumber Daya dalam langganan Azure.

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
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: (Get-AzContext).Subscription.Id
Accept pipeline input: False
Accept wildcard characters: False
```

### -TrafficRestorationTimeToHealedOrNewEndpointsInMinute
Waktu dalam menit untuk mengalihkan lalu lintas ke titik akhir secara bertahap ketika titik akhir yang tidak sehat menjadi sehat atau titik akhir baru ditambahkan.
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

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.Api20210601.IAfdOriginGroup

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


HEALTHPROBESETTING `<IHealthProbeParameters>`: Pengaturan pemeriksaan kesehatan ke asal yang digunakan untuk menentukan kesehatan asal.
  - `[ProbeIntervalInSecond <Int32?>]`: Jumlah detik antara pemeriksaan kesehatan. Defaultnya adalah 240 detik.
  - `[ProbePath <String>]`: Jalur relatif terhadap asal yang digunakan untuk menentukan kesehatan asal.
  - `[ProbeProtocol <ProbeProtocol?>]`: Protokol yang digunakan untuk pemeriksaan kesehatan.
  - `[ProbeRequestType <HealthProbeRequestType?>]`: Jenis permintaan pemeriksaan kesehatan yang dibuat.

LOADBALANCINGSETTING `<ILoadBalancingSettingsParameters>`: Pengaturan penyeimbangan beban untuk kumpulan backend
  - `[AdditionalLatencyInMillisecond <Int32?>]`: Latensi tambahan dalam milidetik untuk pemeriksaan jatuh ke dalam wadah latensi terendah
  - `[SampleSize <Int32?>]`: Jumlah sampel yang perlu dipertimbangkan untuk keputusan penyeimbangan beban
  - `[SuccessfulSamplesRequired <Int32?>]`: Jumlah sampel dalam periode sampel yang harus berhasil

## RELATED LINKS

