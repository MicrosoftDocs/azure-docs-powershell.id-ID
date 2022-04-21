---
external help file: Microsoft.Azure.Commands.Batch.dll-Help.xml
Module Name: AzureRM.Batch
ms.assetid: 36EB9CE6-EAC9-471C-97D6-14E882E0F710
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.batch/enable-azurebatchcomputenodescheduling
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/AzureBatch/Commands.Batch/help/Enable-AzureBatchComputeNodeScheduling.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/AzureBatch/Commands.Batch/help/Enable-AzureBatchComputeNodeScheduling.md
ms.openlocfilehash: e00a1a923afdd8a851416e872028a30ce1e04a55
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142734178"
---
# Enable-AzureBatchComputeNodeScheduling

## SYNOPSIS
Mengaktifkan penjadwalan tugas pada simpul komputasi yang ditentukan.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### Id (Default)
```
Enable-AzureBatchComputeNodeScheduling [-PoolId] <String> [-Id] <String> -BatchContext <BatchAccountContext>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### InputObject
```
Enable-AzureBatchComputeNodeScheduling [[-ComputeNode] <PSComputeNode>] -BatchContext <BatchAccountContext>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Enable-AzureBatchComputeNodeScheduling** memungkinkan penjadwalan tugas pada simpul komputasi yang ditentukan.
Simpul komputasi adalah mesin virtual Azure yang didedikasikan untuk beban kerja aplikasi tertentu.

## EXAMPLES

### Contoh 1: Mengaktifkan penjadwalan tugas pada simpul komputasi
```
PS C:\>$Context = Get-AzureRmBatchAccountKeys -AccountName "contosobatchaccount"
PS C:\> Enable-AzureBatchComputeNodeScheduling  -PoolId "myPool" -Id "tvm-1783593343_34-20151117t222514z" -BatchContext $Context
```

Perintah ini memungkinkan penjadwalan tugas di node komputasi tvm-1783593343_34-20151117t222514z.
Untuk melakukan ini, perintah pertama dalam contoh membuat referensi objek yang berisi kunci akun untuk akun batch contosobatchaccount.
Referensi objek ini disimpan dalam variabel bernama $context.
Perintah kedua kemudian menggunakan referensi objek ini dan cmdlet **Enable-AzureBatchComputeNodeScheduling** untuk menyambungkan ke kumpulan myPool dan mengaktifkan penjadwalan tugas di tvm-1783593343_34-20151117t222514z.

### Contoh 2: Mengaktifkan penjadwalan tugas pada node komputasi dalam kumpulan
```
PS C:\>$Context = Get-AzureRmBatchAccountKeys -AccountName "contosobatchaccount"
PS C:\> Get-AzureBatchComputeNode -PoolId "Pool06"  -BatchContext $Context | Enable-AzureBatchComputeNodeScheduling  -BatchContext $Context
```

Perintah ini memungkinkan penjadwalan tugas di semua node komputasi yang ditemukan di pool Pool06.
Untuk melakukan tugas ini, perintah pertama dalam contoh membuat referensi objek yang berisi kunci akun untuk akun batch contosobatchaccount.
Referensi objek ini disimpan dalam variabel bernama $context.
Perintah kedua dalam contoh lalu menggunakan referensi objek ini dan **Get-AzureBatchComputeNode** untuk mengembalikan kumpulan semua node komputasi yang ditemukan di Pool06.
Kumpulan tersebut kemudian disalurkan ke cmdlet **Enable-AzureBatchComputeNodeScheduling** , yang memungkinkan penjadwalan tugas di setiap simpul komputasi dalam koleksi.

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
Menentukan referensi objek ke simpul komputasi tempat penjadwalan tugas diaktifkan.
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
Menentukan ID kumpulan kumpulan yang berisi simpul komputasi tempat penjadwalan tugas diaktifkan.

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

[Disable-AzureBatchComputeNodeScheduling](./Disable-AzureBatchComputeNodeScheduling.md)


