---
external help file: ''
Module Name: Az.Cdn
online version: https://docs.microsoft.com/powershell/module/az.cdn/new-azcdnorigingroup
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/help/New-AzCdnOriginGroup.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Cdn/help/New-AzCdnOriginGroup.md
ms.openlocfilehash: 7b53ddbb3a288cde4f754ec56cfa73279f7d7d66
ms.sourcegitcommit: 5df8b100721844736630242c724da453a2168434
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/26/2022
ms.locfileid: "146630506"
---
# New-AzCdnOriginGroup

## SYNOPSIS
Membuat grup asal baru dalam titik akhir yang ditentukan.

## SYNTAX

```
New-AzCdnOriginGroup -EndpointName <String> -Name <String> -ProfileName <String> -ResourceGroupName <String>
 [-SubscriptionId <String>] [-HealthProbeSetting <IHealthProbeParameters>] [-Origin <IResourceReference[]>]
 [-ResponseBasedOriginErrorDetectionSetting <IResponseBasedOriginErrorDetectionParameters>]
 [-TrafficRestorationTimeToHealedOrNewEndpointsInMinute <Int32>] [-DefaultProfile <PSObject>] [-AsJob]
 [-NoWait] [-Confirm] [-WhatIf] [<CommonParameters>]
```

## DESCRIPTION
Membuat grup asal baru dalam titik akhir yang ditentukan.

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

### -EndpointName
Nama titik akhir di bawah profil yang unik secara global.

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

### -Name
Nama grup asal yang unik dalam titik akhir.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: OriginGroupName

Required: True
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

### -Origin
Sumber konten yang dikirimkan melalui CDN dalam grup asal tertentu.
Untuk membuat, lihat bagian CATATAN untuk properti ORIGIN dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.Api20210601.IResourceReference[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ProfileName
Nama profil CDN yang unik dalam grup sumber daya.

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

### -ResponseBasedOriginErrorDetectionSetting
Objek JSON yang berisi properti untuk menentukan kesehatan asal menggunakan permintaan/respons nyata.
Properti ini saat ini tidak didukung.
Untuk membuat, lihat bagian CATATAN untuk properti RESPONSEBASEDORIGINERRORDETECTIONSETTING dan buat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.Api20210601.IResponseBasedOriginErrorDetectionParameters
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

### Microsoft.Azure.PowerShell.Cmdlets.Cdn.Models.Api20210601.IOriginGroup

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


HEALTHPROBESETTING `<IHealthProbeParameters>`: Pengaturan pemeriksaan kesehatan ke asal yang digunakan untuk menentukan kesehatan asal.
  - `[ProbeIntervalInSecond <Int32?>]`: Jumlah detik antara pemeriksaan kesehatan. Defaultnya adalah 240 detik.
  - `[ProbePath <String>]`: Jalur relatif terhadap asal yang digunakan untuk menentukan kesehatan asal.
  - `[ProbeProtocol <ProbeProtocol?>]`: Protokol yang digunakan untuk pemeriksaan kesehatan.
  - `[ProbeRequestType <HealthProbeRequestType?>]`: Jenis permintaan pemeriksaan kesehatan yang dibuat.

ORIGIN <IResourceReference[]>: Sumber konten yang dikirimkan melalui CDN dalam grup asal tertentu.
  - `[Id <String>]`: ID Sumber Daya.

RESPONSEBASEDORIGINERRORDETECTIONSETTING `<IResponseBasedOriginErrorDetectionParameters>`: Objek JSON yang berisi properti untuk menentukan kesehatan asal menggunakan permintaan/respons nyata. Properti ini saat ini tidak didukung.
  - `[HttpErrorRange <IHttpErrorRangeParameters[]>]`: Daftar rentang kode status Http yang dianggap sebagai kesalahan server untuk asal dan ditandai sebagai tidak sehat.
    - `[Begin <Int32?>]`: Awal inklusif dari rentang kode status http.
    - `[End <Int32?>]`: Akhir inklusif dari rentang kode status http.
  - `[ResponseBasedDetectedErrorType <ResponseBasedDetectedErrorTypes?>]`: Jenis kesalahan respons untuk permintaan pengguna nyata yang asalnya akan dianggap tidak sehat
  - `[ResponseBasedFailoverThresholdPercentage <Int32?>]`: Persentase permintaan yang gagal dalam sampel di mana failover harus dipicu.

## RELATED LINKS

