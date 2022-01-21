---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Batch.dll-Help.xml
Module Name: Az.Batch
ms.assetid: A202537B-D292-4822-A0B9-27A6A20621D4
online version: https://docs.microsoft.com/powershell/module/az.batch/reset-azbatchcomputenode
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Batch/Batch/help/Reset-AzBatchComputeNode.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Batch/Batch/help/Reset-AzBatchComputeNode.md
ms.openlocfilehash: 4fac48a3eeaeb9b9c61997d91b7b65478b6ea91f
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136557323"
---
# Reset-AzBatchComputeNode

## SYNOPSIS
Menginstal ulang sistem operasi pada node perhitungan yang ditentukan.

## SYNTAX

### Id (Default)
```
Reset-AzBatchComputeNode [-PoolId] <String> [-Id] <String> [-ReimageOption <ComputeNodeReimageOption>]
 -BatchContext <BatchAccountContext> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### InputObject
```
Reset-AzBatchComputeNode [[-ComputeNode] <PSComputeNode>] [-ReimageOption <ComputeNodeReimageOption>]
 -BatchContext <BatchAccountContext> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Reset-AzBatchComputeNode** menginstal ulang sistem operasi pada node perhitungan yang ditentukan.

## EXAMPLES

### Contoh 1: Mengganti simpul
```
PS C:\>Reset-AzBatchComputeNode -PoolId "MyPool" -Id "tvm-3257026573_2-20150813t200938z" -BatchContext $Context
```

Perintah ini akan mengulangi node perhitungan dengan ID "tvm-3257026573_2-20150813t200938z" di pool bernama MyPool.
Gunakan cmdlet Get-AzBatchAccountKey cmdlet untuk menetapkan konteks ke $Context penerima.

### Contoh 2: Mengganti semua simpul dalam sebuah pool
```
PS C:\>Get-AzBatchComputeNode -PoolId "MyPool" -BatchContext $Context | Reset-AzBatchComputeNode -BatchContext $Context
```

Perintah ini akan mengulangi setiap node perhitungan dalam pool yang bernama MyPool.

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

### -ComputeNode
Menentukan objek **PSComputeNode** yang mewakili node perhitungan untuk mengganti.

```yaml
Type: Microsoft.Azure.Commands.Batch.Models.PSComputeNode
Parameter Sets: InputObject
Aliases:

Required: False
Position: 0
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

### -Id
Menentukan ID node hitung untuk mengganti.

```yaml
Type: System.String
Parameter Sets: Id
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PoolId
Menentukan ID pool yang berisi node perhitungan.

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

### -ReimageOption
Menentukan kapan mengganti simpul dan apa yang harus dilakukan dengan tugas yang sedang berjalan.
Defaultnya adalah Requeue.

```yaml
Type: System.Nullable`1[Microsoft.Azure.Batch.Common.ComputeNodeReimageOption]
Parameter Sets: (All)
Aliases:
Accepted values: Requeue, Terminate, TaskCompletion, RetainedData

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Batch.Models.PSComputeNode

### Microsoft.Azure.Commands.Batch.BatchAccountContext

## OUTPUTS

### System.Void

## CATATAN

## RELATED LINKS

[Get-AzBatchComputeNode](./Get-AzBatchComputeNode.md)

[Restart-AzBatchComputeNode](./Restart-AzBatchComputeNode.md)

[Cmdlet Kumpulan Azure](/powershell/module/Az.Batch/)
