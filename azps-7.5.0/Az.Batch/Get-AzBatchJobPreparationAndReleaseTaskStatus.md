---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Batch.dll-Help.xml
Module Name: Az.Batch
online version: https://docs.microsoft.com/powershell/module/az.batch/get-azbatchjobpreparationandreleasetaskstatus
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Batch/Batch/help/Get-AzBatchJobPreparationAndReleaseTaskStatus.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Batch/Batch/help/Get-AzBatchJobPreparationAndReleaseTaskStatus.md
ms.openlocfilehash: 2408501a80ef908adf8ae85f3bbd91da877ba046
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144240306"
---
# Get-AzBatchJobPreparationAndReleaseTaskStatus

## SYNOPSIS
Mendapatkan persiapan pekerjaan Batch dan status tugas rilis.

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
**Cmdlet Get-AzBatchJobPreparationAndReleaseTaskStatus** mendapatkan Azure Batch persiapan pekerjaan dan melepaskan status tugas untuk pekerjaan Batch.
Anda harus menyediakan parameter *Id* atau **instans PSCloudJob** ke cmdlet ini.

## EXAMPLES

### Contoh 1: Mendapatkan status persiapan dan rilis pekerjaan
```powershell
Get-AzBatchJobPreparationAndReleaseTaskStatus -BatchContext $Context -Id Test
```

```output
ComputeNodeId                          : tvm-2316545714_1-20170613t201733z
ComputeNodeUrl                         : https://account.westus.batch.azure.com/pools/test/nodes/tvm-2316545714_1-20170613t201733z
JobPreparationTaskExecutionInformation : Microsoft.Azure.Commands.Batch.Models.PSJobPreparationTaskExecutionInformation
JobReleaseTaskExecutionInformation     :
PoolId                                 : test
```

Perintah ini mendapatkan persiapan pekerjaan dan status tugas rilis untuk pekerjaan "Uji".
Gunakan cmdlet Get-AzBatchAccountKey untuk menetapkan konteks ke variabel $Context.

### Contoh 2: Dapatkan status persiapan dan rilis pekerjaan dengan Filter dan Pilih yang ditentukan
```powershell
Get-AzBatchJobPreparationAndReleaseTaskStatus -BatchContext $context -Id Test -Filter "nodeId eq 'tvm-2316545714_1-20170613t201733z'" -Select "jobPreparationTaskExecutionInfo"
```

```output
ComputeNodeId                          :
ComputeNodeUrl                         :
JobPreparationTaskExecutionInformation : Microsoft.Azure.Commands.Batch.Models.PSJobPreparationTaskExecutionInformation
JobReleaseTaskExecutionInformation     :
PoolId                                 :
```

Perintah ini mendapatkan status tugas persiapan dan pelepasan pekerjaan untuk pekerjaan "Uji" pada node "tvm-2316545714_1-20170613t201733z" dan menggunakan klausa Select untuk menentukan untuk hanya mengembalikan informasi JobPreparationTaskExecutionInformation

## PARAMETERS

### -BatchContext
Instans BatchAccountContext untuk digunakan saat berinteraksi dengan layanan Batch.
Gunakan cmdlet Get-AzBatchAccountKey untuk mendapatkan objek BatchAccountContext dengan kunci aksesnya yang diisi.

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
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

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
Menentukan klausa perluasan Open Data Protocol (OData).
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
Menentukan klausa filter OData.
Jika Anda tidak menentukan filter, cmdlet ini mengembalikan semua persiapan pekerjaan dan status tugas rilis' untuk pekerjaan tersebut.

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
Menentukan ID pekerjaan yang tugas persiapan dan pelepasannya harus diambil.
Anda tidak dapat menentukan karakter kartubebas.

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
Menentukan objek **PSCloudJob** yang mewakili pekerjaan untuk mendapatkan status tugas persiapan dan pelepasan.
Untuk mendapatkan objek **PSCloudJob** , gunakan cmdlet Get-AzBatchJob.

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
Menentukan jumlah maksimum persiapan pekerjaan dan status tugas rilis' untuk dikembalikan.
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
Menentukan klausa pilih OData.
Tentukan nilai untuk parameter ini untuk mendapatkan properti tertentu daripada semua properti objek.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.Commands.Batch.Models.PSCloudJob

### Microsoft.Azure.Commands.Batch.BatchAccountContext

## OUTPUTS

### Microsoft.Azure.Commands.Batch.Models.PSJobPreparationAndReleaseTaskExecutionInformation

## NOTES

## RELATED LINKS

[Get-AzBatchJob](./Get-AzBatchJob.md)

[Cmdlet Azure Batch](/powershell/module/Az.Batch/)
