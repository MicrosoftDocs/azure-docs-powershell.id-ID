---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
ms.assetid: CF3548F6-03FE-44D6-AA2C-1015611C657A
online version: ''
schema: 2.0.0
ms.openlocfilehash: a7be848e7806e77e8d720542b037c5bb0dabe933
ms.sourcegitcommit: d28d7d5f6278862d833182868a9dcde2c31e657b
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/25/2022
ms.locfileid: "132415215"
---
# Get-AzureStorSimpleTask

## SYNOPSIS
Mendapatkan status tugas pada perangkat StorSimple.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureStorSimpleTask -InstanceId <String> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureStorSimpleTask** mengambil status tugas yang berjalan secara asinkron pada perangkat Azure StorSimple.

Ketika mengelola perangkat StorSimple, sebagian besar tindakan membuat, membaca, memperbarui, dan menghapus dapat berjalan secara asinkron.
Windows PowerShell mengembalikan **TaskId**.
Gunakan ID untuk mendapatkan status tugas saat ini.

## EXAMPLES

### Contoh 1: Mendapatkan status tugas
```
PS C:\>Get-AzureStorSimpleTask -TaskId "53816d8d-a8b5-4c1d-a177-e59007608d6d"
VERBOSE: ClientRequestId: d9c1e8a7-994f-4698-8b42-064600b45cad_PS
VERBOSE: ClientRequestId: aae17c82-6fd3-435e-a965-1c66b3c955fe_PS


AsyncTaskAggregatedResult : Succeeded
Error                     : Microsoft.WindowsAzure.Management.StorSimple.Models.ErrorDetails
Result                    : Succeeded
Status                    : Completed
TaskId                    : 53816d8d-a8b5-4c1d-a177-e59007608d6d
TaskSteps                 : {}
StatusCode                : OK
RequestId                 : e9174990825750bba69383748f23019c
```

Perintah ini mendapatkan status tugas yang memiliki ID tertentu.
Hasilnya memperlihatkan bahwa tugas tersebut memiliki status selesai dan hasil berhasil.

## PARAMETERS

### -InstanceId
Menentukan ID tugas yang melacak status cmdlet ini.

```yaml
Type: String
Parameter Sets: (All)
Aliases: TaskId

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Profil
Menentukan profil Azure yang akan dibaca cmdlet ini.
Jika Anda tidak menentukan profil, cmdlet ini akan membaca dari profil default lokal.

```yaml
Type: AzureSMProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak ada

## OUTPUTS

### JobStatusInfo
Cmdlet ini mengembalikan objek **TaskStatusInfo** yang berisi bidang berikut ini: 

- **Kesalahan**.
**ErrorDetails**, yang berisi **Kode** dan **Pesan**.
- **TaskId**.
**String**.
ID tugas yang statusnya dikembalikan.
- **Langkah Tugas**.
**IList\<TaskStep\>**.
Setiap **objek TaskStep** berisi **Detail**, **KesalahanKode**, **Pesan**, **Hasil**, dan **Status**.
- **Hasil**.
**TaskResult**, yang berisi hasil keseluruhan tugas.
Nilai yang valid adalah: Gagal, Berhasil, PartialSuccess, Cancelled, dan Invalid.
- **Status**.
**TaskStatus**, berisi status menjalankan tugas secara keseluruhan.
Nilai valid adalah: Inprogress, Invalid, dan Completed.
- **TaskResult**.
**TaskResult**, sebuah nilai dihitung berdasarkan **Hasil** dan **Status**.
Nilai valid adalah: Gagal, Berhasil, InProgress, PartialSuccess, Cancelled, dan Invalid.

## CATATAN

## RELATED LINKS

