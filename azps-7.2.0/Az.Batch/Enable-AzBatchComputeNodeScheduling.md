---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Batch.dll-Help.xml
Module Name: Az.Batch
ms.assetid: 36EB9CE6-EAC9-471C-97D6-14E882E0F710
online version: https://docs.microsoft.com/powershell/module/az.batch/enable-azbatchcomputenodescheduling
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Batch/Batch/help/Enable-AzBatchComputeNodeScheduling.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Batch/Batch/help/Enable-AzBatchComputeNodeScheduling.md
ms.openlocfilehash: 0a779eed283bc26eb24937c92c416b9c8d5cdd35
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140241145"
---
# Enable-AzBatchComputeNodeScheduling

## SYNOPSIS
Memungkinkan penjadwalan tugas pada node perhitungan tertentu.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.batch/enable-azbatchcomputenodescheduling) untuk informasi terkini.

## SYNTAX

### Id (Default)
```
Enable-AzBatchComputeNodeScheduling [-PoolId] <String> [-Id] <String> -BatchContext <BatchAccountContext>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### InputObject
```
Enable-AzBatchComputeNodeScheduling [[-ComputeNode] <PSComputeNode>] -BatchContext <BatchAccountContext>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Enable-AzBatchComputeNodeScheduling** mengaktifkan penjadwalan tugas pada node perhitungan yang ditentukan.
Node perhitungan adalah mesin virtual Azure yang dikhususkan untuk beban kerja aplikasi tertentu.

## EXAMPLES

### Contoh 1: Mengaktifkan penjadwalan tugas pada simpul perhitungan
```
PS C:\>$Context = Get-AzBatchAccountKey -AccountName "contosobatchaccount"
PS C:\> Enable-AzBatchComputeNodeScheduling  -PoolId "myPool" -Id "tvm-1783593343_34-20151117t222514z" -BatchContext $Context
```

Perintah ini mengaktifkan penjadwalan tugas pada node tvm-1783593343_34-20151117t222514z.
Untuk melakukannya, perintah pertama dalam contoh membuat referensi objek yang berisi tombol akun untuk akun batch contosobatchaccount.
Referensi objek ini disimpan dalam variabel yang bernama $context.
Perintah kedua lalu menggunakan referensi objek ini dan cmdlet **Enable-AzBatchComputeNodeScheduling** untuk menyambungkan ke myPool pool dan mengaktifkan penjadwalan tugas di tvm-1783593343_34-20151117t222514z.

### Contoh 2: Mengaktifkan penjadwalan tugas pada node perhitungan dalam satu pool
```
PS C:\>$Context = Get-AzBatchAccountKey -AccountName "contosobatchaccount"
PS C:\> Get-AzBatchComputeNode -PoolId "Pool06"  -BatchContext $Context | Enable-AzBatchComputeNodeScheduling  -BatchContext $Context
```

Perintah ini mengaktifkan penjadwalan tugas di semua node perhitungan yang ditemukan dalam pool Pool06.
Untuk menjalankan tugas ini, perintah pertama dalam contoh membuat referensi objek yang berisi tombol akun untuk akun batch contosobatchaccount.
Referensi objek ini disimpan dalam variabel yang bernama $context.
Perintah kedua dalam contoh lalu menggunakan referensi objek ini dan **Get-AzBatchComputeNode** untuk mengembalikan kumpulan semua node hitung yang ditemukan di Pool06.
Kumpulan itu lalu dibingkas ke cmdlet **Enable-AzBatchComputeNodeScheduling** , yang memungkinkan penjadwalan tugas pada setiap node perhitungan dalam koleksi.

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
Menentukan referensi objek ke simpul perhitungan tempat penjadwalan tugas diaktifkan.
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

### -Id
Menentukan ID node hitung tempat penjadwalan tugas diaktifkan.

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
Menentukan ID kumpulan kumpulan yang berisi node perhitungan tempat penjadwalan tugas diaktifkan.

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

[Disable-AzBatchComputeNodeScheduling](./Disable-AzBatchComputeNodeScheduling.md)


