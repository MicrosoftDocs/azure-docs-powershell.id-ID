---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Batch.dll-Help.xml
Module Name: Az.Batch
ms.assetid: BF0C1A2F-2703-492F-A3A7-053416A5D1EB
online version: https://docs.microsoft.com/powershell/module/az.batch/test-azbatchautoscale
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Batch/Batch/help/Test-AzBatchAutoScale.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Batch/Batch/help/Test-AzBatchAutoScale.md
ms.openlocfilehash: 717bfa219e1a87337ec53bc67ce23acd5a09ddbb
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143359703"
---
# Test-AzBatchAutoScale

## SYNOPSIS
Mendapatkan hasil rumus penskalaan otomatis pada kumpulan.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.batch/test-azbatchautoscale) untuk informasi terbaru.

## SYNTAX

```
Test-AzBatchAutoScale [-Id] <String> [-AutoScaleFormula] <String> -BatchContext <BatchAccountContext>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Test-AzBatchAutoScale** mendapatkan hasil rumus penskalaan otomatis pada kumpulan yang ditentukan.

## EXAMPLES

### Contoh 1: Mengevaluasi rumus skala otomatis pada kumpulan
```powershell
$Formula = 'totalNodes=($CPUPercent.GetSamplePercent(TimeInterval_Minute*0,TimeInterval_Minute*10)<0.7?5:(min($CPUPercent.GetSample(TimeInterval_Minute*0, TimeInterval_Minute*10))>0.8?($CurrentDedicated*1.1):$CurrentDedicated));$TargetDedicated=min(100,totalNodes);';
$Evaluation = Test-AzBatchAutoScale -Id "ContosoPool" -AutoScaleFormula $Formula -BatchContext $Context
$Evaluation.AutoScaleRun.Results
$TargetDedicated=5;$NodeDeallocationOption=requeue;totalNodes=5
```

Perintah pertama menyimpan rumus dalam variabel $Formula untuk digunakan dalam contoh.
Perintah kedua mengevaluasi rumus skala otomatis pada kumpulan yang memiliki ID ContosoPool.
Perintah akhir menampilkan **Hasil** dengan menggunakan sintaks titik standar.

## PARAMETERS

### -AutoScaleFormula
Menentukan rumus untuk jumlah node komputasi yang diinginkan dalam kumpulan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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
Menentukan ID objek kumpulan untuk menguji penskalaan otomatis.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### Microsoft.Azure.Commands.Batch.BatchAccountContext

## OUTPUTS

### Microsoft.Azure.Commands.Batch.Models.PSAutoScaleRun

## NOTES

## RELATED LINKS

[Disable-AzBatchAutoScale](./Disable-AzBatchAutoScale.md)

[Enable-AzBatchAutoScale](./Enable-AzBatchAutoScale.md)

[Get-AzBatchAccountKey](./Get-AzBatchAccountKey.md)

[Cmdlet Azure Batch](/powershell/module/Az.Batch/)
