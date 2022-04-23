---
external help file: ''
Module Name: Az.ContainerInstance
online version: https://docs.microsoft.com/powershell/module/az.ContainerInstance/new-AzContainerInstanceObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/New-AzContainerInstanceObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/New-AzContainerInstanceObject.md
ms.openlocfilehash: 690691ff79f0ac71e8d8ad90b2a418cb5e7aa39e
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143186237"
---
# New-AzContainerInstanceObject

## SYNOPSIS
Membuat objek dalam memori untuk Kontainer

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.containerinstance/new-azcontainerinstanceobject) untuk informasi terbaru.

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
Membuat objek dalam memori untuk Kontainer

## EXAMPLES

### Contoh 1: Membuat instance container menggunakan alfin gambar dengan request cpu 1.0 dan request memory 1.5Gb
```powershell
New-AzContainerInstanceObject -Name "test-container" -Image alpine -RequestCpu 1 -RequestMemoryInGb 1.5
```

```output
Name
----
test-container
```

Membuat instance container menggunakan image alphine dengan request cpu 1.0 dan request memory 1.5Gb

### Contoh 2: Membuat instance container menggunakan alfin gambar dengan limit cpu 2.0 dan limit memory 2.5Gb
```powershell
New-AzContainerInstanceObject -Image alpine -Name "test-container" -LimitCpu 2 -LimitMemoryInGb 2.5
```

```output
Name
----
test-container
```

Membuat instance container menggunakan alphine image dengan limit cpu 2.0 dan limit memory 2.5Gb

### Contoh 3: Membuat grup wadah dengan contoh kontainer
```powershell
PS C:\> $container = New-AzContainerInstanceObject -Name test-container -Image alpine
PS C:\> New-AzContainerGroup -ResourceGroupName testrg-rg -Name test-cg -Location eastus -Container $container

Location Name    Zone ResourceGroupName
-------- ----    ---- -----------------
eastus   test-cg      test-rg
```

Membuat grup wadah dengan contoh kontainer

## PARAMETERS

### -Command
Perintah untuk dijalankan dalam contoh kontainer dalam formulir exec.

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
Variabel lingkungan yang diatur dalam instance kontainer.
Untuk membangun, lihat bagian CATATAN untuk properti ENVIRONMENTVARIABLE dan membuat tabel hash.

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

### -Gambar
Nama gambar yang digunakan untuk membuat contoh kontainer.

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
Batas CPU dari contoh kontainer ini.

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

### -LimitMemoryInGb
Batas memori dalam GB dari instance container ini.

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
Hitungan sumber daya GPU.

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

### -LivenessProbeHttpGetHttpHeader
Header HTTP untuk penyelidikan keaktifan.
Untuk membangun, lihat bagian CATATAN untuk properti LIVENESSPROBEHTTPGETHTTPHEADER dan membuat tabel hash.

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

### -LivenessProbeHttpGetPath
Jalan menuju penyelidikan.

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

### -LivenessProbeHttpGetPort
Nomor port untuk diprobes.

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

### -LivenessProbeHttpGetScheme
Skemanya.

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
Penundaan awal detik.

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
Nama kontainer yang disediakan pengguna.

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
Port yang diekspos pada instance container.
Untuk membangun, lihat bagian CATATAN untuk properti PORT dan membuat tabel hash.

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

### -ReadinessProbeHttpGetHttpHeader
Header HTTP untuk penyelidikan kesiapan.
Untuk membangun, lihat bagian CATATAN untuk properti READINESSPROBEHTTPGETHTTPHEADER dan membuat tabel hash.

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

### -ReadinessProbeHttpGetPath
Jalan menuju penyelidikan.

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

### -ReadinessProbeHttpGetPort
Nomor port untuk diprobes.

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

### -ReadinessProbeHttpGetScheme
Skemanya.

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
Penundaan awal detik.

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
Permintaan CPU dari contoh kontainer ini.

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

### -RequestMemoryInGb
Permintaan memori dalam GB contoh kontainer ini.

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
Hitungan sumber daya GPU.

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

### -RequestsGpuSku
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
Volume akan terpasang pada instance container.
Untuk membangun, lihat bagian CATATAN untuk properti VOLUMEMOUNT dan membuat tabel hash.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ContainerInstance.Models.Api20210901.Container

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


ENVIRONMENTVARIABLE <IEnvironmentVariable[]>: Variabel lingkungan yang diatur dalam instance kontainer.
  - `Name <String>`: Nama variabel lingkungan.
  - `[SecureValue <String>]`: Nilai variabel lingkungan yang aman.
  - `[Value <String>]`: Nilai variabel lingkungan.

LIVENESSPROBEHTTPGETHTTPHEADER <IHttpHeader[]>: Header HTTP untuk penyelidikan liveness.
  - `[Name <String>]`: Nama header.
  - `[Value <String>]`: Nilai header.

PORT <IContainerPort[]>: Port yang terbuka pada instance container.
  - `Port <Int32>`: Nomor port yang diekspos dalam grup kontainer.
  - `[Protocol <ContainerNetworkProtocol?>]`: Protokol yang terkait dengan port.

READINESSPROBEHTTPGETHTTPHEADER <IHttpHeader[]>: Header HTTP untuk penyelidikan kesiapan.
  - `[Name <String>]`: Nama header.
  - `[Value <String>]`: Nilai header.

VOLUMEMOUNT <IVolumeMount[]>: Volume akan terpasang pada instance container.
  - `MountPath <String>`: Jalur dalam wadah tempat volume harus dipasang. Tidak boleh mengandung titik dua (:).
  - `Name <String>`: Nama dudukan volume.
  - `[ReadOnly <Boolean?>]`: Bendera menunjukkan apakah dudukan volume bersifat baca-saja.

## RELATED LINKS

