---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Batch.dll-Help.xml
Module Name: Az.Batch
ms.assetid: 38ED2854-23D0-400E-A5C8-239346B2AF99
online version: https://docs.microsoft.com/powershell/module/az.batch/get-azbatchnodefile
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Batch/Batch/help/Get-AzBatchNodeFile.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Batch/Batch/help/Get-AzBatchNodeFile.md
ms.openlocfilehash: 9515b2da5cd3f9cbee441aaebd3c3cec1f889740
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145515607"
---
# Get-AzBatchNodeFile

## SYNOPSIS
Mendapatkan properti file simpul Batch.

## SYNTAX

### ComputeNode_Id (Default)
```
Get-AzBatchNodeFile [-PoolId] <String> [-ComputeNodeId] <String> [[-Path] <String>]
 -BatchContext <BatchAccountContext> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### Task_Id
```
Get-AzBatchNodeFile -JobId <String> -TaskId <String> [[-Path] <String>] -BatchContext <BatchAccountContext>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### Task_ODataFilter
```
Get-AzBatchNodeFile -JobId <String> -TaskId <String> [-Filter <String>] [-MaxCount <Int32>] [-Recursive]
 -BatchContext <BatchAccountContext> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ParentTask
```
Get-AzBatchNodeFile [[-Task] <PSCloudTask>] [-Filter <String>] [-MaxCount <Int32>] [-Recursive]
 -BatchContext <BatchAccountContext> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ComputeNode_ODataFilter
```
Get-AzBatchNodeFile [-PoolId] <String> [-ComputeNodeId] <String> [-Filter <String>] [-MaxCount <Int32>]
 [-Recursive] -BatchContext <BatchAccountContext> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### ParentComputeNode
```
Get-AzBatchNodeFile [[-ComputeNode] <PSComputeNode>] [-Filter <String>] [-MaxCount <Int32>] [-Recursive]
 -BatchContext <BatchAccountContext> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzBatchNodeFile** mendapatkan properti file simpul Azure Batch dari tugas atau simpul komputasi.
Untuk mempersempit hasil, Anda dapat menentukan filter Open Data Protocol (OData).
Jika Anda menentukan tugas, tetapi bukan filter, cmdlet ini mengembalikan properti untuk semua file simpul untuk tugas tersebut.
Jika Anda menentukan simpul komputasi, tetapi bukan filter, cmdlet ini mengembalikan properti untuk semua file simpul untuk simpul komputasi tersebut.

## EXAMPLES

### Contoh 1: Mendapatkan properti file simpul yang terkait dengan tugas
```powershell
Get-AzBatchNodeFile -JobId "Job-000001" -TaskId "Task26" -Path "Stdout.txt" -BatchContext $Context
```

```output
IsDirectory Name          Properties                                      Url

----------- ----          ----------                                      ---

False       StdOut.txt    Microsoft.Azure.Commands.Batch.Models.PSFile... https://cmdletexample.westus.Batch.contoso...
```

Perintah ini mendapatkan properti file simpul StdOut.txt yang terkait dengan tugas yang memiliki Tugas ID26 dalam pekerjaan yang memiliki ID Job-000001.
Gunakan cmdlet Get-AzBatchAccountKey untuk menetapkan konteks ke variabel $Context.

### Contoh 2: Mendapatkan properti file simpul yang terkait dengan tugas dengan menggunakan filter
```powershell
Get-AzBatchNodeFile -JobId "Job-00002" -TaskId "Task26" -Filter "startswith(name,'St')" -BatchContext $Context
```

```output
IsDirectory Name        Properties                                      Url

----------- ----        ----------                                      ---

False       StdErr.txt  Microsoft.Azure.Commands.Batch.Models.PSFile... https://cmdletexample.westus.Batch.contoso...
False       StdOut.txt  Microsoft.Azure.Commands.Batch.Models.PSFile... https://cmdletexample.westus.Batch.contoso...
```

Perintah ini mendapatkan properti file simpul yang namanya dimulai dengan st dan dikaitkan dengan tugas yang memiliki TUGAS ID26 di bawah pekerjaan yang memiliki ID Job-00002.

### Contoh 3: Secara rekursif mendapatkan properti file simpul yang terkait dengan tugas
```powershell
Get-AzBatchTask "Job-00003" "Task31" -BatchContext $Context | Get-AzBatchNodeFile -Recursive -BatchContext $Context
```

```output
IsDirectory Name             Properties                                      Url

----------- ----             ----------                                      ---

False       ProcessEnv.cmd   Microsoft.Azure.Commands.Batch.Models.PSFile... https://cmdletexample.westus.Batch.contoso...
False       StdErr.txt       Microsoft.Azure.Commands.Batch.Models.PSFile... https://cmdletexample.westus.Batch.contoso...
False       StdOut.txt       Microsoft.Azure.Commands.Batch.Models.PSFile... https://cmdletexample.westus.Batch.contoso...
True        wd                                                               https://cmdletexample.westus.Batch.contoso...
False       wd\newFile.txt   Microsoft.Azure.Commands.Batch.Models.PSFile... https://cmdletexample.westus.Batch.contoso...
```

Perintah ini mendapatkan properti semua file yang terkait dengan tugas yang memiliki TUGAS ID31 dalam pekerjaan Job-00003.
Perintah ini menentukan parameter *Rekursif* .
Oleh karena itu, cmdlet melakukan pencarian file rekursif dilakukan, dan mengembalikan file simpul wd\newFile.txt.

