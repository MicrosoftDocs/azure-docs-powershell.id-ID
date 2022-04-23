---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Batch.dll-Help.xml
Module Name: Az.Batch
ms.assetid: 82DC8DC4-D8EC-4847-A54C-B779256FD590
online version: https://docs.microsoft.com/powershell/module/az.batch/start-azbatchpoolresize
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Batch/Batch/help/Start-AzBatchPoolResize.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Batch/Batch/help/Start-AzBatchPoolResize.md
ms.openlocfilehash: a9351f4ca3b417f2b9993563cd4de4bb9f222c36
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143302229"
---
# Start-AzBatchPoolResize

## SYNOPSIS
Mulai mengubah ukuran kolam renang.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.batch/start-azbatchpoolresize) untuk informasi terbaru.

## SYNTAX

```
Start-AzBatchPoolResize [-Id] <String> [-TargetDedicatedComputeNodes <Int32>]
 [-TargetLowPriorityComputeNodes <Int32>] [-ResizeTimeout <TimeSpan>]
 [-ComputeNodeDeallocationOption <ComputeNodeDeallocationOption>] -BatchContext <BatchAccountContext>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Start-AzBatchPoolResize** memulai operasi pengulangan ukuran Azure Batch pada kolam renang.

## EXAMPLES

### Contoh 1: Mengubah ukuran kumpulan menjadi 12 node
```
PS C:\>Start-AzBatchPoolResize -Id "ContosoPool06" -TargetDedicatedComputeNodes 12 -BatchContext $Context
```

Perintah ini memulai operasi ubah ukuran pada kumpulan yang memiliki ID ContosoPool06.
Target untuk operasi ini adalah 12 node komputasi khusus.
Gunakan cmdlet Get-AzBatchAccountKey untuk menetapkan konteks ke variabel $Context.

### Contoh 2: Mengubah ukuran kumpulan menggunakan opsi penawaran
```
PS C:\>Get-AzBatchPool -Id "ContosoPool06" -BatchContext $Context | Start-AzBatchPoolResize -TargetDedicatedComputeNodes 5 -ResizeTimeout ([TimeSpan]::FromHours(1)) -ComputeNodeDeallocationOption ([Microsoft.Azure.Batch.Common.ComputeNodeDeallocationOption]::Terminate) -BatchContext $Context
```

Cmdlet ini mengubah ukuran kolam menjadi lima node komputasi khusus.
Perintah mendapatkan kolam yang memiliki ID ContosoPool06 dengan menggunakan cmdlet Get-AzBatchPool.
Perintah melewati objek pool tersebut ke cmdlet saat ini menggunakan operator pipeline.
Perintah memulai operasi ubah ukuran pada kumpulan.
Targetnya adalah lima node komputasi khusus.
Perintah menentukan periode batas waktu satu jam.
Perintah menentukan opsi deallocation Dari Hentikan.

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

### -ComputeNodeAllocationOption
Menentukan opsi deallokasi untuk operasi pengulangan ukuran yang dimulai cmdlet ini.

```yaml
Type: System.Nullable`1[Microsoft.Azure.Batch.Common.ComputeNodeDeallocationOption]
Parameter Sets: (All)
Aliases:
Accepted values: Requeue, Terminate, TaskCompletion, RetainedData

Required: False
Position: Named
Default value: None
Accept pipeline input: False
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
Menentukan ID kumpulan yang diubah ukuran cmdletnya.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -ResizeTimeout
Menentukan periode waktu habis untuk operasi pengubahan ukuran.
Jika pool tidak mencapai ukuran target saat ini, operasi ubah ukuran berhenti.

```yaml
Type: System.Nullable`1[System.TimeSpan]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetDedicatedComputeNodes
Jumlah node komputasi khusus target.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases: TargetDedicated

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetLowPriorityComputeNodes
Jumlah node komputasi prioritas rendah target.

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Azure.Commands.Batch.BatchAccountContext

## OUTPUTS

### System.Void

## NOTES

## RELATED LINKS

[Get-AzBatchAccountKey](./Get-AzBatchAccountKey.md)

[Get-AzBatchPool](./Get-AzBatchPool.md)

[Stop-AzBatchPoolResize](./Stop-AzBatchPoolResize.md)

[Cmdlet Azure Batch](/powershell/module/Az.Batch/)
