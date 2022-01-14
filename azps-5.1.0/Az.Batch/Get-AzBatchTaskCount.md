---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Batch.dll-Help.xml
Module Name: Az.Batch
online version: https://docs.microsoft.com/en-us/powershell/module/az.batch/get-azbatchtaskcount
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Batch/Batch/help/Get-AzBatchTaskCount.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Batch/Batch/help/Get-AzBatchTaskCount.md
ms.openlocfilehash: d1f493556a1ff1007073611338b937ef0715c164
ms.sourcegitcommit: d81c3b0f0f7289104be03869eb675128b61db7d3
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/17/2020
ms.locfileid: "136011274"
---
# Get-AzBatchTaskCount

## SYNOPSIS
Mendapatkan hitungan tugas untuk pekerjaan tertentu.

## SINTAKS

### Id
```
Get-AzBatchTaskCount [-JobId] <String> -BatchContext <BatchAccountContext>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ParentObject
```
Get-AzBatchTaskCount [[-Job] <PSCloudJob>] -BatchContext <BatchAccountContext>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESKRIPSI
Cmdlet **Get-AzBatchTaskCount** mendapatkan jumlah tugas Azure Batch untuk pekerjaan Kumpulan.
Tentukan pekerjaan dengan parameter *JobId* atau *parameter Job.*
Hitungan tugas menyediakan hitungan tugas menurut status tugas aktif, berjalan atau selesai, dan hitungan tugas yang berhasil atau gagal. Tugas dalam keadaan mempersiapkan dihitung sebagai berjalan. Jika validationStatus tidak divalidasi, layanan Kumpulan belum dapat memeriksa jumlah status terhadap status tugas seperti yang dilaporkan di API Tugas Daftar. ValidasiStatus mungkin tidak divalidasi jika pekerjaan berisi lebih dari 200.000 tugas.

## CONTOH

### Contoh 1: Dapatkan hitungan tugas menurut ID
```
PS C:\> Get-AzBatchTaskCount -JobId "Job01" -Id "Task03" -BatchContext $Context
Active              : 1
Completed           : 0
Failed              : 0
Running             : 1
Succeeded           : 5
ValidationStatus    : Validated
```

Perintah ini menghitung jumlah tugas untuk pekerjaan Job01.
Gunakan cmdlet Get-AzBatchAccountKey cmdlet untuk menetapkan konteks ke $Context variabel.

## PARAMETERS

### -BatchContext
Contoh BatchAccountContext untuk digunakan ketika berinteraksi dengan layanan Batch.
Jika Anda menggunakan cmdlet Get-AzBatchAccount untuk mendapatkan BatchAccountContext, autentikasi Azure Active Directory akan digunakan saat berinteraksi dengan layanan Batch.
Untuk menggunakan autentikasi kunci bersama, gunakan cmdlet Get-AzBatchAccountKey untuk mendapatkan objek BatchAccountContext dengan tombol aksesnya diisi.
Saat menggunakan autentikasi kunci bersama, kunci akses utama digunakan secara default.
Untuk mengubah kunci yang akan digunakan, atur properti BatchAccountContext.KeyInUse.

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

### -Job
Menentukan pekerjaan berisi tugas yang akan didaurkan cmdlet ini.
Untuk mendapatkan objek **PSCloudJob,** gunakan cmdlet Get-AzBatchJob baru.

```yaml
Type: Microsoft.Azure.Commands.Batch.Models.PSCloudJob
Parameter Sets: ParentObject
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -JobId
Id pekerjaan untuk mendapatkan hitungan tugas.

```yaml
Type: System.String
Parameter Sets: Id
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUT

### System.String

### Microsoft.Azure.Commands.Batch.Models.PSCloudJob

### Microsoft.Azure.Commands.Batch.BatchAccountContext

## OUTPUT

### Microsoft.Azure.Commands.Batch.Models.PSTaskCounts

## CATATAN

## LINK TERKAIT

[Get-AzBatchAccountKey](./Get-AzBatchAccountKey.md)

[Get-AzBatchJob](./Get-AzBatchJob.md)

[Cmdlet Kumpulan Azure](/powershell/module/Az.Batch/)
