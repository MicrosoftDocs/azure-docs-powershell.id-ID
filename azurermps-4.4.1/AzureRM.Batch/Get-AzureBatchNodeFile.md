---
external help file: Microsoft.Azure.Commands.Batch.dll-Help.xml
Module Name: AzureRM.Batch
ms.assetid: 38ED2854-23D0-400E-A5C8-239346B2AF99
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/AzureBatch/Commands.Batch/help/Get-AzureBatchNodeFile.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/AzureBatch/Commands.Batch/help/Get-AzureBatchNodeFile.md
ms.openlocfilehash: 0a027bd15d4b207baf9c69fcb9104428c2881872
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132424397"
---
# Get-AzureBatchNodeFile

## SYNOPSIS
Mendapatkan properti file node Kumpulan.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### ComputeNode_Id (Default)
```
Get-AzureBatchNodeFile [-PoolId] <String> [-ComputeNodeId] <String> [[-Name] <String>]
 -BatchContext <BatchAccountContext> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### Task_Id
```
Get-AzureBatchNodeFile -JobId <String> -TaskId <String> [[-Name] <String>] -BatchContext <BatchAccountContext>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### Task_ODataFilter
```
Get-AzureBatchNodeFile -JobId <String> -TaskId <String> [-Filter <String>] [-MaxCount <Int32>] [-Recursive]
 -BatchContext <BatchAccountContext> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### Tanda Kurung
```
Get-AzureBatchNodeFile [[-Task] <PSCloudTask>] [-Filter <String>] [-MaxCount <Int32>] [-Recursive]
 -BatchContext <BatchAccountContext> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ComputeNode_ODataFilter
```
Get-AzureBatchNodeFile [-PoolId] <String> [-ComputeNodeId] <String> [-Filter <String>] [-MaxCount <Int32>]
 [-Recursive] -BatchContext <BatchAccountContext> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### ParentComputeNode
```
Get-AzureBatchNodeFile [[-ComputeNode] <PSComputeNode>] [-Filter <String>] [-MaxCount <Int32>] [-Recursive]
 -BatchContext <BatchAccountContext> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureBatchNodeFile** mendapatkan properti file node Azure Batch dari tugas atau node perhitungan.
Untuk mempersempit hasil Anda, Anda bisa menentukan filter Open Data Protocol (OData).
Jika Anda menentukan tugas, tetapi bukan filter, cmdlet ini akan mengembalikan properti untuk semua file node untuk tugas tersebut.
Jika Anda menentukan simpul perhitungan, tetapi bukan filter, cmdlet ini mengembalikan properti untuk semua file node untuk node perhitungan itu.

## EXAMPLES

### Contoh 1: Mendapatkan properti file simpul yang terkait dengan tugas
```
PS C:\>Get-AzureBatchNodeFile -JobId "Job-000001" -TaskId "Task26" -Name "Stdout.txt" -BatchContext $Context
IsDirectory Name          Properties                                      Url

----------- ----          ----------                                      ---

False       StdOut.txt    Microsoft.Azure.Commands.Batch.Models.PSFile... https://cmdletexample.westus.Batch.contoso...
```

Perintah ini mendapatkan properti file node StdOut.txt terkait dengan tugas yang memiliki ID Task26 dalam pekerjaan yang memiliki ID Job-000001.
Gunakan cmdlet Get-AzureRmBatchAccountKeys cmdlet untuk menetapkan konteks ke variabel $Context tersebut.

### Contoh 2: Dapatkan properti file node yang terkait dengan tugas menggunakan filter
```
PS C:\>Get-AzureBatchNodeFile -JobId "Job-00002" -TaskId "Task26" -Filter "startswith(name,'St')" -BatchContext $Context
IsDirectory Name        Properties                                      Url

----------- ----        ----------                                      ---

False       StdErr.txt  Microsoft.Azure.Commands.Batch.Models.PSFile... https://cmdletexample.westus.Batch.contoso... 
False       StdOut.txt  Microsoft.Azure.Commands.Batch.Models.PSFile... https://cmdletexample.westus.Batch.contoso...
```

