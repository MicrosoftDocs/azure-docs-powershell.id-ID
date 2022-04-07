---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Batch.dll-Help.xml
Module Name: Az.Batch
ms.assetid: 23893EAE-47F3-45AA-AEB2-354FB8316C25
online version: https://docs.microsoft.com/powershell/module/az.batch/set-azbatchpool
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Batch/Batch/help/Set-AzBatchPool.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Batch/Batch/help/Set-AzBatchPool.md
ms.openlocfilehash: ed9e3782740c9470f8a6279079d364b68e11c007
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140373758"
---
# Set-AzBatchPool

## SYNOPSIS
Memperbarui properti kolam renang.

## SYNTAX

```
Set-AzBatchPool [-Pool] <PSCloudPool> -BatchContext <BatchAccountContext>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzBatchPool** memperbarui properti kumpulan di layanan Azure Batch.
Gunakan cmdlet Get-AzBatchPool untuk mendapatkan objek **PSCloudPool** .
Modifikasi properti objek itu, lalu gunakan cmdlet saat ini untuk melakukan perubahan Anda ke layanan Batch.

## EXAMPLES

### Contoh 1: Perbarui pool
```powershell
$Pool = Get-AzBatchPool "ContosoPool" -BatchContext $Context
$StartTask = New-Object Microsoft.Azure.Commands.Batch.Models.PSStartTask
$StartTask.CommandLine = "cmd /c echo example"
$Pool.StartTask = $StartTask
Set-AzBatchPool -Pool $Pool -BatchContext $Context
```

Perintah pertama mendapatkan kolam renang dengan menggunakan **Get-AzBatchPool**, lalu menyimpannya di $Pool berbeda.
Tiga perintah berikutnya memodifikasi spesifikasi mulai tugas pada $Pool baru.
Perintah terakhir memperbarui layanan Kumpulan agar sesuai dengan objek lokal di $Pool.

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

### -Pool
Menentukan **PSCloudPool tempat** cmdlet ini memperbarui layanan Kumpulan.

```yaml
Type: Microsoft.Azure.Commands.Batch.Models.PSCloudPool
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Batch.Models.PSCloudPool

### Microsoft.Azure.Commands.Batch.BatchAccountContext

## OUTPUTS

### System.Void

## CATATAN

## RELATED LINKS

[Get-AzBatchPool](./Get-AzBatchPool.md)

[Get-AzBatchAccountKey](./Get-AzBatchAccountKey.md)

[New-AzBatchPool](./New-AzBatchPool.md)

[Remove-AzBatchPool](./Remove-AzBatchPool.md)

[Cmdlet Kumpulan Azure](/powershell/module/Az.Batch/)
