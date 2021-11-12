---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
ms.assetid: CF3548F6-03FE-44D6-AA2C-1015611C657A
online version: ''
schema: 2.0.0
ms.openlocfilehash: 5e77d6b1600d1e323c668e7c5e49dbf6365ae10e2b6991481b5e8eaf5c870f49
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### Tidak ada

## OUTPUTS

### JobStatusInfo
Cmdlet ini mengembalikan objek **TaskStatusInfo** yang berisi bidang berikut ini: 

- **Kesalahan**.
**ErrorDetails,** yang berisi **Kode** dan **Pesan.**
- **TaskId**.
**String**.
ID tugas yang statusnya dikembalikan.
- **Langkah Tugas**.
**IList \<TaskStep\>**.
Setiap **objek TaskStep** berisi **Detail**, **ErrorCode**, **Pesan**, **Hasil**, dan **Status**.
- **Hasil**.
**TaskResult,** yang berisi hasil keseluruhan tugas.
Nilai yang valid adalah: Gagal, Berhasil, PartialSuccess, Cancelled, dan Invalid.
- **Status**.
**TaskStatus,** yang berisi status menjalankan tugas secara keseluruhan.
Nilai valid adalah: Inprogress, Invalid, dan Completed.
- **Hasil TaskResult**.
**TaskResult,** nilai yang dihitung berdasarkan **Hasil** dan **Status.**
Nilai valid adalah: Gagal, Berhasil, InProgress, PartialSuccess, Cancelled, dan Invalid.

## CATATAN

## RELATED LINKS

