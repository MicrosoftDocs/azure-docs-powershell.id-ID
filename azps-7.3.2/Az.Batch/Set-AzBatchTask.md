---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Batch.dll-Help.xml
Module Name: Az.Batch
ms.assetid: 6A6D6C7D-EED7-4AD4-ACE6-BFA64404455E
online version: https://docs.microsoft.com/powershell/module/az.batch/set-azbatchtask
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Batch/Batch/help/Set-AzBatchTask.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Batch/Batch/help/Set-AzBatchTask.md
ms.openlocfilehash: 0757b02080d20b34ebe885a19cd93671e5f13470
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142260277"
---
# Set-AzBatchTask

## SYNOPSIS
Memperbarui properti tugas.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.batch/set-azbatchtask) untuk informasi terbaru.

## SYNTAX

```
Set-AzBatchTask [-Task] <PSCloudTask> -BatchContext <BatchAccountContext>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzBatchTask** memperbarui properti tugas dalam layanan Azure Batch.
Gunakan cmdlet Get-AzBatchTask untuk mendapatkan objek **PSCloudTask** .
Ubah properti objek tersebut, lalu gunakan cmdlet saat ini untuk melakukan perubahan Pada layanan Batch.

## EXAMPLES

### Contoh 1: Memperbarui tugas
```powershell
$Task = Get-AzBatchTask -JobId "Job16" -Id "Task22" -BatchContext $Context
$Constraints = New-Object Microsoft.Azure.Commands.Batch.Models.PSTaskConstraints -ArgumentList @([TimeSpan}::FromDays(5), [TimeSpan]::FromDays(2), 3)
$Task.Constraints = $Constraints
Set-AzBatchTask -Task $Task -BatchContext $Context
```

Perintah pertama mendapatkan tugas dengan menggunakan **Get-AzBatchTask**, lalu menyimpannya dalam variabel $Task.
Dua perintah berikutnya mengubah batasan tugas dalam $Task.
Perintah akhir memperbarui layanan Batch agar sesuai dengan objek lokal di $Task.

## PARAMETERS

### -BatchContext
Menentukan instans **BatchAccountContext** yang digunakan cmdlet ini untuk berinteraksi dengan layanan Batch.
Jika Anda menggunakan cmdlet Get-AzBatchAccount untuk mendapatkan BatchAccountContext, autentikasi Azure Active Directory akan digunakan saat berinteraksi dengan layanan Batch. Untuk menggunakan autentikasi kunci bersama, gunakan cmdlet Get-AzBatchAccountKey untuk mendapatkan objek BatchAccountContext dengan tombol akses yang diisi. Ketika menggunakan autentikasi kunci bersama, kunci akses utama digunakan secara default. Untuk mengubah kunci yang akan digunakan, atur properti BatchAccountContext.KeyInUse.

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

### -Tugas
Menentukan **PSCloudTask** tempat cmdlet ini memperbarui layanan Batch.

```yaml
Type: Microsoft.Azure.Commands.Batch.Models.PSCloudTask
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Batch.Models.PSCloudTask

### Microsoft.Azure.Commands.Batch.BatchAccountContext

## OUTPUTS

### System.Void

## CATATAN

## RELATED LINKS

[Get-AzBatchTask](./Get-AzBatchTask.md)

[Get-AzBatchAccountKey](./Get-AzBatchAccountKey.md)

[New-AzBatchTask](./New-AzBatchTask.md)

[Hapus-AzBatchTask](./Remove-AzBatchTask.md)

[Stop-AzBatchTask](./Stop-AzBatchTask.md)

[Cmdlet Azure Batch](/powershell/module/Az.Batch/)