Perintah ini mendapatkan properti file node yang namanya dimulai dengan st dan terkait dengan tugas yang memiliki ID Task26 berdasarkan pekerjaan yang memiliki ID Job-00002.

### Contoh 3: Mendapatkan properti file simpul yang terkait dengan tugas secara rekursif
```
PS C:\>Get-AzureBatchTask "Job-00003" "Task31" -BatchContext $Context | Get-AzureBatchNodeFile -Recursive -BatchContext $Context
IsDirectory Name             Properties                                      Url

----------- ----             ----------                                      ---

False       ProcessEnv.cmd   Microsoft.Azure.Commands.Batch.Models.PSFile... https://cmdletexample.westus.Batch.contoso... 
False       StdErr.txt       Microsoft.Azure.Commands.Batch.Models.PSFile... https://cmdletexample.westus.Batch.contoso... 
False       StdOut.txt       Microsoft.Azure.Commands.Batch.Models.PSFile... https://cmdletexample.westus.Batch.contoso... 
True        wd                                                               https://cmdletexample.westus.Batch.contoso... 
False       wd\newFile.txt   Microsoft.Azure.Commands.Batch.Models.PSFile... https://cmdletexample.westus.Batch.contoso...
```

Perintah ini mendapatkan properti semua file yang terkait dengan tugas yang memiliki ID Task31 dalam pekerjaan Pekerjaan-00003.
Perintah ini menentukan parameter *Rekursif.*
Oleh karena itu, cmdlet akan melakukan pencarian file berulang, dan mengembalikan file wd\newFile.txt node tersebut.

### Contoh 4: Dapatkan satu file dari simpul perhitungan
```
PS C:\>Get-AzureBatchNodeFile -PoolId "Pool22" -ComputeNodeId "ComputeNode01" -Name "Startup\StdOut.txt" -BatchContext $Context
IsDirectory Name                    Properties                                      Url
----------- ----                    ----------                                      ---
False       startup\stdout.txt      Microsoft.Azure.Commands.Batch.Models.PSFile... https://cmdletexample.westus.Batch.contoso...
```

Perintah ini mendapatkan file yang diberi nama Startup\StdOut.txt dari node hitung yang memiliki ID ComputeNode01 di pool yang memiliki ID Pool22.

### Contoh 5: Mendapatkan semua file dalam folder dari node perhitungan
```
PS C:\>Get-AzureBatchNodeFile -PoolId "Pool22" -ComputeNodeId "ComputeNode01" -Filter "startswith(name,'startup')" -Recursive -BatchContext $Context
IsDirectory Name                      Properties                                      Url
----------- ----                      ----------                                      ---
True        startup                                                                   https://cmdletexample.westus.Batch.contoso... 
False       startup\ProcessEnv.cmd    Microsoft.Azure.Commands.Batch.Models.PSFile... https://cmdletexample.westus.Batch.contoso... 
False       startup\stderr.txt        Microsoft.Azure.Commands.Batch.Models.PSFile... https://cmdletexample.westus.Batch.contoso... 
False       startup\stdout.txt        Microsoft.Azure.Commands.Batch.Models.PSFile... https://cmdletexample.westus.Batch.contoso... 
True        startup\wd                                                                https://cmdletexample.westus.Batch.contoso...
```

Perintah ini mendapatkan semua file di bawah folder mulai dari node hitung yang memiliki ID ComputeNode01 di pool yang memiliki ID Pool22.
Cmdlet ini menentukan parameter *Rekursif.*

