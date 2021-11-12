---
external help file: Microsoft.Azure.Commands.Batch.dll-Help.xml
Module Name: AzureRM.Batch
ms.assetid: 8BF49C4D-E7CD-4FD0-AFAC-9856239D24EC
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/AzureBatch/Commands.Batch/help/Get-AzureBatchJob.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/AzureBatch/Commands.Batch/help/Get-AzureBatchJob.md
ms.openlocfilehash: c2aa673b9cd0f8cccc3f1a8721313f5a3236270d
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132425352"
---
# Get-AzureBatchJob

## SYNOPSIS
Dapatkan pekerjaan Kumpulan untuk akun Kumpulan atau jadwal pekerjaan.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### ODataFilter (Default)
```
Get-AzureBatchJob [-JobScheduleId <String>] [-Filter <String>] [-MaxCount <Int32>] [-Select <String>]
 [-Expand <String>] -BatchContext <BatchAccountContext> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### Id
```
Get-AzureBatchJob [[-Id] <String>] [-Select <String>] [-Expand <String>] -BatchContext <BatchAccountContext>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ParentObject
```
Get-AzureBatchJob [[-JobSchedule] <PSCloudJobSchedule>] [-Filter <String>] [-MaxCount <Int32>]
 [-Select <String>] [-Expand <String>] -BatchContext <BatchAccountContext>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureBatchJob** mendapatkan pekerjaan Azure Batch untuk akun Batch yang ditentukan oleh parameter *BatchAccountContext.*
Anda dapat menggunakan parameter *Id* untuk mendapatkan pekerjaan tunggal.
Anda dapat menggunakan parameter *Filter* untuk mendapatkan pekerjaan yang cocok dengan filter Open Data Protocol (OData).
Jika Anda menyediakan instans ID jadwal pekerjaan **atau PSCloudJobSchedule,** cmdlet ini hanya mengembalikan pekerjaan untuk jadwal pekerjaan tersebut.

## EXAMPLES

### Contoh 1: Get a Batch job by ID
```
PS C:\>Get-AzureBatchJob -Id "Job01" -BatchContext $Context
CommonEnvironmentSettings   : 
Constraints                 : Microsoft.Azure.Commands.Batch.Models.PSJobConstraints
CreationTime                : 7/25/2015 9:12:07 PM
DisplayName                 : 
ETag                        : 0x8D29535B2941439
ExecutionInformation        : Microsoft.Azure.Commands.Batch.Models.PSJobExecutionInformation
Id                          : Job01
JobManagerTask              : 
JobPreparationTask          : 
JobReleaseTask              : 
LastModified                : 7/25/2015 9:12:07 PM
Metadata                    : 
PoolInformation             : Microsoft.Azure.Commands.Batch.Models.PSPoolInformation
PreviousState               : 
PreviousStateTransitionTime : 
Priority                    : 0
State                       : Active
StateTransitionTime         : 7/25/2015 9:12:07 PM
Statistics                  : 
Url                         : https://pfuller.westus.batch.azure.com/jobs/Job01
```

Perintah ini mendapatkan pekerjaan dengan ID Job01.
Gunakan cmdlet Get-AzureRmBatchAccountKeys cmdlet untuk menetapkan konteks ke variabel $Context tersebut.

### Contoh 2: Mendapatkan semua pekerjaan aktif untuk jadwal pekerjaan
```
PS C:\>Get-AzureBatchJob -JobScheduleId "JobSchedule27" -Filter "state eq 'active'" -BatchContext $Context
CommonEnvironmentSettings   : 
Constraints                 : Microsoft.Azure.Commands.Batch.Models.PSJobConstraints
CreationTime                : 7/25/2015 9:15:44 PM
DisplayName                 : 
ETag                        : 0x8D2953633DD13E1
ExecutionInformation        : Microsoft.Azure.Commands.Batch.Models.PSJobExecutionInformation
Id                          : JobSchedule27:job-1
JobManagerTask              : 
JobPreparationTask          : 
JobReleaseTask              : 
LastModified                : 7/25/2015 9:15:44 PM
Metadata                    : 
PoolInformation             : Microsoft.Azure.Commands.Batch.Models.PSPoolInformation
PreviousState               : 
PreviousStateTransitionTime : 
Priority                    : 0
State                       : Active
StateTransitionTime         : 7/25/2015 9:15:44 PM
Statistics                  : 
Url                         : https://pfuller.westus.batch.azure.com/jobs/JobSchedule27:job-1
```

Perintah ini memperoleh pekerjaan aktif untuk jadwal pekerjaan yang memiliki ID JobSchedule27.

### Contoh 3: Mendapatkan semua pekerjaan dalam jadwal pekerjaan menggunakan pipeline
```
PS C:\>Get-AzureBatchJobSchedule -Id "JobSchedule27" -BatchContext $Context | Get-AzureBatchJob -BatchContext $Context
CommonEnvironmentSettings   : 
Constraints                 : Microsoft.Azure.Commands.Batch.Models.PSJobConstraints
CreationTime                : 7/25/2015 9:15:44 PM
DisplayName                 : 
ETag                        : 0x8D2953633DD13E1
ExecutionInformation        : Microsoft.Azure.Commands.Batch.Models.PSJobExecutionInformation
Id                          : JobSchedule27:job-1
JobManagerTask              : 
JobPreparationTask          : 
JobReleaseTask              : 
LastModified                : 7/25/2015 9:15:44 PM
Metadata                    : 
PoolInformation             : Microsoft.Azure.Commands.Batch.Models.PSPoolInformation
PreviousState               : 
PreviousStateTransitionTime : 
Priority                    : 0
State                       : Active
StateTransitionTime         : 7/25/2015 9:15:44 PM
Statistics                  : 
Url                         : https://pfuller.westus.batch.azure.com/jobs/JobSchedule27:job-1
```

Perintah ini mendapatkan jadwal pekerjaan yang memiliki ID JobSchedule27 menggunakan cmdlet Get-AzureBatchJobSchedule cmdlet.
Perintah itu menyampaikan jadwal kerja itu ke cmdlet saat ini dengan menggunakan operator pipeline.
Perintah tersebut mendapatkan semua pekerjaan untuk jadwal pekerjaan tersebut.

## PARAMETERS

### -BatchContext
Menentukan contoh **BatchAccountContext** yang digunakan cmdlet untuk berinteraksi dengan layanan Batch.
Untuk mendapatkan objek **BatchAccountContext** yang berisi tombol akses untuk langganan Anda, gunakan cmdlet Get-AzureRmBatchAccountKeys cmdlet.

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
Menentukan klausul filter OData untuk pekerjaan.
Jika Anda tidak menentukan filter, cmdlet ini mengembalikan semua pekerjaan untuk akun Kumpulan atau jadwal kerja.

```yaml
Type: System.String
Parameter Sets: ODataFilter, ParentObject
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
Menentukan ID pekerjaan yang akan dapatkan cmdlet ini.
Anda tidak bisa menentukan karakter wildcard.

