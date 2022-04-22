---
external help file: Microsoft.Azure.Commands.Batch.dll-Help.xml
Module Name: AzureRM.Batch
ms.assetid: 2DF5FB4D-A5CB-439C-AC6F-DF2130AF33EC
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.batch/disable-azurebatchcomputenodescheduling
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/AzureBatch/Commands.Batch/help/Disable-AzureBatchComputeNodeScheduling.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/AzureBatch/Commands.Batch/help/Disable-AzureBatchComputeNodeScheduling.md
ms.openlocfilehash: 281e8a883474b3cb0f42b22de1bb00ef2f6e7249
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142861336"
---
# Disable-AzureBatchComputeNodeScheduling

## SYNOPSIS
Menonaktifkan penjadwalan tugas pada simpul komputasi yang ditentukan.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### Id (Default)
```
Disable-AzureBatchComputeNodeScheduling [-PoolId] <String> [-Id] <String>
 [-DisableSchedulingOption <DisableComputeNodeSchedulingOption>] -BatchContext <BatchAccountContext>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### InputObject
```
Disable-AzureBatchComputeNodeScheduling [[-ComputeNode] <PSComputeNode>]
 [-DisableSchedulingOption <DisableComputeNodeSchedulingOption>] -BatchContext <BatchAccountContext>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Disable-AzureBatchComputeNodeScheduling** menonaktifkan penjadwalan tugas pada simpul komputasi yang ditentukan.
Simpul komputasi adalah mesin virtual Azure yang didedikasikan untuk beban kerja aplikasi tertentu.
Saat Anda menonaktifkan penjadwalan tugas pada simpul komputasi, Anda juga akan memiliki opsi untuk menentukan apa yang harus dilakukan tentang pekerjaan yang saat ini berada dalam antrean tugas simpul.
**Disable-AzureBatchComputeNodeScheduling** memungkinkan Anda melakukan hal berikut: 
- Hentikan tugas dan letakkan kembali dalam antrean pekerjaan.
Ini memungkinkan tugas tersebut dijadwalkan ulang pada simpul komputasi lain. 
- Hentikan tugas dan hapus tugas dari antrean pekerjaan.
Tugas dihentikan dengan cara ini tidak akan dijadwalkan ulang. 
- Tunggu hingga semua tugas yang sedang dijalankan selesai lalu nonaktifkan penjadwalan tugas pada simpul komputasi. 
- Tunggu hingga semua tugas yang berjalan selesai dan semua periode penyimpanan data kedaluwarsa, lalu nonaktifkan penjadwalan tugas pada simpul komputasi.

## EXAMPLES

### Contoh 1: Menonaktifkan penjadwalan tugas pada simpul komputasi
```
PS C:\>$Context = Get-AzureRmBatchAccountKeys -AccountName "contosobatchaccount"
PS C:\> Disable-AzureBatchComputeNodeScheduling -PoolId "myPool" -Id "tvm-1783593343_34-20151117t222514z" -BatchContext $Context
```

Perintah ini menonaktifkan jadwal tugas pada node komputasi tvm-1783593343_34-20151117t222514z.
Untuk melakukan ini, perintah pertama dalam contoh membuat referensi objek ke kunci akun untuk akun batch contosobatchaccount.
Referensi objek ini disimpan dalam variabel bernama $context.
Perintah kedua kemudian menggunakan referensi objek ini dan cmdlet **Disable-AzureBatchComputeNodeScheduling** untuk menyambungkan ke kumpulan myPool dan menonaktifkan penjadwalan tugas di node tvm-1783593343_34-20151117t222514z.
Karena parameter *DisableComputeNodeSchedulingOptions tidak disertakan* tugas apa pun yang saat ini berjalan pada simpul komputasi akan diantrikan kembali.