### Contoh 6: Dapatkan file dari folder akar node perhitungan
```
PS C:\>Get-AzureBatchComputeNode "Pool22" -Id "ComputeNode01" -BatchContext $Context | Get-AzureBatchNodeFile -BatchContext $Context
IsDirectory Name           Properties       Url
----------- ----           ----------       ---
True        shared                          https://cmdletexample.westus.Batch.contoso... 
True        startup                         https://cmdletexample.westus.Batch.contoso... 
True        workitems                       https://cmdletexample.westus.Batch.contoso...
```

Perintah ini mendapatkan semua file di folder akar node hitung yang memiliki ID ComputeNode01 di pool yang memiliki ID Pool22.

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

### -ComputeNode
Menentukan node perhitungan, sebagai objek **PSComputeNode,** yang berisi file node Batch.
Untuk mendapatkan objek node perhitungan, gunakan Get-AzureBatchComputeNode cmdlet.

```yaml
Type: Microsoft.Azure.Commands.Batch.Models.PSComputeNode
Parameter Sets: ParentComputeNode
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ComputeNodeId
Menentukan ID node hitung yang berisi file node Batch.

```yaml
Type: System.String
Parameter Sets: ComputeNode_Id, ComputeNode_ODataFilter
Aliases: 

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Filter
Menentukan klausul filter OData.
Cmdlet ini mengembalikan properti untuk file node yang cocok dengan filter yang ditentukan parameter ini.

```yaml
Type: System.String
Parameter Sets: Task_ODataFilter, ParentTask, ComputeNode_ODataFilter, ParentComputeNode
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -JobId
Menentukan ID pekerjaan yang berisi tugas target.

```yaml
Type: System.String
Parameter Sets: Task_Id, Task_ODataFilter
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -MaxCount
Menentukan jumlah maksimum file node yang dikembalikan cmdlet ini.
Jika Anda menentukan nilai nol (0) atau kurang, cmdlet tidak menggunakan batas atas.
Nilai defaultnya adalah 1000.

```yaml
Type: System.Int32
Parameter Sets: Task_ODataFilter, ParentTask, ComputeNode_ODataFilter, ParentComputeNode
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Menentukan nama file node yang propertinya diambil cmdlet ini.
Anda tidak bisa menentukan karakter wildcard.

```yaml
Type: System.String
Parameter Sets: ComputeNode_Id, Task_Id
Aliases: 

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PoolId
Menentukan ID pool yang berisi node perhitungan untuk mendapatkan properti file node.

```yaml
Type: System.String
Parameter Sets: ComputeNode_Id, ComputeNode_ODataFilter
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Rekursif
Mengindikasikan bahwa cmdlet ini mengembalikan daftar file rekursif.
Jika tidak, file akan dikembalikan hanya dalam folder akar.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Task_ODataFilter, ParentTask, ComputeNode_ODataFilter, ParentComputeNode
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Tugas
Menentukan tugas, sebagai objek **PSCloudTask,** dengan file node yang terkait.
Untuk mendapatkan objek tugas, gunakan cmdlet Get-AzureBatchTask.

```yaml
Type: Microsoft.Azure.Commands.Batch.Models.PSCloudTask
Parameter Sets: ParentTask
Aliases: 

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -TaskId
Menentukan ID tugas yang mendapatkan properti file node dari cmdlet ini.

```yaml
Type: System.String
Parameter Sets: Task_Id, Task_ODataFilter
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### PSComputeNode
Parameter 'ComputeNode' menerima nilai tipe 'PSComputeNode' dari saluran

### PSCloudTask
Parameter 'Tugas' menerima nilai tipe 'PSCloudTask' dari saluran

## OUTPUTS

### PSNodeFile

## CATATAN

## RELATED LINKS

[Get-AzureRmBatchAccountKeys](./Get-AzureRmBatchAccountKeys.md)

[Get-AzureBatchComputeNode](./Get-AzureBatchComputeNode.md)

[Get-AzureBatchNodeFileContent](./Get-AzureBatchNodeFileContent.md)

[Get-AzureBatchTask](./Get-AzureBatchTask.md)

[Cmdlet Kumpulan Azure](./AzureRM.Batch.md)


