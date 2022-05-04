---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Accounts.dll-Help.xml
Module Name: Az.Accounts
online version: https://docs.microsoft.com/powershell/module/az.accounts/disable-azdatacollection
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Accounts/Accounts/help/Disable-AzDataCollection.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Accounts/Accounts/help/Disable-AzDataCollection.md
ms.openlocfilehash: f390e5ac2a65ae46a31920a726afd4118d1ed625
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144586765"
---
# Disable-AzDataCollection

## SYNOPSIS
Menolak mengumpulkan data untuk meningkatkan cmdlet Azure PowerShell. Data dikumpulkan secara default kecuali Anda secara eksplisit memilih keluar.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.accounts/disable-azdatacollection) untuk informasi terbaru.

## SYNTAX

```
Disable-AzDataCollection [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

`Disable-AzDataCollection` Cmdlet digunakan untuk menolak pengumpulan data. Azure PowerShell secara otomatis mengumpulkan data telemetri secara default. Untuk menonaktifkan pengumpulan data, Anda harus secara eksplisit menolak. Microsoft mengumpulkan data untuk mengidentifikasi pola penggunaan, mengidentifikasi masalah umum, dan untuk meningkatkan pengalaman Azure PowerShell. Microsoft Azure PowerShell tidak mengumpulkan data pribadi atau personal apa pun. Jika sebelumnya Anda telah memilih keluar, jalankan `Enable-AzDataCollection` cmdlet untuk mengaktifkan kembali pengumpulan data untuk pengguna saat ini di komputer saat ini.

## EXAMPLES

### Contoh 1: Menonaktifkan pengumpulan data untuk pengguna saat ini

Contoh berikut menunjukkan cara menonaktifkan pengumpulan data untuk pengguna saat ini.

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

[Enable-AzDataCollection](./Enable-AzDataCollection.md)
