---
external help file: ''
Module Name: Az.ContainerInstance
online version: https://docs.microsoft.com/powershell/module/az.ContainerInstance/new-AzContainerInstanceObject
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/New-AzContainerInstanceObject.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/ContainerInstance/help/New-AzContainerInstanceObject.md
ms.openlocfilehash: 745445180f3ca943422032f65a21b931d30d2f12
ms.sourcegitcommit: 321c644cf2161807a71e1af318fc5c5311d22e25
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/25/2022
ms.locfileid: "145793188"
---
# New-AzContainerInstanceObject

## SYNOPSIS
Membuat objek dalam memori untuk Kontainer

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.containerinstance/new-azcontainerinstanceobject) untuk informasi terbaru.

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

### Contoh 1: Membuat instans kontainer menggunakan alphine gambar dengan cpu permintaan 1.0 dan meminta memori 1,5Gb
```powershell
New-AzContainerInstanceObject -Name "test-container" -Image alpine -RequestCpu 1 -RequestMemoryInGb 1.5
```

```output
Name
----
test-container
```

Membuat instans kontainer menggunakan alphine gambar dengan cpu permintaan 1.0 dan meminta memori 1,5Gb

### Contoh 2: Buat instans kontainer menggunakan alphine gambar dengan batas cpu 2.0 dan batasi memori 2,5Gb
```powershell
New-AzContainerInstanceObject -Image alpine -Name "test-container" -LimitCpu 2 -LimitMemoryInGb 2.5
```

```output
Name
----
test-container
```

Membuat instans kontainer menggunakan alphine gambar dengan batas cpu 2.0 dan batasi memori 2,5Gb

### Contoh 3: Membuat grup kontainer dengan instans kontainer
```powershell
$container = New-AzContainerInstanceObject -Name test-container -Image alpine
New-AzContainerGroup -ResourceGroupName testrg-rg -Name test-cg -Location eastus -Container $container
```

```output
Location Name    Zone ResourceGroupName
-------- ----    ---- -----------------
eastus   test-cg      test-rg
```

Membuat grup kontainer dengan instans kontainer

## PARAMETERS

### -Perintah
Perintah untuk menjalankan di dalam instans kontainer dalam bentuk eksekusi.

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
Variabel lingkungan yang akan diatur dalam instans kontainer.
Untuk membuat, lihat bagian CATATAN untuk properti ENVIRONMENTVARIABLE dan buat tabel hash.

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
Nama gambar yang digunakan untuk membuat instans kontainer.

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
Batas CPU instans kontainer ini.

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
Batas memori dalam GB dari instans kontainer ini.

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
Perintah untuk menjalankan dalam kontainer.

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
Header HTTP untuk pemeriksaan keaktivaan.
Untuk membuat, lihat bagian CATATAN untuk properti LIVENESSPROBEHTTPGETHTTPHEADER dan buat tabel hash.

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
Jalur menuju penyelidikan.

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
Nomor port untuk diselidiki.

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
Detik waktu habis.

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

### -Name
Nama instans kontainer yang disediakan pengguna.

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
Port yang terekspos di instans kontainer.
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
Perintah untuk menjalankan dalam kontainer.

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
Header HTTP untuk pemeriksaan kesiapan.
Untuk membuat, lihat bagian CATATAN untuk properti READINESSPROBEHTTPGETHTTPHEADER dan buat tabel hash.

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
Jalur menuju penyelidikan.

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
Nomor port untuk diselidiki.

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
Detik waktu habis.

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
Permintaan CPU instans kontainer ini.

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
Permintaan memori dalam GB dari instans kontainer ini.

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
Mount volume yang tersedia untuk instans kontainer.
Untuk membuat, lihat bagian CATATAN untuk properti VOLUMEMOUNT dan buat tabel hash.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

## OUTPUTS

### Microsoft.Azure.PowerShell.Cmdlets.ContainerInstance.Models.Api20210901.Container

## NOTES

ALIAS

PROPERTI PARAMETER KOMPLEKS

Untuk membuat parameter yang dijelaskan di bawah ini, buat tabel hash yang berisi properti yang sesuai. Untuk informasi tentang tabel hash, jalankan Get-Help about_Hash_Tables.


ENVIRONMENTVARIABLE <IEnvironmentVariable[]>: Variabel lingkungan yang akan diatur dalam instans kontainer.
  - `Name <String>`: Nama variabel lingkungan.
  - `[SecureValue <String>]`: Nilai variabel lingkungan yang aman.
  - `[Value <String>]`: Nilai variabel lingkungan.

LIVENESSPROBEHTTPGETHTTPHEADER <IHttpHeader[]>: Header HTTP untuk pemeriksaan keaktifan.
  - `[Name <String>]`: Nama header.
  - `[Value <String>]`: Nilai header.

PORT <IContainerPort[]>: Port yang diekspos pada instans kontainer.
  - `Port <Int32>`: Nomor port yang terekspos dalam grup kontainer.
  - `[Protocol <ContainerNetworkProtocol?>]`: Protokol yang terkait dengan port.

READINESSPROBEHTTPGETHTTPHEADER <IHttpHeader[]>: Header HTTP untuk pemeriksaan kesiapan.
  - `[Name <String>]`: Nama header.
  - `[Value <String>]`: Nilai header.

VOLUMEMOUNT <IVolumeMount[]>: Volume dipasang tersedia untuk instans kontainer.
  - `MountPath <String>`: Jalur dalam kontainer tempat volume harus dipasang. Tidak boleh ada titik dua (:).
  - `Name <String>`: Nama pemasangan volume.
  - `[ReadOnly <Boolean?>]`: Bendera yang menunjukkan apakah pemasangan volume bersifat baca-saja.

## RELATED LINKS