### Contoh 4: Mendapatkan satu file dari simpul komputasi
```powershell
Get-AzBatchNodeFile -PoolId "Pool22" -ComputeNodeId "ComputeNode01" -Path "Startup\StdOut.txt" -BatchContext $Context
```

```output
IsDirectory Name                    Properties                                      Url
----------- ----                    ----------                                      ---
False       startup\stdout.txt      Microsoft.Azure.Commands.Batch.Models.PSFile... https://cmdletexample.westus.Batch.contoso...
```

Perintah ini mendapatkan file yang diberi nama Startup\StdOut.txt dari simpul komputasi yang memiliki ID ComputeNode01 di kumpulan yang memiliki ID Pool22.

### Contoh 5: Mendapatkan semua file di bawah folder dari simpul komputasi
```powershell
Get-AzBatchNodeFile -PoolId "Pool22" -ComputeNodeId "ComputeNode01" -Filter "startswith(name,'startup')" -Recursive -BatchContext $Context
```

```output
IsDirectory Name                      Properties                                      Url
----------- ----                      ----------                                      ---
True        startup                                                                   https://cmdletexample.westus.Batch.contoso...
False       startup\ProcessEnv.cmd    Microsoft.Azure.Commands.Batch.Models.PSFile... https://cmdletexample.westus.Batch.contoso...
False       startup\stderr.txt        Microsoft.Azure.Commands.Batch.Models.PSFile... https://cmdletexample.westus.Batch.contoso...
False       startup\stdout.txt        Microsoft.Azure.Commands.Batch.Models.PSFile... https://cmdletexample.westus.Batch.contoso...
True        startup\wd                                                                https://cmdletexample.westus.Batch.contoso...
```

Perintah ini mendapatkan semua file di bawah folder startup dari simpul komputasi yang memiliki ID ComputeNode01 di kumpulan yang memiliki ID Pool22.
Cmdlet ini menentukan parameter *Rekursif* .

### Contoh 6: Mendapatkan file dari folder akar simpul komputasi
```powershell
Get-AzBatchComputeNode "Pool22" -Id "ComputeNode01" -BatchContext $Context | Get-AzBatchNodeFile -BatchContext $Context
```

```output
IsDirectory Name           Properties       Url
----------- ----           ----------       ---
True        shared                          https://cmdletexample.westus.Batch.contoso...
True        startup                         https://cmdletexample.westus.Batch.contoso...
True        workitems                       https://cmdletexample.westus.Batch.contoso...
```

Perintah ini mendapatkan semua file di folder akar simpul komputasi yang memiliki ID ComputeNode01 di kumpulan yang memiliki ID Pool22.

## PARAMETERS

### -BatchContext
Menentukan instans **BatchAccountContext** yang digunakan cmdlet ini untuk berinteraksi dengan layanan Batch.
Jika Anda menggunakan cmdlet Get-AzBatchAccount untuk mendapatkan BatchAccountContext Anda, maka autentikasi Azure Active Directory akan digunakan saat berinteraksi dengan layanan Batch. Untuk menggunakan autentikasi kunci bersama sebagai gantinya, gunakan cmdlet Get-AzBatchAccountKey untuk mendapatkan objek BatchAccountContext dengan kunci aksesnya yang diisi. Saat menggunakan autentikasi kunci bersama, kunci akses utama digunakan secara default. Untuk mengubah kunci yang akan digunakan, atur properti BatchAccountContext.KeyInUse.

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
Menentukan simpul komputasi, sebagai objek **PSComputeNode** , yang berisi file simpul Batch.
Untuk mendapatkan objek simpul komputasi, gunakan cmdlet Get-AzBatchComputeNode.

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
Menentukan ID simpul komputasi yang berisi file simpul Batch.

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

### -Filter
Menentukan klausa filter OData.
Cmdlet ini mengembalikan properti untuk file simpul yang cocok dengan filter yang ditentukan parameter ini.

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
Menentukan jumlah maksimum file simpul yang cmdlet ini mengembalikan properti.
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

### -Jalur
Menentukan jalur file simpul tempat cmdlet ini mengambil properti.
Anda tidak dapat menentukan karakter kartubebas.

```yaml
Type: System.String
Parameter Sets: ComputeNode_Id, Task_Id
Aliases: Name

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PoolId
Menentukan ID kumpulan yang berisi simpul komputasi untuk mendapatkan properti file simpul.

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
Menunjukkan bahwa cmdlet ini mengembalikan daftar file rekursif.
Jika tidak, ia hanya mengembalikan file di folder akar.

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
Menentukan tugas, sebagai objek **PSCloudTask** , yang dengannya file simpul dikaitkan.
Untuk mendapatkan objek tugas, gunakan cmdlet Get-AzBatchTask.

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
Menentukan ID tugas tempat cmdlet ini mendapatkan properti file simpul.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

### Microsoft.Azure.Commands.Batch.Models.PSCloudTask

### Microsoft.Azure.Commands.Batch.Models.PSComputeNode

### Microsoft.Azure.Commands.Batch.BatchAccountContext

## OUTPUTS

### Microsoft.Azure.Commands.Batch.Models.PSNodeFile

## NOTES

## RELATED LINKS

[Get-AzBatchAccountKey](./Get-AzBatchAccountKey.md)

[Get-AzBatchComputeNode](./Get-AzBatchComputeNode.md)

[Get-AzBatchNodeFileContent](./Get-AzBatchNodeFileContent.md)

[Get-AzBatchTask](./Get-AzBatchTask.md)

[Cmdlet Azure Batch](/powershell/module/Az.Batch/)
