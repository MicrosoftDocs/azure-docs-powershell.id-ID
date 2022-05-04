---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Batch.dll-Help.xml
Module Name: Az.Batch
ms.assetid: C9E2D9EC-3B6A-492D-B183-9856185548CD
online version: https://docs.microsoft.com/powershell/module/az.batch/get-azbatchnodefilecontent
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Batch/Batch/help/Get-AzBatchNodeFileContent.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Batch/Batch/help/Get-AzBatchNodeFileContent.md
ms.openlocfilehash: 3e9507c26bf6726d9a7670efd3228cb5930537cd
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144579854"
---
# Get-AzBatchNodeFileContent

## SYNOPSIS
Mendapatkan file simpul Batch.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.batch/get-azbatchnodefilecontent) untuk informasi terbaru.

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
Cmdlet **Get-AzBatchNodeFileContent** mendapatkan file simpul Azure Batch dan menyimpannya sebagai file atau ke aliran.

## EXAMPLES

### Contoh 1: Mendapatkan file simpul Batch yang terkait dengan tugas dan menyimpan file
```powershell
Get-AzBatchNodeFileContent -JobId "Job01" -TaskId "Task01" -Path "StdOut.txt" -DestinationPath "E:\PowerShell\StdOut.txt" -BatchContext $Context
```

Perintah ini mendapatkan file simpul yang diberi nama StdOut.txt, dan menyimpannya ke jalur file E:\PowerShell\StdOut.txt di komputer lokal.
File simpul StdOut.txt dikaitkan dengan tugas yang memiliki ID Task01 untuk pekerjaan yang memiliki ID Job01.
Gunakan cmdlet Get-AzBatchAccountKey untuk menetapkan konteks ke variabel $Context.

### Contoh 2: Dapatkan file simpul Batch dan simpan ke jalur file tertentu menggunakan alur
```powershell
Get-AzBatchNodeFile -JobId "Job02" -TaskId "Task02" -Path "StdErr.txt" -BatchContext $Context | Get-AzBatchNodeFileContent -DestinationPath "E:\PowerShell\StdOut.txt" -BatchContext $Context
```

Perintah ini mendapatkan file simpul yang diberi nama StdErr.txt dengan menggunakan cmdlet Get-AzBatchNodeFile.
Perintah meneruskan file tersebut ke cmdlet saat ini dengan menggunakan operator alur.
Cmdlet saat ini menyimpan file tersebut ke jalur file E:\PowerShell\StdOut.txt pada komputer lokal.
File simpul StdOut.txt dikaitkan dengan tugas yang memiliki TUGAS ID02 untuk pekerjaan yang memiliki ID Job02.

### Contoh 3: Mendapatkan file simpul Batch yang terkait dengan tugas dan mengarahkannya ke aliran
```powershell
$Stream = New-Object -TypeName "System.IO.MemoryStream"
Get-AzBatchNodeFileContent -JobId "Job03" -TaskId "Task11" -Path "StdOut.txt" -DestinationStream $Stream -BatchContext $Context
```

Perintah pertama membuat aliran dengan menggunakan cmdlet New-Object, lalu menyimpannya dalam variabel $Stream.
Perintah kedua mendapatkan file simpul yang diberi nama StdOut.txt dari tugas yang memiliki ID Task11 untuk pekerjaan yang memiliki ID Job03.
Perintah mengarahkan konten file ke aliran di $Stream.

### Contoh 4: Dapatkan file simpul dari simpul komputasi dan simpan
```powershell
Get-AzBatchNodeFileContent -PoolId "Pool01" -ComputeNodeId "ComputeNode01" -Path "Startup\StdOut.txt" -DestinationPath "E:\PowerShell\StdOut.txt" -BatchContext $Context
```

Perintah ini mendapatkan file simpul Startup\StdOut.txt dari simpul komputasi yang memiliki ID ComputeNode01 di kumpulan yang memiliki ID Pool01.
Perintah menyimpan file ke jalur file E:\PowerShell\StdOut.txt di komputer lokal.

### Contoh 5: Dapatkan file simpul dari simpul komputasi dan simpan dengan menggunakan alur
```powershell
Get-AzBatchNodeFile -PoolId "Pool01" -ComputeNodeId "ComputeNode01" -Path "Startup\StdOut.txt" -BatchContext $Context | Get-AzBatchNodeFileContent -DestinationPath "E:\PowerShell\StdOut.txt" -BatchContext $Context
```

Perintah ini mendapatkan file simpul Startup\StdOut.txt dengan menggunakan Get-AzBatchNodeFile dari simpul komputasi yang memiliki ID ComputeNode01.
Simpul komputasi berada di kumpulan yang memiliki ID Pool01.
Perintah meneruskan file simpul tersebut ke cmdlet saat ini.
Cmdlet tersebut menyimpan file ke jalur file E:\PowerShell\StdOut.txt di komputer lokal.

### Contoh 6: Dapatkan file simpul dari simpul komputasi dan arahkan ke aliran
```powershell
$Stream = New-Object -TypeName "System.IO.MemoryStream"
Get-AzBatchNodeFileContent -PoolId "Pool01" -ComputeNodeId "ComputeNode01" -Path "startup\stdout.txt" -DestinationStream $Stream -BatchContext $Context
```

Perintah pertama membuat aliran dengan menggunakan cmdlet New-Object, lalu menyimpannya dalam variabel $Stream.
Perintah kedua mendapatkan file simpul yang diberi nama StdOut.txt dari simpul komputasi yang memiliki ID ComputeNode01 di kumpulan yang memiliki ID Pool01.
Perintah mengarahkan konten file ke aliran di $Stream.

## PARAMETERS

### -BatchContext
Menentukan instans **BatchAccountContext** yang digunakan cmdlet ini untuk berinteraksi dengan layanan Batch.
Jika Anda menggunakan cmdlet Get-AzBatchAccount untuk mendapatkan BatchAccountContext Anda, maka autentikasi Azure Active Directory akan digunakan saat berinteraksi dengan layanan Batch. Untuk menggunakan autentikasi kunci bersama, gunakan cmdlet Get-AzBatchAccountKey untuk mendapatkan objek BatchAccountContext dengan kunci aksesnya yang diisi. Saat menggunakan autentikasi kunci bersama, kunci akses utama digunakan secara default. Untuk mengubah kunci yang akan digunakan, atur properti BatchAccountContext.KeyInUse.

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
Menentukan ID simpul komputasi yang berisi file simpul yang dikembalikan cmdlet ini.

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

### -DestinationPath
Menentukan jalur file tempat cmdlet ini menyimpan file simpul.

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
Menentukan aliran tempat cmdlet ini menulis konten file simpul.
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
Menentukan file yang didapat cmdlet ini, sebagai objek **PSNodeFile** .
Untuk mendapatkan objek file simpul, gunakan cmdlet Get-AzBatchNodeFile.

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

### -Jalur
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
Menentukan ID kumpulan yang berisi simpul komputasi yang berisi file simpul yang didapatkan cmdlet ini.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

### Microsoft.Azure.Commands.Batch.Models.PSNodeFile

### Microsoft.Azure.Commands.Batch.BatchAccountContext

## OUTPUTS

### System.Void

## NOTES

## RELATED LINKS

[Get-AzBatchAccountKey](./Get-AzBatchAccountKey.md)

[Get-AzBatchNodeFile](./Get-AzBatchNodeFile.md)

[Cmdlet Azure Batch](/powershell/module/Az.Batch/)
