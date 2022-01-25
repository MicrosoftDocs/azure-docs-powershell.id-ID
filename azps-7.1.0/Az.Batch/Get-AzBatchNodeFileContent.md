---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Batch.dll-Help.xml
Module Name: Az.Batch
ms.assetid: C9E2D9EC-3B6A-492D-B183-9856185548CD
online version: https://docs.microsoft.com/powershell/module/az.batch/get-azbatchnodefilecontent
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Batch/Batch/help/Get-AzBatchNodeFileContent.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Batch/Batch/help/Get-AzBatchNodeFileContent.md
ms.openlocfilehash: 0a16ed5c3ade6d6f43ab2c70eba61b744d4306e3
ms.sourcegitcommit: e109cc5320478db6aa8a52d49996b133007a65b9
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 01/12/2022
ms.locfileid: "136741459"
---
# Get-AzBatchNodeFileContent

## SYNOPSIS
Mendapatkan file node Kumpulan.

## SYNTAX

### Task_Id_Path
```
Get-AzBatchNodeFileContent -JobId <String> -TaskId <String> [-Path] <String> -DestinationPath <String>
 [-ByteRangeStart <Int64>] [-ByteRangeEnd <Int64>] -BatchContext <BatchAccountContext>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### Task_Id_Stream
```
Get-AzBatchNodeFileContent -JobId <String> -TaskId <String> [-Path] <String> -DestinationStream <Stream>
 [-ByteRangeStart <Int64>] [-ByteRangeEnd <Int64>] -BatchContext <BatchAccountContext>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ComputeNode_Id_Path
```
Get-AzBatchNodeFileContent [-PoolId] <String> [-ComputeNodeId] <String> [-Path] <String>
 -DestinationPath <String> [-ByteRangeStart <Int64>] [-ByteRangeEnd <Int64>]
 -BatchContext <BatchAccountContext> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ComputeNode_Id_Stream
```
Get-AzBatchNodeFileContent [-PoolId] <String> [-ComputeNodeId] <String> [-Path] <String>
 -DestinationStream <Stream> [-ByteRangeStart <Int64>] [-ByteRangeEnd <Int64>]
 -BatchContext <BatchAccountContext> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### InputObject_Path
```
Get-AzBatchNodeFileContent [[-InputObject] <PSNodeFile>] -DestinationPath <String> [-ByteRangeStart <Int64>]
 [-ByteRangeEnd <Int64>] -BatchContext <BatchAccountContext> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### InputObject_Stream
```
Get-AzBatchNodeFileContent [[-InputObject] <PSNodeFile>] -DestinationStream <Stream> [-ByteRangeStart <Int64>]
 [-ByteRangeEnd <Int64>] -BatchContext <BatchAccountContext> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzBatchNodeFileContent** mendapatkan file node Azure Batch dan menyimpannya sebagai file atau ke streaming.

## EXAMPLES

### Contoh 1: Dapatkan file node Kumpulan yang terkait dengan tugas dan simpan file
```
PS C:\>Get-AzBatchNodeFileContent -JobId "Job01" -TaskId "Task01" -Path "StdOut.txt" -DestinationPath "E:\PowerShell\StdOut.txt" -BatchContext $Context
```

Perintah ini mendapatkan file node yang dinamai StdOut.txt, dan menyimpannya ke jalur file E:\PowerShell\StdOut.txt di komputer lokal.
File StdOut.txt node terkait dengan tugas yang memiliki ID Task01 untuk pekerjaan yang memiliki ID Job01.
Gunakan cmdlet Get-AzBatchAccountKey cmdlet untuk menetapkan konteks ke $Context variabel.

### Contoh 2: Dapatkan file node Kumpulan dan simpan ke jalur file tertentu menggunakan saluran
```
PS C:\>Get-AzBatchNodeFile -JobId "Job02" -TaskId "Task02" -Path "StdErr.txt" -BatchContext $Context | Get-AzBatchNodeFileContent -DestinationPath "E:\PowerShell\StdOut.txt" -BatchContext $Context
```

Perintah ini mendapatkan file node yang dinamai StdErr.txt dengan menggunakan cmdlet Get-AzBatchNodeFile.
Perintah meneruskan file itu ke cmdlet saat ini menggunakan operator pipeline.
Cmdlet saat ini menyimpan file tersebut ke E:\PowerShell\StdOut.txt jalur file di komputer lokal.
File node StdOut.txt terkait dengan tugas yang memiliki ID Task02 untuk pekerjaan yang memiliki ID Job02.

### Contoh 3: Dapatkan file node Kumpulan yang terkait dengan tugas dan arahkan ke aliran
```
PS C:\>$Stream = New-Object -TypeName "System.IO.MemoryStream"
PS C:\> Get-AzBatchNodeFileContent -JobId "Job03" -TaskId "Task11" -Path "StdOut.txt" -DestinationStream $Stream -BatchContext $Context
```

Perintah pertama membuat aliran menggunakan cmdlet New-Object, lalu menyimpannya di $Stream variabel.
Perintah kedua mendapatkan file node yang dinamai StdOut.txt dari tugas yang memiliki ID Task11 untuk pekerjaan yang memiliki ID Job03.
Perintah mengarahkan konten file ke streaming di $Stream.

### Contoh 4: Dapatkan file node dari node hitung dan simpan
```
PS C:\>Get-AzBatchNodeFileContent -PoolId "Pool01" -ComputeNodeId "ComputeNode01" -Path "Startup\StdOut.txt" -DestinationPath "E:\PowerShell\StdOut.txt" -BatchContext $Context
```

