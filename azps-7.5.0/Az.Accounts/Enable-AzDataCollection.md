---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Accounts.dll-Help.xml
Module Name: Az.Accounts
online version: https://docs.microsoft.com/powershell/module/az.accounts/enable-azdatacollection
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Accounts/Accounts/help/Enable-AzDataCollection.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Accounts/Accounts/help/Enable-AzDataCollection.md
ms.openlocfilehash: 2750e32988f0813ceb0d6fbfe179be0b7acd1e43
ms.sourcegitcommit: 321c644cf2161807a71e1af318fc5c5311d22e25
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/25/2022
ms.locfileid: "145782856"
---
# Enable-AzDataCollection

## SYNOPSIS
Memungkinkan Azure PowerShell mengumpulkan data untuk meningkatkan pengalaman pengguna dengan cmdlet Azure PowerShell. Menjalankan cmdlet ini memilih untuk pengumpulan data untuk pengguna saat ini pada komputer saat ini. Data dikumpulkan secara default kecuali Anda secara eksplisit memilih keluar.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.accounts/enable-azdatacollection) untuk informasi terbaru.

## SYNTAX

```
Enable-AzDataCollection [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Enable-AzDataCollection` Cmdlet digunakan untuk ikut serta dalam pengumpulan data. Azure PowerShell secara otomatis mengumpulkan data telemetri secara default. Microsoft mengagregasi kumpulan data untuk mengidentifikasi pola penggunaan, mengidentifikasi masalah umum, dan meningkatkan pengalaman Azure PowerShell.
Microsoft Azure PowerShell tidak mengumpulkan data pribadi atau personal apa pun. Untuk menonaktifkan pengumpulan data, Anda harus secara eksplisit memilih keluar dengan mengeksekusi `Disable-AzDataCollection`.

## EXAMPLES

### Contoh 1: Mengaktifkan pengumpulan data untuk pengguna saat ini

Contoh berikut menunjukkan cara mengaktifkan pengumpulan data untuk pengguna saat ini.

```powershell
Enable-AzDataCollection
```

## PARAMETERS

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

### -Confirm

Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

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

Menunjukkan yang akan terjadi jika cmdlet dijalankan. Cmdlet tidak dijalankan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Tidak ada

## OUTPUTS

### System.Void

## NOTES

## RELATED LINKS

[Disable-AzDataCollection](./Disable-AzDataCollection.md)
