---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Batch.dll-Help.xml
Module Name: Az.Batch
ms.assetid: 2DF5FB4D-A5CB-439C-AC6F-DF2130AF33EC
online version: https://docs.microsoft.com/powershell/module/az.batch/disable-azbatchcomputenodescheduling
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Batch/Batch/help/Disable-AzBatchComputeNodeScheduling.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Batch/Batch/help/Disable-AzBatchComputeNodeScheduling.md
ms.openlocfilehash: a9acbe569d18195c55167ea35fd307180e03da6f
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144185018"
---
# Disable-AzBatchComputeNodeScheduling

## SYNOPSIS
Menonaktifkan penjadwalan tugas pada simpul komputasi yang ditentukan.

## SYNTAX

### Id (Default)
```
Disable-AzBatchComputeNodeScheduling [-PoolId] <String> [-Id] <String>
 [-DisableSchedulingOption <DisableComputeNodeSchedulingOption>] -BatchContext <BatchAccountContext>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### InputObject
```
Disable-AzBatchComputeNodeScheduling [[-ComputeNode] <PSComputeNode>]
 [-DisableSchedulingOption <DisableComputeNodeSchedulingOption>] -BatchContext <BatchAccountContext>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Disable-AzBatchComputeNodeScheduling** menonaktifkan penjadwalan tugas pada simpul komputasi yang ditentukan.
Simpul komputasi adalah komputer virtual Azure yang didedikasikan untuk beban kerja aplikasi tertentu.
Ketika Anda menonaktifkan penjadwalan tugas pada simpul komputasi, Anda juga akan memiliki opsi untuk menentukan apa yang harus dilakukan tentang pekerjaan yang saat ini berada dalam antrean tugas simpul.
**Disable-AzBatchComputeNodeScheduling** memungkinkan Anda melakukan hal berikut: 
- Hentikan tugas dan letakkan kembali dalam antrean pekerjaan.
Ini memungkinkan tugas-tugas tersebut dijadwalkan ulang pada simpul komputasi lain. 
- Hentikan tugas dan hapus dari antrean pekerjaan.
Tugas yang dihentikan dengan cara ini tidak akan dijadwalkan ulang. 
- Tunggu hingga semua tugas yang sedang dijalankan selesai lalu nonaktifkan penjadwalan tugas pada simpul komputasi. 
- Tunggu hingga semua tugas yang sedang berjalan selesai dan semua periode retensi data kedaluwarsa, lalu nonaktifkan penjadwalan tugas pada simpul komputasi.

## EXAMPLES

### Contoh 1: Menonaktifkan penjadwalan tugas pada simpul komputasi
```powershell
$Context = Get-AzBatchAccountKey -AccountName "contosobatchaccount"
Disable-AzBatchComputeNodeScheduling -PoolId "myPool" -Id "tvm-1783593343_34-20151117t222514z" -BatchContext $Context
```

Perintah ini menonaktifkan jadwal tugas pada simpul komputasi tvm-1783593343_34-20151117t222514z.
Untuk melakukan ini, perintah pertama dalam contoh membuat referensi objek ke kunci akun untuk akun batch contosobatchaccount.
Referensi objek ini disimpan dalam variabel bernama $context.
Perintah kedua kemudian menggunakan referensi objek ini dan cmdlet **Disable-AzBatchComputeNodeScheduling** untuk terhubung ke kumpulan myPool dan menonaktifkan penjadwalan tugas pada simpul tvm-1783593343_34-20151117t222514z.
Karena parameter *DisableComputeNodeSchedulingOptions* tidak menyertakan tugas apa pun yang saat ini berjalan pada simpul komputasi akan diantrekan kembali.

### Contoh 2: Menonaktifkan penjadwalan tugas pada semua simpul komputasi dalam kumpulan
```powershell
$Context = Get-AzBatchAccountKey -AccountName "contosobatchaccount"
Get-AzBatchComputeNode -PoolId "Pool06"  -BatchContext $Context | Disable-AzBatchComputeNodeScheduling -BatchContext $Context
```

Perintah ini menonaktifkan penjadwalan tugas pada semua simpul komputer di kumpulan batch Pool06.
Untuk melakukan tugas ini, perintah pertama dalam contoh membuat referensi objek ke kunci akun untuk akun batch contosobatchaccount.
Referensi objek ini disimpan dalam variabel bernama $context.
Perintah kedua dalam contoh kemudian menggunakan referensi objek ini dan **Get-AzBatchComputeNode** untuk mengembalikan koleksi semua simpul komputasi yang ditemukan di Pool06.
Koleksi tersebut kemudian disalurkan ke cmdlet **Disable-AzBatchComputeNodeScheduling** untuk menonaktifkan penjadwalan tugas pada setiap simpul komputasi dalam koleksi.
Karena parameter *DisableComputeNodeSchedulingOptions* tidak menyertakan tugas apa pun yang saat ini berjalan pada simpul komputasi akan diantrekan kembali.

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
Menentukan referensi objek ke simpul komputasi tempat penjadwalan tugas dinonaktifkan.
Referensi objek ini dibuat dengan menggunakan cmdlet Get-AzBatchComputeNode dan menyimpan objek simpul komputasi yang dikembalikan dalam variabel.

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

### -DisableSchedulingOption
Menentukan bagaimana cmdlet ini menangani tugas apa pun yang saat ini berjalan pada simpul komputer tempat penjadwalan dinonaktifkan.
Nilai yang dapat diterima untuk parameter ini adalah:
- Antrean ulang.
Tugas segera dihentikan dan dikembalikan ke antrean pekerjaan.
Ini memungkinkan tugas dijadwalkan ulang pada simpul komputasi lain.
Ini adalah nilai default. 
- Mengakhiri.
Tugas segera dihentikan dan dihapus dari antrean pekerjaan.
Tugas-tugas ini tidak akan dijadwalkan ulang. 
- TaskCompletion.
Tugas yang sedang berjalan akan dapat diselesaikan sebelum penjadwalan tugas dinonaktifkan pada simpul komputasi.
Tidak ada tugas baru yang akan dijadwalkan pada simpul ini. 
- RetainedData.
Tugas yang sedang berjalan saat ini akan dapat diselesaikan dan periode retensi data akan dapat kedaluwarsa sebelum penjadwalan tugas dinonaktifkan pada simpul komputasi.
Tidak ada tugas baru yang akan dijadwalkan pada simpul ini.

```yaml
Type: System.Nullable`1[Microsoft.Azure.Batch.Common.DisableComputeNodeSchedulingOption]
Parameter Sets: (All)
Aliases:
Accepted values: Requeue, Terminate, TaskCompletion

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
Menentukan ID simpul komputasi tempat penjadwalan tugas dinonaktifkan.

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
Menentukan ID kumpulan batch yang berisi simpul komputasi tempat penjadwalan tugas dinonaktifkan.
Jika Anda menggunakan parameter *PoolId* , jangan gunakan parameter *ComputeNode* dalam perintah yang sama.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.Commands.Batch.Models.PSComputeNode

### Microsoft.Azure.Commands.Batch.BatchAccountContext

## OUTPUTS

### System.Void

## NOTES

## RELATED LINKS

[Get-AzBatchAccountKey](./Get-AzBatchAccountKey.md)

[Enable-AzBatchComputeNodeScheduling](./Enable-AzBatchComputeNodeScheduling.md)


