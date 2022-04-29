---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Batch.dll-Help.xml
Module Name: Az.Batch
online version: https://docs.microsoft.com/powershell/module/az.batch/get-azbatchtaskslotcount
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Batch/Batch/help/Get-AzBatchTaskSlotCount.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Batch/Batch/help/Get-AzBatchTaskSlotCount.md
ms.openlocfilehash: 60e02a382d000bc8e1981be6c31556e9aca0a438
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144245035"
---
# Get-AzBatchTaskSlotCount

## SYNOPSIS
Mendapatkan jumlah slot tugas untuk pekerjaan yang ditentukan.

## SYNTAX

### Id (Default)
```
Get-AzBatchTaskSlotCount [-JobId] <String> -BatchContext <BatchAccountContext>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ParentObject
```
Get-AzBatchTaskSlotCount [[-Job] <PSCloudJob>] -BatchContext <BatchAccountContext>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzBatchTaskSlotCount** mendapatkan jumlah slot tugas Azure Batch untuk pekerjaan Batch.
Tentukan pekerjaan dengan parameter *JobId* atau parameter *Pekerjaan* .
Jumlah slot tugas menyediakan hitungan slot dengan status tugas aktif, berjalan, atau selesai, dan jumlah slot tempat tugas berhasil atau gagal. Slot untuk tugas dalam status persiapan dihitung sebagai berjalan. Jika validationStatus tidak divalidasi, maka layanan Batch belum dapat memeriksa jumlah status terhadap status tugas seperti yang dilaporkan dalam API Daftar Tugas. ValidationStatus mungkin tidak valid jika pekerjaan berisi lebih dari 200.000 tugas.

## EXAMPLES

### Contoh 1: Mendapatkan jumlah tugas berdasarkan ID
```
PS C:\> Get-AzBatchTaskSlotCounts -JobId "Job01" -BatchContext $Context
Active              : 1
Completed           : 0
Failed              : 0
Running             : 1
Succeeded           : 5
ValidationStatus    : Validated
```

Perintah ini mendapatkan jumlah tugas untuk pekerjaan Job01.
Gunakan cmdlet Get-AzBatchAccountKey untuk menetapkan konteks ke variabel $Context.

## PARAMETERS

### -BatchContext
Instans BatchAccountContext untuk digunakan saat berinteraksi dengan layanan Batch.
Jika Anda menggunakan cmdlet Get-AzBatchAccount untuk mendapatkan BatchAccountContext Anda, maka autentikasi Azure Active Directory akan digunakan saat berinteraksi dengan layanan Batch.
Untuk menggunakan autentikasi kunci bersama, gunakan cmdlet Get-AzBatchAccountKeys untuk mendapatkan objek BatchAccountContext dengan kunci aksesnya yang diisi.
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

### -Pekerjaan
Menentukan pekerjaan yang berisi tugas yang didapat cmdlet ini. Untuk mendapatkan objek **PSCloudJob** , gunakan cmdlet Get-AzBatchJob.

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
Id pekerjaan untuk mendapatkan jumlah slot tugas.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

### Microsoft.Azure.Commands.Batch.Models.PSCloudJob

### Microsoft.Azure.Commands.Batch.BatchAccountContext

## OUTPUTS

### Microsoft.Azure.Commands.Batch.Models.PSTaskSlotCounts

## NOTES

## RELATED LINKS
