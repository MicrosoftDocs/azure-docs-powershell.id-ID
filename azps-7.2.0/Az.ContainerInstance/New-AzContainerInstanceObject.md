---
external help file: ''
Module Name: Az.ContainerInstance
online version: https://docs.microsoft.com/powershell/module/az.ContainerInstance/new-AzContainerInstanceObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/New-AzContainerInstanceObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/New-AzContainerInstanceObject.md
ms.openlocfilehash: 441ee7551552590c0417397152df94e41b2fc576
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138278555"
---
# New-AzContainerInstanceObject

## SYNOPSIS
Membuat objek dalam memori untuk Wadah

## SYNTAX

```
New-AzContainerInstanceObject -Image <String> -Name <String> [-Command <String[]>]
 [-EnvironmentVariable <IEnvironmentVariable[]>] [-LimitCpu <Double>] [-LimitMemoryInGb <Double>]
 [-LimitsGpuCount <Int32>] [-LimitsGpuSku <String>] [-LivenessProbeExecCommand <String[]>]
 [-LivenessProbeFailureThreshold <Int32>] [-LivenessProbeHttpGetHttpHeader <IHttpHeader[]>]
 [-LivenessProbeHttpGetPath <String>] [-LivenessProbeHttpGetPort <Int32>]
 [-LivenessProbeHttpGetScheme <String>] [-LivenessProbeInitialDelaySecond <Int32>]
 [-LivenessProbePeriodSecond <Int32>] [-LivenessProbeSuccessThreshold <Int32>]
 [-LivenessProbeTimeoutSecond <Int32>] [-Port <IContainerPort[]>] [-ReadinessProbeExecCommand <String[]>]
 [-ReadinessProbeFailureThreshold <Int32>] [-ReadinessProbeHttpGetHttpHeader <IHttpHeader[]>]
 [-ReadinessProbeHttpGetPath <String>] [-ReadinessProbeHttpGetPort <Int32>]
 [-ReadinessProbeHttpGetScheme <String>] [-ReadinessProbeInitialDelaySecond <Int32>]
 [-ReadinessProbePeriodSecond <Int32>] [-ReadinessProbeSuccessThreshold <Int32>]
 [-ReadinessProbeTimeoutSecond <Int32>] [-RequestCpu <Double>] [-RequestMemoryInGb <Double>]
 [-RequestsGpuCount <Int32>] [-RequestsGpuSku <String>] [-VolumeMount <IVolumeMount[]>] [<CommonParameters>]
```

## DESCRIPTION
Membuat objek dalam memori untuk Wadah

## EXAMPLES

### Contoh 1: Membuat contoh wadah menggunakan alphine gambar dengan cpu permintaan 1.0 dan memori permintaan 1.5Gb
```powershell
PS C:\> New-AzContainerInstanceObject -Name "test-container" -Image alpine -RequestCpu 1 -RequestMemoryInGb 1.5

Name
----
test-container
```

Membuat contoh wadah menggunakan alphine gambar dengan cpu permintaan 1.0 dan memori permintaan 1,5Gb

### Contoh 2: Buat contoh wadah menggunakan alphine gambar dengan batas cpu 2,0 dan batasi memori 2,5Gb
```powershell
PS C:\> New-AzContainerInstanceObject -Image alpine -Name "test-container" -LimitCpu 2 -LimitMemoryInGb 2.5

Name
----
test-container
```

Membuat contoh wadah menggunakan alphine gambar dengan batas cpu 2,0 dan membatasi memori 2,5Gb

## PARAMETERS

