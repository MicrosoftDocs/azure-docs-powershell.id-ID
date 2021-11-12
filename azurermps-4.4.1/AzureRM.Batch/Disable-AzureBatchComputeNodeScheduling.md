---
external help file: Microsoft.Azure.Commands.Batch.dll-Help.xml
Module Name: AzureRM.Batch
ms.assetid: 2DF5FB4D-A5CB-439C-AC6F-DF2130AF33EC
online version: ''
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/AzureBatch/Commands.Batch/help/Disable-AzureBatchComputeNodeScheduling.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/AzureBatch/Commands.Batch/help/Disable-AzureBatchComputeNodeScheduling.md
ms.openlocfilehash: 778347394e9793b95434e1b308bbdb4e28fc0915
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132429049"
---
# Disable-AzureBatchComputeNodeScheduling

## SYNOPSIS
Menonaktifkan penjadwalan tugas pada node perhitungan tertentu.

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
Cmdlet **Disable-AzureBatchComputeNodeScheduling** menonaktifkan penjadwalan tugas pada node perhitungan yang ditentukan.
Node perhitungan adalah mesin virtual Azure yang dikhususkan untuk beban kerja aplikasi tertentu.
Ketika Anda menonaktifkan penjadwalan tugas pada simpul perhitungan, Anda juga akan memiliki opsi untuk menentukan apa yang harus dilakukan tentang pekerjaan saat ini dalam antrean tugas simpul.
**Disable-AzureBatchComputeNodeScheduling** memungkinkan Anda melakukan hal berikut: 

- Akhiri tugas dan letakkan kembali dalam antrean pekerjaan.
Ini memungkinkan tugas tersebut untuk dijadwalkan kembali di node perhitungan lain. 
- Akhiri tugas dan hapus tugas dari antrean pekerjaan.
Tugas yang dihentikan dengan cara ini tidak akan dijadwal ulang. 
- Tunggu hingga semua tugas yang saat ini sedang dijalankan selesai lalu nonaktifkan penjadwalan tugas pada simpul perhitungan. 
- Tunggu hingga semua tugas yang berjalan selesai dan semua periode penyimpanan data kedaluwarsa, lalu nonaktifkan penjadwalan tugas pada simpul perhitungan.

## EXAMPLES

### Contoh 1: Nonaktifkan penjadwalan tugas pada simpul perhitungan
```
PS C:\>$Context = Get-AzureRmBatchAccountKeys -AccountName "contosobatchaccount"
PS C:\> Disable-AzureBatchComputeNodeScheduling -PoolId "myPool" -Id "tvm-1783593343_34-20151117t222514z" -BatchContext $Context
```

Perintah ini menonaktifkan jadwal tugas pada node tvm-1783593343_34-20151117t222514z.
Untuk melakukannya, perintah pertama dalam contoh membuat referensi objek ke tombol akun untuk akun batch contosobatchaccount.
Referensi objek ini disimpan dalam variabel yang bernama $context.

Perintah kedua lalu menggunakan referensi objek ini dan cmdlet **Disable-AzureBatchComputeNodeScheduling** untuk menyambungkan ke myPool pool dan menonaktifkan penjadwalan tugas pada node tvm-1783593343_34-20151117t222514z.

Karena parameter *DisableComputeNodeSchedulingOptions* tidak menyertakan tugas apa pun yang saat ini berjalan di node perhitungan yang akan dikuhkan kembali.

### Contoh 2: Nonaktifkan penjadwalan tugas di semua node perhitungan dalam satu pool
```
PS C:\>$Context = Get-AzureRmBatchAccountKeys -AccountName "contosobatchaccount"
PS C:\> Get-AzureBatchComputeNode -PoolId "Pool06"  -BatchContext $Context | Disable-AzureBatchComputeNodeScheduling -BatchContext $Context
```

Perintah ini menonaktifkan penjadwalan tugas di semua node komputer dalam Pool06 kumpulan.
Untuk menjalankan tugas ini, perintah pertama dalam contoh membuat referensi objek ke tombol akun untuk akun batch contosobatchaccount.
Referensi objek ini disimpan dalam variabel yang bernama $context.

Perintah kedua dalam contoh lalu menggunakan referensi objek ini dan **Get-AzureBatchComputeNode** untuk mengembalikan kumpulan semua node hitung yang ditemukan di Pool06.
Kumpulan itu lalu disambungkan ke cmdlet **Disable-AzureBatchComputeNodeScheduling** untuk menonaktifkan penjadwalan tugas pada setiap node perhitungan dalam koleksi.

Karena parameter *DisableComputeNodeSchedulingOptions* tidak disertakan tugas apa pun yang saat ini berjalan di node perhitungan akan dikukukuhkan kembali.

## PARAMETERS

### -BatchContext
Menentukan contoh **BatchAccountContext** yang digunakan cmdlet untuk berinteraksi dengan layanan Batch.
Untuk mendapatkan objek **BatchAccountContext** yang berisi tombol akses untuk langganan Anda, gunakan cmdlet Get-AzureRmBatchAccountKeys cmdlet.

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
Referensi objek ini dibuat dengan menggunakan cmdlet Get-AzureBatchComputeNode dan menyimpan objek node perhitungan yang dikembalikan dalam variabel.

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

Jika Anda menggunakan parameter *PoolId,* jangan gunakan parameter *ComputeNode* di perintah yang sama.

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

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### BatchAccountContext
Parameter 'BatchContext' menerima nilai tipe 'BatchAccountContext' dari saluran

### PSComputeNode
Parameter 'ComputeNode' menerima nilai tipe 'PSComputeNode' dari saluran

## OUTPUTS

## CATATAN

## RELATED LINKS

[Get-AzureRmBatchAccountKeys](./Get-AzureRmBatchAccountKeys.md)

[Enable-AzureBatchComputeNodeScheduling](./Enable-AzureBatchComputeNodeScheduling.md)


