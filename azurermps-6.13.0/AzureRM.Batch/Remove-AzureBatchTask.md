---
external help file: Microsoft.Azure.Commands.Batch.dll-Help.xml
Module Name: AzureRM.Batch
ms.assetid: D79AEF8C-F0DC-40F8-9EEE-A2BB6AE5C4BF
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.batch/remove-azurebatchtask
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/AzureBatch/Commands.Batch/help/Remove-AzureBatchTask.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/AzureBatch/Commands.Batch/help/Remove-AzureBatchTask.md
ms.openlocfilehash: 3012abfca2ca257ad7b72fb974a8c062bfe196d4
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132428439"
---
# Remove-AzureBatchTask

## SYNOPSIS
Menghapus tugas Kumpulan.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

### Id
```
Remove-AzureBatchTask [-JobId] <String> [-Id] <String> [-Force] -BatchContext <BatchAccountContext>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InputObject
```
Remove-AzureBatchTask [-InputObject] <PSCloudTask> [-Force] -BatchContext <BatchAccountContext>
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Remove-AzureBatchTask** menghapus tugas Kumpulan Azure.
Cmdlet ini akan meminta konfirmasi Anda, kecuali anda menentukan parameter *Paksa.*

## EXAMPLES

### Contoh 1: Hapus tugas Kumpulan menurut ID
```
PS C:\>Remove-AzureBatchTask -JobId "Job-000001" -Id "Task23" -BatchContext $Context
```

Perintah ini menghapus tugas yang memiliki ID Task23 di bawah pekerjaan yang memiliki ID Job-000001.
Perintah akan meminta konfirmasi Anda.
Gunakan cmdlet **Get-AzureRmBatchAccountKeys** untuk menetapkan konteks ke $Context variabel.

### Contoh 2: Hapus tugas Kumpulan dengan menggunakan saluran tanpa konfirmasi
```
PS C:\>Get-AzureBatchTask -JobId "Job-000001" -Id "Task26" -BatchContext $Context | Remove-AzureBatchTask -Force -BatchContext $Context
```

Perintah ini mendapatkan tugas Kumpulan yang memiliki ID Task26 dalam pekerjaan yang memiliki ID Job-000001 dengan menggunakan cmdlet **Get-AzureBatchTask.**
Perintah itu meneruskan tugas itu ke cmdlet saat ini dengan menggunakan operator pipeline.
Perintah menghapus tugas tersebut.
Perintah ini menentukan parameter *Force.*
Oleh karena itu, perintah tidak akan meminta konfirmasi Anda.

## PARAMETERS

### -BatchContext
Menentukan contoh **BatchAccountContext** yang digunakan cmdlet untuk berinteraksi dengan layanan Batch.
Jika Anda menggunakan cmdlet Get-AzureRmBatchAccount untuk mendapatkan BatchAccountContext, autentikasi Azure Active Directory akan digunakan saat berinteraksi dengan layanan Batch. Untuk menggunakan autentikasi kunci bersama, gunakan cmdlet Get-AzureRmBatchAccountKeys untuk mendapatkan objek BatchAccountContext dengan tombol aksesnya diisi. Saat menggunakan autentikasi kunci bersama, kunci akses utama digunakan secara default. Untuk mengubah kunci yang akan digunakan, atur properti BatchAccountContext.KeyInUse.

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

### -Force
Memaksa perintah untuk dijalankan tanpa meminta konfirmasi pengguna.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
Menentukan ID tugas yang dihapus cmdlet ini.
Anda tidak bisa menentukan karakter wildcard.

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

### -InputObject
Menentukan tugas yang dihapus cmdlet ini.
Untuk mendapatkan objek **PSCloudTask,** gunakan Get-AzureBatchTask cmdlet.

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

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak berjalan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### System.String

### Microsoft.Azure.Commands.Batch.Models.PSCloudTask
Parameter: InputObject (ByValue)

### Microsoft.Azure.Commands.Batch.BatchAccountContext
Parameter: BatchContext (ByValue)

## OUTPUTS

### System.Void

## CATATAN

## RELATED LINKS

[Get-AzureRmBatchAccountKeys](./Get-AzureRmBatchAccountKeys.md)

[Get-AzureBatchTask](./Get-AzureBatchTask.md)

[New-AzureBatchTask](./New-AzureBatchTask.md)

[Remove-AzureBatchTask](./Remove-AzureBatchTask.md)

[Stop-AzureBatchTask](./Stop-AzureBatchTask.md)

[Cmdlet Kumpulan Azure](./AzureRM.Batch.md)