### -Command
Perintah untuk dijalankan dalam wadah dalam formulir exec.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -EnvironmentVariable
Variabel lingkungan yang diatur dalam contoh wadah.
Untuk membuat, lihat bagian CATATAN untuk properti ENVIRONMENTVARIABLE dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ContainerInstance.Models.Api20210901.IEnvironmentVariable[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Image
Nama gambar yang digunakan untuk membuat contoh wadah.

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

### -LimitCpu
Batas CPU instans wadah ini.

```yaml
Type: System.Double
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Limit Limit LimitInGb
Batas memori dalam GB contoh wadah ini.

```yaml
Type: System.Double
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LimitsGpuCount
Jumlah sumber daya GPU.

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

### -LimitsGpuSku
SKU sumber daya GPU.

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

### -LivenessProbeExecCommand
Perintah untuk dijalankan dalam wadah.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LivenessProbeFailureThreshold
Ambang kegagalan.

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

### -LivenessProbehttpGetHttpHeader
Header HTTP untuk kebersamaan dan kebersamaan.
Untuk membuat, lihat bagian CATATAN untuk properti LIVENESSPROBEHTTPGETHTTPHEADER dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ContainerInstance.Models.Api20210901.IHttpHeader[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -LivenessProbehttpGetPath
Jalur keseringaan.

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

### -LivenessProbehttpGetPort
Nomor port ke laut.

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

### -LivenessProbehttpGetScheme
Skema.

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

### -LivenessProbeInitialDelaySecond
Detik penundaan awal.

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

### -LivenessProbePeriodSecond
Detik periode.

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

### -LivenessProbeSuccessThreshold
Ambang keberhasilan.

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

### -LivenessProbeTimeoutSecond
Waktu habis detik.

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

### -Nama
Nama contoh wadah yang disediakan pengguna.

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

### -Port
Port yang diekspos pada wadah wadah.
Untuk membuat, lihat bagian CATATAN untuk properti PORT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ContainerInstance.Models.Api20210901.IContainerPort[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReadinessProbeExecCommand
Perintah untuk dijalankan dalam wadah.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReadinessProbeFailureThreshold
Ambang kegagalan.

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

### -ReadinessProbehttpGetHttpHeader
Header HTTP untuk permintaan kesiapan.
Untuk membuat, lihat bagian CATATAN untuk properti READINESSPROBEHTTPGETHTTPHEADER dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ContainerInstance.Models.Api20210901.IHttpHeader[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ReadinessProbehttpGetPath
Jalur keseringaan.

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

### -ReadinessProbehttpGetPort
Nomor port ke laut.

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

### -ReadinessProbehttpGetScheme
Skema.

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

### -ReadinessProbeInitialDelaySecond
Detik penundaan awal.

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

### -ReadinessProbePeriodSecond
Detik periode.

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

### -ReadinessProbeSuccessThreshold
Ambang keberhasilan.

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

### -ReadinessProbeTimeoutSecond
Waktu habis detik.

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

### -RequestCpu
Permintaan CPU instans wadah ini.

```yaml
Type: System.Double
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Request Request RequestInGb
Permintaan memori dalam GB contoh wadah ini.

```yaml
Type: System.Double
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RequestsGpuCount
Jumlah sumber daya GPU.

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

### -RequestsgpuSku
SKU sumber daya GPU.

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

### -VolumeMount
Volume yang terpasang tersedia pada contoh wadah.
Untuk membuat, lihat bagian CATATAN untuk properti VOLUMEMOUNT dan membuat tabel hash.

```yaml
Type: Microsoft.Azure.PowerShell.Cmdlets.ContainerInstance.Models.Api20210901.IVolumeMount[]
Parameter Sets: (All)
Aliases:

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

### Microsoft.Azure.PowerShell.Cmdlets.ContainerInstance.Models.Api20210901.Container

## CATATAN

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


ENVIRONMENTVARIABLE <IEnvironmentVariable[]>: Variabel lingkungan yang diatur dalam wadah.
  - `Name <String>`: Nama variabel lingkungan.
  - `[SecureValue <String>]`: Nilai variabel lingkungan yang aman.
  - `[Value <String>]`: Nilai variabel lingkungan.

LIVENESSPROBEHTTPGETHTTPHEADER <IHttpHeader[]>: Header HTTP untuk liveness.
  - `[Name <String>]`: Nama header.
  - `[Value <String>]`: Nilai header.

PORT <IContainerPort[]>: Port yang diekspos pada contoh wadah.
  - `Port <Int32>`: Nomor port yang diekspos dalam grup wadah.
  - `[Protocol <ContainerNetworkProtocol?>]`: Protokol yang terkait dengan port.

READINESSPROBEHTTPGETHTTPHEADER <IHttpHeader[]>: Header HTTP untuk kesiapan.
  - `[Name <String>]`: Nama header.
  - `[Value <String>]`: Nilai header.

VOLUMEMOUNT <IVolumeMount[]>: Volume terpasang yang tersedia pada wadah.
  - `MountPath <String>`: Jalur di dalam wadah tempat volume harus terpasang. Tidak boleh berisi titik dua (:).
  - `Name <String>`: Nama volume yang naik.
  - `[ReadOnly <Boolean?>]`: Bendera menunjukkan apakah volume naik merupakan baca-saja.

## RELATED LINKS