```yaml
Type: System.String
Parameter Sets: Id
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobSchedule
Menentukan objek **PSCloudJobSchedule** yang mewakili jadwal pekerjaan yang berisi pekerjaan.
Untuk mendapatkan objek **PSCloudJobSchedule,** gunakan Get-AzureBatchJobSchedule cmdlet.

```yaml
Type: Microsoft.Azure.Commands.Batch.Models.PSCloudJobSchedule
Parameter Sets: ParentObject
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -JobScheduleId
Menentukan ID jadwal pekerjaan yang berisi pekerjaan.

```yaml
Type: System.String
Parameter Sets: ODataFilter
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MaxCount
Menentukan jumlah maksimum pekerjaan untuk dikembalikan.
Jika Anda menentukan nilai nol (0) atau kurang, cmdlet tidak menggunakan batas atas.
Nilai defaultnya adalah 1000.

```yaml
Type: System.Int32
Parameter Sets: ODataFilter, ParentObject
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

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### BatchAccountContext
Parameter 'BatchContext' menerima nilai tipe 'BatchAccountContext' dari saluran

### PSCloudJobSchedule
Parameter 'JobSchedule' menerima nilai tipe 'PSCloudJobSchedule' dari saluran

## OUTPUTS

### PSCloudJob

## CATATAN

## RELATED LINKS

[Disable-AzureBatchJob](./Disable-AzureBatchJob.md)

[Enable-AzureBatchJob](./Enable-AzureBatchJob.md)

[Get-AzureRmBatchAccountKeys](./Get-AzureRmBatchAccountKeys.md)

[Get-AzureBatchJobSchedule](./Get-AzureBatchJobSchedule.md)

[New-AzureBatchJob](./New-AzureBatchJob.md)

[Remove-AzureBatchJob](./Remove-AzureBatchJob.md)

[Stop-AzureBatchJob](./Stop-AzureBatchJob.md)

[Cmdlet Kumpulan Azure](./AzureRM.Batch.md)


