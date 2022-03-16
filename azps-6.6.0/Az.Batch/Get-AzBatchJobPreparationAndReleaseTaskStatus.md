---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Batch.dll-Help.xml
Module Name: Az.Batch
online version: https://docs.microsoft.com/powershell/module/az.batch/get-azbatchjobpreparationandreleasetaskstatus
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Batch/Batch/help/Get-AzBatchJobPreparationAndReleaseTaskStatus.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Batch/Batch/help/Get-AzBatchJobPreparationAndReleaseTaskStatus.md
ms.openlocfilehash: cfbd9155f02a9d1e2c1b28535ec7b5985817b08a
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "139980141"
---
# Get-AzBatchJobPreparationAndReleaseTaskStatus

## SYNOPSIS
Dapatkan persiapan pekerjaan Kumpulan dan lepaskan status tugas.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.batch/get-azbatchjobpreparationandreleasetaskstatus) untuk informasi terkini.

## SYNTAX

### Id (Default)
```
Get-AzBatchJobPreparationAndReleaseTaskStatus [-Id] <String> [-Filter <String>] [-MaxCount <Int32>]
 [-Select <String>] [-Expand <String>] -BatchContext <BatchAccountContext>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### InputObject
```
Get-AzBatchJobPreparationAndReleaseTaskStatus [-InputObject] <PSCloudJob> [-Filter <String>]
 [-MaxCount <Int32>] [-Select <String>] [-Expand <String>] -BatchContext <BatchAccountContext>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzBatchJobPreparationAndReleaseTaskStatus** menyiapkan dan merilis status tugas Azure Batch untuk pekerjaan Kumpulan.
Anda harus menyediakan *parameter Id* atau instans **PSCloudJob** ke cmdlet ini.

## EXAMPLES

### Contoh 1: Mendapatkan status persiapan pekerjaan dan rilis pekerjaan
```
PS C:\> Get-AzBatchJobPreparationAndReleaseTaskStatus -BatchContext $Context -Id Test

ComputeNodeId                          : tvm-2316545714_1-20170613t201733z
ComputeNodeUrl                         : https://account.westus.batch.azure.com/pools/test/nodes/tvm-2316545714_1-20170613t201733z
JobPreparationTaskExecutionInformation : Microsoft.Azure.Commands.Batch.Models.PSJobPreparationTaskExecutionInformation
JobReleaseTaskExecutionInformation     :
PoolId                                 : test
```

Perintah ini mendapatkan status persiapan pekerjaan dan rilis tugas untuk "Tes" pekerjaan.
Gunakan cmdlet Get-AzBatchAccountKey cmdlet untuk menetapkan konteks ke $Context variabel.

### Contoh 2: Dapatkan status persiapan pekerjaan dan rilis pekerjaan dengan Filter dan Pilih yang ditentukan
```
PS C:\> Get-AzBatchJobPreparationAndReleaseTaskStatus -BatchContext $context -Id Test -Filter "nodeId eq 'tvm-2316545714_1-20170613t201733z'" -Select "jobPreparationTaskExecutionInfo"

ComputeNodeId                          :
ComputeNodeUrl                         :
JobPreparationTaskExecutionInformation : Microsoft.Azure.Commands.Batch.Models.PSJobPreparationTaskExecutionInformation
JobReleaseTaskExecutionInformation     :
PoolId                                 :
```

Perintah ini mendapatkan status tugas persiapan dan rilis pekerjaan untuk "Tes" pekerjaan di node "tvm-2316545714_1-20170613t201733z" dan menggunakan klausul Select untuk menentukan untuk hanya mengembalikan informasi JobPreparationTaskExecutionInformation

## PARAMETERS

### -BatchContext
Contoh BatchAccountContext untuk digunakan ketika berinteraksi dengan layanan Batch.
Gunakan cmdlet Get-AzBatchAccountKey untuk mendapatkan objek BatchAccountContext dengan tombol aksesnya diisi.

```yaml
Type: Microsoft.Azure.Commands.Batch.BatchAccountContext
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Perluas
Menentukan klausul perluas Open Data Protocol (OData).
Tentukan nilai untuk parameter ini untuk mendapatkan entitas terkait dari entitas utama yang Anda dapatkan.

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

### -Filter
Menentukan klausul filter OData.
Jika Anda tidak menentukan filter, cmdlet ini akan mengembalikan semua status persiapan dan rilis tugas pekerjaan untuk pekerjaan tersebut.

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

### -Id
Menentukan ID pekerjaan yang tugas persiapan dan rilisnya harus diambil.
Anda tidak bisa menentukan karakter wildcard.

```yaml
Type: System.String
Parameter Sets: Id
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Menentukan objek **PSCloudJob** yang mewakili pekerjaan untuk mendapatkan status tugas persiapan dan rilis.
Untuk mendapatkan objek **PSCloudJob** , gunakan Get-AzBatchJob cmdlet.

```yaml
Type: Microsoft.Azure.Commands.Batch.Models.PSCloudJob
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -MaxCount
Menentukan jumlah maksimum dari persiapan pekerjaan dan status tugas rilis yang akan dikembalikan.
Jika Anda menentukan nilai nol (0) atau kurang, cmdlet tidak menggunakan batas atas.
Nilai defaultnya adalah 1000.

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

### -Pilih
Menentukan klausul pilih OData.
Tentukan nilai untuk parameter ini agar mendapatkan properti tertentu dan bukan semua properti objek.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Batch.Models.PSCloudJob

### Microsoft.Azure.Commands.Batch.BatchAccountContext

## OUTPUTS

### Microsoft.Azure.Commands.Batch.Models.PSJobPreparationAndReleaseTaskExecutionInformation

## CATATAN

## RELATED LINKS

[Get-AzBatchJob](./Get-AzBatchJob.md)

[Cmdlet Kumpulan Azure](/powershell/module/Az.Batch/)
