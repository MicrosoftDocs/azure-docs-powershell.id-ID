---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Batch.dll-Help.xml
Module Name: Az.Batch
ms.assetid: 87E7FA51-427E-4DB8-A6A2-D8638FD3DB8B
online version: https://docs.microsoft.com/powershell/module/az.batch/new-azbatchjobschedule
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Batch/Batch/help/New-AzBatchJobSchedule.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Batch/Batch/help/New-AzBatchJobSchedule.md
ms.openlocfilehash: 89f88e82f1886fd28f3fc053a44e2e0b9193ea78
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144694299"
---
# New-AzBatchJobSchedule

## SYNOPSIS
Membuat jadwal pekerjaan di layanan Batch.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.batch/new-azbatchjobschedule) untuk informasi terbaru.

## SYNTAX

```
New-AzBatchJobSchedule [-Id] <String> [-DisplayName <String>] -Schedule <PSSchedule>
 -JobSpecification <PSJobSpecification> [-Metadata <IDictionary>] -BatchContext <BatchAccountContext>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzBatchJobSchedule** membuat jadwal pekerjaan di layanan Azure Batch.
Parameter *BatchAccountContext* menentukan akun tempat cmdlet ini membuat jadwal.

## EXAMPLES

### Contoh 1: Membuat jadwal pekerjaan
```powershell
$Schedule = New-Object -TypeName "Microsoft.Azure.Commands.Batch.Models.PSSchedule"
$Schedule.RecurrenceInterval = [TimeSpan]::FromDays(1)
$JobSpecification = New-Object -TypeName "Microsoft.Azure.Commands.Batch.Models.PSJobSpecification"
$JobSpecification.PoolInformation = New-Object -TypeName "Microsoft.Azure.Commands.Batch.Models.PSPoolInformation"
$JobSpecification.PoolInformation.PoolId = "ContosoPool06"
New-AzBatchJobSchedule -Id "JobSchedule17" -Schedule $Schedule -JobSpecification $JobSpecification -BatchContext $Context
```

Contoh ini membuat jadwal pekerjaan.
Lima perintah pertama membuat dan memodifikasi objek **PSSchedule**, **PSJobSpecification**, dan **PSPoolInformation** .
Perintah menggunakan cmdlet New-Object dan sintaks Azure PowerShell standar.
Perintah menyimpan objek ini dalam variabel $Schedule dan $JobSpecification.
Perintah akhir membuat jadwal pekerjaan yang memiliki ID JobSchedule17.
Jadwal ini membuat pekerjaan dengan interval pengulangan satu hari.
Pekerjaan berjalan pada kumpulan yang memiliki ID ContosoPool06, seperti yang ditentukan dalam perintah kelima.
Gunakan cmdlet **Get-AzBatchAccountKey** untuk menetapkan konteks ke variabel $Context.

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

### -DisplayName
Menentukan nama tampilan untuk jadwal pekerjaan.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
Menentukan ID jadwal pekerjaan yang dibuat cmdlet ini.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -JobSpecification
Menentukan detail pekerjaan yang disertakan cmdlet ini dalam jadwal pekerjaan.

```yaml
Type: Microsoft.Azure.Commands.Batch.Models.PSJobSpecification
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Metadata
Menentukan metadata, sebagai pasangan kunci/nilai, untuk ditambahkan ke jadwal pekerjaan.
Kuncinya adalah nama metadata.
Nilainya adalah nilai metadata.

```yaml
Type: System.Collections.IDictionary
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Jadwal
Menentukan jadwal yang menentukan kapan harus membuat pekerjaan.

```yaml
Type: Microsoft.Azure.Commands.Batch.Models.PSSchedule
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

### Microsoft.Azure.Commands.Batch.BatchAccountContext

## OUTPUTS

### System.Void

## NOTES

## RELATED LINKS

[Disable-AzBatchJobSchedule](./Disable-AzBatchJobSchedule.md)

[Enable-AzBatchJobSchedule](./Enable-AzBatchJobSchedule.md)

[Get-AzBatchAccountKey](./Get-AzBatchAccountKey.md)

[Get-AzBatchJobSchedule](./Get-AzBatchJobSchedule.md)

[Remove-AzBatchJobSchedule](./Remove-AzBatchJobSchedule.md)

[Stop-AzBatchJobSchedule](./Stop-AzBatchJobSchedule.md)

[Cmdlet Azure Batch](/powershell/module/Az.Batch/)
