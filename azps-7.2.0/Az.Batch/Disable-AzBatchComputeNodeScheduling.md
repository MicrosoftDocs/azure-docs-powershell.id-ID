---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Batch.dll-Help.xml
Module Name: Az.Batch
ms.assetid: 2DF5FB4D-A5CB-439C-AC6F-DF2130AF33EC
online version: https://docs.microsoft.com/powershell/module/az.batch/disable-azbatchcomputenodescheduling
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Batch/Batch/help/Disable-AzBatchComputeNodeScheduling.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Batch/Batch/help/Disable-AzBatchComputeNodeScheduling.md
ms.openlocfilehash: f566fbece728eb6695332e501abfde1d80c18d6f
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138285868"
---
# Disable-AzBatchComputeNodeScheduling

## SYNOPSIS
Menonaktifkan penjadwalan tugas pada node perhitungan tertentu.

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
Cmdlet **Disable-AzBatchComputeNodeScheduling** menonaktifkan penjadwalan tugas pada node perhitungan yang ditentukan.
Node perhitungan adalah mesin virtual Azure yang dikhususkan untuk beban kerja aplikasi tertentu.
Ketika Anda menonaktifkan penjadwalan tugas pada simpul perhitungan, Anda juga akan memiliki opsi untuk menentukan apa yang harus dilakukan tentang pekerjaan saat ini dalam antrean tugas simpul.
**Disable-AzBatchComputeNodeScheduling** memungkinkan Anda melakukan hal berikut: 
- Akhiri tugas dan letakkan kembali dalam antrean pekerjaan.
Ini memungkinkan tugas tersebut untuk dijadwalkan kembali di node perhitungan lain. 
- Akhiri tugas dan hapus tugas dari antrean pekerjaan.
Tugas yang dihentikan dengan cara ini tidak akan dijadwal ulang. 
- Tunggu hingga semua tugas yang saat ini sedang dijalankan selesai lalu nonaktifkan penjadwalan tugas pada simpul perhitungan. 
- Tunggu hingga semua tugas yang berjalan selesai dan semua periode penyimpanan data kedaluwarsa, lalu nonaktifkan penjadwalan tugas pada simpul perhitungan.

## EXAMPLES

### Contoh 1: Nonaktifkan penjadwalan tugas pada simpul perhitungan
```
PS C:\>$Context = Get-AzBatchAccountKey -AccountName "contosobatchaccount"
PS C:\> Disable-AzBatchComputeNodeScheduling -PoolId "myPool" -Id "tvm-1783593343_34-20151117t222514z" -BatchContext $Context
```

Perintah ini menonaktifkan jadwal tugas pada node tvm-1783593343_34-20151117t222514z.
Untuk melakukannya, perintah pertama dalam contoh membuat referensi objek ke tombol akun untuk akun batch contosobatchaccount.
Referensi objek ini disimpan dalam variabel yang bernama $context.
Perintah kedua lalu menggunakan referensi objek ini dan cmdlet **Disable-AzBatchComputeNodeScheduling** untuk menyambungkan ke myPool pool dan menonaktifkan penjadwalan tugas di node tvm-1783593343_34-20151117t222514z.
Karena parameter *DisableComputeNodeSchedulingOptions* tidak menyertakan tugas apa pun yang saat ini berjalan di node perhitungan yang akan dikuhkan kembali.

### Contoh 2: Nonaktifkan penjadwalan tugas di semua node perhitungan dalam satu pool
```
PS C:\>$Context = Get-AzBatchAccountKey -AccountName "contosobatchaccount"
PS C:\> Get-AzBatchComputeNode -PoolId "Pool06"  -BatchContext $Context | Disable-AzBatchComputeNodeScheduling -BatchContext $Context
```

Perintah ini menonaktifkan penjadwalan tugas di semua node komputer dalam pool Pool06 kumpulan.
Untuk menjalankan tugas ini, perintah pertama dalam contoh membuat referensi objek ke tombol akun untuk akun batch contosobatchaccount.
Referensi objek ini disimpan dalam variabel yang bernama $context.
Perintah kedua dalam contoh lalu menggunakan referensi objek ini dan **Get-AzBatchComputeNode** untuk mengembalikan kumpulan semua node hitung yang ditemukan di Pool06.
Kumpulan itu lalu dibingkas ke lalu cmdlet **Disable-AzBatchComputeNodeScheduling** untuk menonaktifkan penjadwalan tugas pada setiap node perhitungan dalam koleksi.
Karena parameter *DisableComputeNodeSchedulingOptions* tidak disertakan tugas apa pun yang saat ini berjalan di node perhitungan akan dikukukuhkan kembali.

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
Menentukan referensi objek ke node hitung tempat penjadwalan tugas dinonaktifkan.
Referensi objek ini dibuat dengan menggunakan cmdlet Get-AzBatchComputeNode dan menyimpan objek node perhitungan yang dikembalikan dalam variabel.

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

### -DisableSchedulingOption
Menentukan bagaimana cmdlet ini berhubungan dengan tugas apa pun yang saat ini berjalan pada node komputer tempat penjadwalan sedang dinonaktifkan.
Nilai yang dapat diterima untuk parameter ini adalah:
- Requeue.
Tugas dihentikan dengan segera dan kembali ke antrean pekerjaan.
Ini memungkinkan tugas untuk dijadwalkan kembali di node perhitungan lain.
Ini adalah nilai default. 
- Hentikan.
Tugas dihentikan secara langsung dan dihapus dari antrean pekerjaan.
Tugas ini tidak akan dijadwal ulang. 
- TaskCompletion.
Tugas yang saat ini sedang berjalan akan dapat diselesaikan sebelum penjadwalan tugas dinonaktifkan pada node perhitungan.
Tidak ada tugas baru yang akan dijadwalkan pada simpul ini. 
- RetainedData.
Tugas yang saat ini berjalan dapat selesai dan periode penyimpanan data dapat kedaluwarsa sebelum penjadwalan tugas dinonaktifkan pada node perhitungan.
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
Menentukan ID node perhitungan tempat penjadwalan tugas dinonaktifkan.

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
Menentukan ID kumpulan kumpulan yang berisi node perhitungan tempat penjadwalan tugas dinonaktifkan.
Jika Anda menggunakan parameter *PoolId* , jangan gunakan parameter *ComputeNode* di perintah yang sama.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Batch.Models.PSComputeNode

### Microsoft.Azure.Commands.Batch.BatchAccountContext

## OUTPUTS

### System.Void

## CATATAN

## RELATED LINKS

[Get-AzBatchAccountKey](./Get-AzBatchAccountKey.md)

[Enable-AzBatchComputeNodeScheduling](./Enable-AzBatchComputeNodeScheduling.md)