Perintah ini mendapatkan file node Startup\StdOut.txt dari node hitung yang memiliki ID ComputeNode01 di pool yang memiliki ID Pool01.
Perintah menyimpan file ke E:\PowerShell\StdOut.txt jalur file di komputer lokal.

### Contoh 5: Dapatkan file node dari node hitung dan simpan dengan menggunakan saluran
```
PS C:\>Get-AzBatchNodeFile -PoolId "Pool01" -ComputeNodeId "ComputeNode01" -Path "Startup\StdOut.txt" -BatchContext $Context | Get-AzBatchNodeFileContent -DestinationPath "E:\PowerShell\StdOut.txt" -BatchContext $Context
```

Perintah ini mendapatkan file node Startup\StdOut.txt menggunakan Get-AzBatchNodeFile dari node hitung yang memiliki ID ComputeNode01.
Node perhitungan berada di pool yang memiliki ID Pool01.
Perintah meneruskan file node itu ke cmdlet saat ini.
Cmdlet tersebut menyimpan file ke E:\PowerShell\StdOut.txt file di komputer lokal.

### Contoh 6: Dapatkan file node dari node hitung dan arahkan ke aliran
```
PS C:\>$Stream = New-Object -TypeName "System.IO.MemoryStream"
PS C:\> Get-AzBatchNodeFileContent -PoolId "Pool01" -ComputeNodeId "ComputeNode01" -Path "startup\stdout.txt" -DestinationStream $Stream -BatchContext $Context
```

Perintah pertama membuat aliran menggunakan cmdlet New-Object, lalu menyimpannya di $Stream variabel.
Perintah kedua mendapatkan file node yang dinamai StdOut.txt dari node perhitungan yang memiliki ID ComputeNode01 dalam pool yang memiliki ID Pool01.
Perintah mengarahkan konten file ke streaming di $Stream.

## PARAMETERS

### -BatchContext
Menentukan contoh **BatchAccountContext** yang digunakan cmdlet untuk berinteraksi dengan layanan Batch.
Jika Anda menggunakan cmdlet Get-AzBatchAccount untuk mendapatkan BatchAccountContext, autentikasi Azure Active Directory akan digunakan saat berinteraksi dengan layanan Batch. Untuk menggunakan autentikasi kunci bersama, gunakan cmdlet Get-AzBatchAccountKey untuk mendapatkan objek BatchAccountContext dengan tombol aksesnya diisi. Saat menggunakan autentikasi kunci bersama, kunci akses utama digunakan secara default. Untuk mengubah kunci yang akan digunakan, atur properti BatchAccountContext.KeyInUse.

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

### -ByteRangeEnd
Akhir rentang byte yang akan diunduh.

```yaml
Type: System.Nullable`1[System.Int64]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ByteRangeStart
Awal rentang byte yang akan diunduh.

```yaml
Type: System.Nullable`1[System.Int64]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ComputeNodeId
Menentukan ID node hitung yang berisi file node yang dikembalikan cmdlet ini.

```yaml
Type: System.String
Parameter Sets: ComputeNode_Id_Path, ComputeNode_Id_Stream
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### -DestinationPath
Menentukan jalur file tempat cmdlet ini menyimpan file node.

```yaml
Type: System.String
Parameter Sets: Task_Id_Path, ComputeNode_Id_Path, InputObject_Path
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DestinationStream
Menentukan aliran tempat cmdlet menulis konten file node.
Cmdlet ini tidak menutup atau memutar balik aliran ini.

```yaml
Type: System.IO.Stream
Parameter Sets: Task_Id_Stream, ComputeNode_Id_Stream, InputObject_Stream
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject
Menentukan file yang akan dapatkan cmdlet ini, sebagai objek **PSNodeFile.**
Untuk mendapatkan objek file node, gunakan cmdlet Get-AzBatchNodeFile.

```yaml
Type: Microsoft.Azure.Commands.Batch.Models.PSNodeFile
Parameter Sets: InputObject_Path, InputObject_Stream
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -JobId
Menentukan ID pekerjaan yang berisi tugas target.

```yaml
Type: System.String
Parameter Sets: Task_Id_Path, Task_Id_Stream
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path
Jalur file simpul untuk diunduh.

```yaml
Type: System.String
Parameter Sets: Task_Id_Path, Task_Id_Stream, ComputeNode_Id_Path, ComputeNode_Id_Stream
Aliases: Name

Required: True
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PoolId
Menentukan ID pool yang berisi node perhitungan yang berisi file node yang didaurkan cmdlet ini.

```yaml
Type: System.String
Parameter Sets: ComputeNode_Id_Path, ComputeNode_Id_Stream
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -TaskId
Menentukan ID tugas.

```yaml
Type: System.String
Parameter Sets: Task_Id_Path, Task_Id_Stream
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Azure.Commands.Batch.Models.PSNodeFile

### Microsoft.Azure.Commands.Batch.BatchAccountContext

## OUTPUTS

### System.Void

## CATATAN

## RELATED LINKS

[Get-AzBatchAccountKey](./Get-AzBatchAccountKey.md)

[Get-AzBatchNodeFile](./Get-AzBatchNodeFile.md)

[Cmdlet Kumpulan Azure](/powershell/module/Az.Batch/)