### Contoh 2: Menonaktifkan penjadwalan tugas di semua node komputasi dalam kumpulan
```
PS C:\>$Context = Get-AzureRmBatchAccountKeys -AccountName "contosobatchaccount"
PS C:\> Get-AzureBatchComputeNode -PoolId "Pool06"  -BatchContext $Context | Disable-AzureBatchComputeNodeScheduling -BatchContext $Context
```

Perintah ini menonaktifkan penjadwalan tugas di semua simpul komputer dalam kumpulan Pool06.
Untuk melakukan tugas ini, perintah pertama dalam contoh membuat referensi objek ke kunci akun untuk akun batch contosobatchaccount.
Referensi objek ini disimpan dalam variabel bernama $context.
Perintah kedua dalam contoh lalu menggunakan referensi objek ini dan **Get-AzureBatchComputeNode** untuk mengembalikan kumpulan semua node komputasi yang ditemukan di Pool06.
Kumpulan tersebut kemudian disalurkan ke cmdlet **Disable-AzureBatchComputeNodeScheduling** untuk menonaktifkan penjadwalan tugas pada setiap simpul komputasi dalam koleksi.
Karena parameter *DisableComputeNodeSchedulingOptions tidak disertakan* tugas apa pun yang saat ini berjalan pada node komputasi akan diantrikan ulang.

## PARAMETERS

### -BatchContext
Menentukan instans **BatchAccountContext** yang digunakan cmdlet ini untuk berinteraksi dengan layanan Batch.
Jika Anda menggunakan cmdlet Get-AzureRmBatchAccount untuk mendapatkan BatchAccountContext, autentikasi Azure Active Directory akan digunakan saat berinteraksi dengan layanan Batch. Untuk menggunakan autentikasi kunci bersama, gunakan cmdlet Get-AzureRmBatchAccountKeys untuk mendapatkan objek BatchAccountContext dengan tombol akses yang diisi. Ketika menggunakan autentikasi kunci bersama, kunci akses utama digunakan secara default. Untuk mengubah kunci yang akan digunakan, atur properti BatchAccountContext.KeyInUse.

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
Referensi objek ini dibuat dengan menggunakan cmdlet Get-AzureBatchComputeNode dan menyimpan objek node komputasi yang dikembalikan dalam variabel.

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
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DisableSchedulingOption
Menentukan bagaimana cmdlet ini menangani tugas apa pun yang sedang berjalan pada simpul komputer tempat penjadwalan dinonaktifkan.
Nilai yang dapat diterima untuk parameter ini adalah:
- Antrean ulang.
Tugas segera dihentikan dan dikembalikan ke antrean pekerjaan.
Ini memungkinkan tugas untuk dijadwal ulang pada simpul komputasi lain.
Ini adalah nilai default. 
- Mengakhiri.
Tugas segera dihentikan dan dihapus dari antrean pekerjaan.
Tugas ini tidak akan dijadwalkan ulang. 
- Penyelesaian Tugas.
Tugas yang sedang berjalan saat ini akan bisa diselesaikan sebelum penjadwalan tugas dinonaktifkan pada simpul komputasi.
Tidak ada tugas baru yang akan dijadwalkan pada simpul ini. 
- RetainedData.
Tugas yang sedang berjalan saat ini akan bisa diselesaikan dan periode penyimpanan data akan bisa kedaluwarsa sebelum penjadwalan tugas dinonaktifkan pada simpul komputasi.
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
Menentukan ID kumpulan kumpulan yang berisi simpul komputasi tempat penjadwalan tugas dinonaktifkan.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Batch.Models.PSComputeNode
Parameter: ComputeNode (ByValue)

### Microsoft.Azure.Commands.Batch.BatchAccountContext
Parameter: BatchContext (ByValue)

## OUTPUTS

### System.Void

## NOTES

## RELATED LINKS

[Get-AzureRmBatchAccountKeys](./Get-AzureRmBatchAccountKeys.md)

[Enable-AzureBatchComputeNodeScheduling](./Enable-AzureBatchComputeNodeScheduling.md)


