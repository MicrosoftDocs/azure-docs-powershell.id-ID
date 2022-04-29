---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Batch.dll-Help.xml
Module Name: Az.Batch
ms.assetid: 1EA57372-6FA5-45C9-94A1-50D53830FC10
online version: https://docs.microsoft.com/powershell/module/az.batch/stop-azbatchtask
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Batch/Batch/help/Stop-AzBatchTask.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Batch/Batch/help/Stop-AzBatchTask.md
ms.openlocfilehash: 456184fe215febffa1d3e2e9a46f170d41c0d0a5
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144237209"
---
# Stop-AzBatchTask

## SYNOPSIS
Menghentikan tugas Batch.

## SYNTAX

### Id
```
Stop-AzBatchTask [-JobId] <String> [-Id] <String> -BatchContext <BatchAccountContext>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### InputObject
```
Stop-AzBatchTask [-Task] <PSCloudTask> -BatchContext <BatchAccountContext>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Stop-AzBatchTask** menghentikan tugas Azure Batch.

## EXAMPLES

### Contoh 1: Menghapus tugas Batch berdasarkan ID
```powershell
Stop-AzBatchTask -JobId "Job-000001" -Id "Task23" -BatchContext $Context
```

Perintah ini menghentikan tugas yang memiliki TUGAS ID23 di bawah pekerjaan yang memiliki ID Job-000001.
Perintah meminta konfirmasi kepada Anda.
Gunakan cmdlet Get-AzBatchAccountKey untuk menetapkan konteks ke variabel $Context.

### Contoh 2: Menghentikan tugas Batch dengan menggunakan alur
```powershell
Get-AzBatchTask -JobId "Job-000001" -Id "Task26" -BatchContext $Context | Stop-AzBatchTask -BatchContext $Context
```

Perintah ini mendapatkan tugas Batch yang memiliki TUGAS ID26 dalam pekerjaan yang memiliki ID Job-000001 dengan menggunakan cmdlet Get-AzBatchTask.
Perintah meneruskan tugas tersebut ke cmdlet saat ini dengan menggunakan operator alur.
Perintah menghentikan tugas tersebut.

## PARAMETERS

### -BatchContext
Menentukan instans **BatchAccountContext** yang digunakan cmdlet ini untuk berinteraksi dengan layanan Batch.
Jika Anda menggunakan cmdlet Get-AzBatchAccount untuk mendapatkan BatchAccountContext Anda, maka autentikasi Azure Active Directory akan digunakan saat berinteraksi dengan layanan Batch. Untuk menggunakan autentikasi kunci bersama sebagai gantinya, gunakan cmdlet Get-AzBatchAccountKey untuk mendapatkan objek BatchAccountContext dengan kunci aksesnya yang diisi. Saat menggunakan autentikasi kunci bersama, kunci akses utama digunakan secara default. Untuk mengubah kunci yang akan digunakan, atur properti BatchAccountContext.KeyInUse.

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

### -Id
Menentukan ID tugas yang dihentikan cmdlet ini.

```yaml
Type: System.String
Parameter Sets: Id
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -JobId
Menentukan ID pekerjaan yang berisi tugas.

```yaml
Type: System.String
Parameter Sets: Id
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tugas
Menentukan tugas yang dihentikan cmdlet ini.
Untuk mendapatkan objek **PSCloudTask** , gunakan cmdlet Get-AzBatchTask.

```yaml
Type: Microsoft.Azure.Commands.Batch.Models.PSCloudTask
Parameter Sets: InputObject
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

### Microsoft.Azure.Commands.Batch.Models.PSCloudTask

### Microsoft.Azure.Commands.Batch.BatchAccountContext

## OUTPUTS

### System.Void

## NOTES

## RELATED LINKS

[Get-AzBatchTask](./Get-AzBatchTask.md)

[New-AzBatchTask](./New-AzBatchTask.md)

[Remove-AzBatchTask](./Remove-AzBatchTask.md)

[Cmdlet Azure Batch](/powershell/module/Az.Batch/)
