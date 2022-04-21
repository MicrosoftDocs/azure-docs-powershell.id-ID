---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Batch.dll-Help.xml
Module Name: Az.Batch
ms.assetid: A202537B-D292-4822-A0B9-27A6A20621D4
online version: https://docs.microsoft.com/powershell/module/az.batch/reset-azbatchcomputenode
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Batch/Batch/help/Reset-AzBatchComputeNode.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Batch/Batch/help/Reset-AzBatchComputeNode.md
ms.openlocfilehash: 20c361692f1a81f66381925fad1e23841365b641
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142811404"
---
# Reset-AzBatchComputeNode

## SYNOPSIS
Menginstal ulang sistem operasi pada simpul komputasi yang ditentukan.

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
Cmdlet **Reset-AzBatchComputeNode** menginstal ulang sistem operasi pada simpul komputasi yang ditentukan.

## EXAMPLES

### Contoh 1: Reimage a node
```powershell
Reset-AzBatchComputeNode -PoolId "MyPool" -Id "tvm-3257026573_2-20150813t200938z" -BatchContext $Context
```

Perintah ini mereimage simpul komputasi dengan ID "tvm-3257026573_2-20150813t200938z" di kolam renang bernama MyPool.
Gunakan cmdlet Get-AzBatchAccountKey untuk menetapkan konteks ke variabel $Context.

### Contoh 2: Reimage all node in a pool
```powershell
Get-AzBatchComputeNode -PoolId "MyPool" -BatchContext $Context | Reset-AzBatchComputeNode -BatchContext $Context
```

Perintah ini mereimensikan setiap node komputasi di kolam bernama MyPool.

## PARAMETERS

### -BatchContext
Menentukan instans **BatchAccountContext** yang digunakan cmdlet ini untuk berinteraksi dengan layanan Batch.
Jika Anda menggunakan cmdlet Get-AzBatchAccount untuk mendapatkan BatchAccountContext, autentikasi Azure Active Directory akan digunakan saat berinteraksi dengan layanan Batch. Untuk menggunakan autentikasi kunci bersama, gunakan cmdlet Get-AzBatchAccountKey untuk mendapatkan objek BatchAccountContext dengan tombol akses yang diisi. Ketika menggunakan autentikasi kunci bersama, kunci akses utama digunakan secara default. Untuk mengubah kunci yang akan digunakan, atur properti BatchAccountContext.KeyInUse.

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
Menentukan objek **PSComputeNode** yang mewakili node komputasi untuk direimage.

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

### -Id
Menentukan ID simpul komputasi untuk direimage.

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
Menentukan ID kumpulan yang berisi simpul komputasi.

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
Menentukan waktu untuk mengolah ulang simpul dan apa yang harus dilakukan dengan tugas yang sedang berjalan saat ini.
Defaultnya adalah Antrean Ulang.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Batch.Models.PSComputeNode

### Microsoft.Azure.Commands.Batch.BatchAccountContext

## OUTPUTS

### System.Void

## NOTES

## RELATED LINKS

[Get-AzBatchComputeNode](./Get-AzBatchComputeNode.md)

[Mulai ulang-AzBatchComputeNode](./Restart-AzBatchComputeNode.md)

[Cmdlet Azure Batch](/powershell/module/Az.Batch/)
