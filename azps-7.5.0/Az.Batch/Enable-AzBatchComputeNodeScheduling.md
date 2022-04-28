---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Batch.dll-Help.xml
Module Name: Az.Batch
ms.assetid: 36EB9CE6-EAC9-471C-97D6-14E882E0F710
online version: https://docs.microsoft.com/powershell/module/az.batch/enable-azbatchcomputenodescheduling
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Batch/Batch/help/Enable-AzBatchComputeNodeScheduling.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Batch/Batch/help/Enable-AzBatchComputeNodeScheduling.md
ms.openlocfilehash: 3b96b59f7ac9dd594397ab1092833460fc15402d
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144205643"
---
# Enable-AzBatchComputeNodeScheduling

## SYNOPSIS
Mengaktifkan penjadwalan tugas pada simpul komputasi yang ditentukan.

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
Cmdlet **Enable-AzBatchComputeNodeScheduling** memungkinkan penjadwalan tugas pada simpul komputasi yang ditentukan.
Simpul komputasi adalah komputer virtual Azure yang didedikasikan untuk beban kerja aplikasi tertentu.

## EXAMPLES

### Contoh 1: Mengaktifkan penjadwalan tugas pada simpul komputasi
```powershell
$Context = Get-AzBatchAccountKey -AccountName "contosobatchaccount"
Enable-AzBatchComputeNodeScheduling  -PoolId "myPool" -Id "tvm-1783593343_34-20151117t222514z" -BatchContext $Context
```

Perintah ini memungkinkan penjadwalan tugas pada simpul komputasi tvm-1783593343_34-20151117t222514z.
Untuk melakukan ini, perintah pertama dalam contoh membuat referensi objek yang berisi kunci akun untuk akun batch contosobatchaccount.
Referensi objek ini disimpan dalam variabel bernama $context.
Perintah kedua kemudian menggunakan referensi objek ini dan cmdlet **Enable-AzBatchComputeNodeScheduling** untuk terhubung ke kumpulan myPool dan mengaktifkan penjadwalan tugas di tvm-1783593343_34-20151117t22514z.

### Contoh 2: Mengaktifkan penjadwalan tugas pada simpul komputasi dalam kumpulan
```powershell
$Context = Get-AzBatchAccountKey -AccountName "contosobatchaccount"
Get-AzBatchComputeNode -PoolId "Pool06"  -BatchContext $Context | Enable-AzBatchComputeNodeScheduling  -BatchContext $Context
```

Perintah ini memungkinkan penjadwalan tugas pada semua simpul komputasi yang ditemukan di kumpulan Pool06.
Untuk melakukan tugas ini, perintah pertama dalam contoh membuat referensi objek yang berisi kunci akun untuk akun batch contosobatchaccount.
Referensi objek ini disimpan dalam variabel bernama $context.
Perintah kedua dalam contoh kemudian menggunakan referensi objek ini dan **Get-AzBatchComputeNode** untuk mengembalikan koleksi semua simpul komputasi yang ditemukan di Pool06.
Koleksi tersebut kemudian disalurkan ke cmdlet **Enable-AzBatchComputeNodeScheduling** , yang memungkinkan penjadwalan tugas pada setiap simpul komputasi dalam koleksi.

## PARAMETERS

### -BatchContext
Menentukan instans **BatchAccountContext** yang digunakan cmdlet ini untuk berinteraksi dengan layanan Batch.
Jika Anda menggunakan cmdlet Get-AzBatchAccount untuk mendapatkan BatchAccountContext Anda, maka autentikasi Azure Active Directory akan digunakan saat berinteraksi dengan layanan Batch. Untuk menggunakan autentikasi kunci bersama, gunakan cmdlet Get-AzBatchAccountKey untuk mendapatkan objek BatchAccountContext dengan kunci aksesnya yang diisi. Saat menggunakan autentikasi kunci bersama, kunci akses utama digunakan secara default. Untuk mengubah kunci yang akan digunakan, atur properti BatchAccountContext.KeyInUse.

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
Menentukan referensi objek ke simpul komputasi tempat penjadwalan tugas diaktifkan.
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

### -Id
Menentukan ID simpul komputasi tempat penjadwalan tugas diaktifkan.

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
Menentukan ID kumpulan batch yang berisi simpul komputasi tempat penjadwalan tugas diaktifkan.

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

[Disable-AzBatchComputeNodeScheduling](./Disable-AzBatchComputeNodeScheduling.md)


