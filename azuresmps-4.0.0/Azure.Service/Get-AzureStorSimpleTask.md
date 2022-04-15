---
external help file: Microsoft.WindowsAzure.Commands.StorSimple.dll-Help.xml
ms.assetid: CF3548F6-03FE-44D6-AA2C-1015611C657A
online version: ''
schema: 2.0.0
ms.openlocfilehash: a7be848e7806e77e8d720542b037c5bb0dabe933
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142278664"
---
# Get-AzureStorSimpleTask

## SYNOPSIS
Mendapatkan status tugas di perangkat StorSimple.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureStorSimpleTask -InstanceId <String> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzureStorSimpleTask** mengambil status tugas yang berjalan secara asinkron pada perangkat Azure StorSimple.

Saat Anda mengelola perangkat StorSimple, sebagian besar tindakan membuat, membaca, memperbarui, dan menghapus dapat berjalan secara asinkron.
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

Perintah ini mendapatkan status tugas yang memiliki ID yang ditentukan.
Hasilnya menunjukkan bahwa tugas memiliki status selesai dan hasil dari keberhasilan.

## PARAMETERS

### -InstanceId
Menentukan ID tugas yang statusnya dilacak cmdlet ini.

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
Menentukan profil Azure tempat cmdlet ini dibaca.
Jika Anda tidak menentukan profil, cmdlet ini akan dibaca dari profil default lokal.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### JobStatusInfo
Cmdlet ini mengembalikan objek **TaskStatusInfo** yang berisi bidang berikut: 

- **Kesalahan**.
**ErrorDetails**, yang berisi **Kode** dan **Pesan**.
- **TaskId**.
**String**.
ID tugas yang dikembalikan statusnya.
- **TaskSteps**.
**IList\<TaskStep\>**.
Setiap objek **TaskStep** berisi **Detail**, **Kode Kesalahan**, **Pesan**, **Hasil**, dan **Status**.
- **Hasil.**
**TaskResult**, yang berisi keseluruhan hasil tugas.
Nilai yang valid adalah: Gagal, Berhasil, PartialSuccess, Cancelled, dan Tidak Valid.
- **Status**.
**TaskStatus**, yang berisi keseluruhan status tugas yang berjalan.
Nilai yang valid adalah: Inprogress, Invalid, dan Completed.
- **TaskResult**.
**TaskResult**, nilai yang dihitung berdasarkan **Hasil** dan **Status**.
Nilai yang valid adalah: Gagal, Berhasil, InProgress, PartialSuccess, Cancelled, dan Invalid.

## CATATAN

## RELATED LINKS

