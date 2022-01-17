---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Accounts.dll-Help.xml
Module Name: Az.Accounts
online version: https://docs.microsoft.com/en-us/powershell/module/az.accounts/disable-azdatacollection
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Accounts/Accounts/help/Disable-AzDataCollection.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Accounts/Accounts/help/Disable-AzDataCollection.md
ms.openlocfilehash: 27b3565191d7de110a5ba3a1e37d204fe3301cbf
ms.sourcegitcommit: d81c3b0f0f7289104be03869eb675128b61db7d3
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/17/2020
ms.locfileid: "136029716"
---
# Disable-AzDataCollection

## SYNOPSIS
Memilih untuk tidak mengumpulkan data untuk meningkatkan Azure PowerShell cmdlet. Data akan dikumpulkan secara default kecuali Anda secara eksplisit memilih untuk tidak mengikuti.

## SINTAKS

```
Disable-AzDataCollection [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESKRIPSI

Cmdlet `Disable-AzDataCollection` digunakan untuk menolak pengumpulan data. Azure PowerShell mengumpulkan data telemetri secara default. Untuk menonaktifkan pengumpulan data, Anda harus secara eksplisit memilih untuk tidak ikut serta. Microsoft menggabungkan data yang dikumpulkan untuk mengidentifikasi pola penggunaan, untuk mengidentifikasi masalah umum, dan untuk meningkatkan pengalaman Azure PowerShell. Microsoft Azure PowerShell tidak mengumpulkan data pribadi atau pribadi apa pun. Jika sebelumnya Anda memilih untuk tidak mengikuti, jalankan cmdlet untuk `Enable-AzDataCollection` mengaktifkan kembali pengumpulan data bagi pengguna saat ini di komputer saat ini.

## CONTOH

### Contoh 1: Menonaktifkan pengumpulan data untuk pengguna saat ini

Contoh berikut ini memperlihatkan cara menonaktifkan pengumpulan data untuk pengguna saat ini.

```powershell
Disable-AzDataCollection
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

Memperlihatkan apa yang akan terjadi jika cmdlet berjalan. Cmdlet tidak berjalan.

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

Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](/powershell/module/microsoft.powershell.core/about/about_commonparameters).

## INPUT

### Tidak ada

## OUTPUT

### System.Void

## CATATAN

## LINK TERKAIT

[Enable-AzDataCollection](./Enable-AzDataCollection.md)
