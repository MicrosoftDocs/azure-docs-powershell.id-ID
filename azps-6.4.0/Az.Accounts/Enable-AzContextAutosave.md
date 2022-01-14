---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Accounts.dll-Help.xml
Module Name: Az.Accounts
online version: https://docs.microsoft.com/powershell/module/az.accounts/enable-azcontextautosave
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Accounts/Accounts/help/Enable-AzContextAutosave.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Accounts/Accounts/help/Enable-AzContextAutosave.md
ms.openlocfilehash: d42707f94f4c18ea4fa2b7008aeeee560212a5ed
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136179717"
---
# Enable-AzContextAutosave

## SYNOPSIS
Konteks Azure adalah objek PowerShell yang mewakili langganan aktif untuk dijalankan, dan informasi autentikasi yang diperlukan untuk tersambung ke cloud Azure. Dengan konteks Azure, Azure PowerShell tidak perlu mengautentikasi ulang akun Setiap kali Anda beralih langganan. Untuk informasi selengkapnya, lihat [Azure PowerShell objek konteks](https://docs.microsoft.com/powershell/azure/context-persistence).

Cmdlet ini memungkinkan informasi konteks Azure disimpan dan dimuat secara otomatis saat Anda memulai proses PowerShell. Misalnya, ketika membuka jendela baru.

## SYNTAX

```
Enable-AzContextAutosave [-Scope <ContextModificationScope>] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Memungkinkan informasi konteks Azure disimpan dan dimuat secara otomatis saat proses PowerShell dimulai. Konteks disimpan di akhir eksekusi cmdlet apa pun yang mempengaruhi konteks. Misalnya, cmdlet profil apa pun. Jika Anda menggunakan autentikasi pengguna, token dapat diperbarui selama proses menjalankan cmdlet apa pun.

## EXAMPLES

### Contoh 1: Mengaktifkan kredensial autosaving untuk pengguna saat ini

Aktifkan simpan otomatis kredensial untuk pengguna saat ini. Setiap kali jendela PowerShell dibuka, konteks Anda saat ini akan diingat tanpa masuk.

```powershell
Enable-AzContextAutosave
```

### Contoh 2

Perbolehkan kredensial Azure, akun, dan informasi langganan, disimpan dan dimuat secara otomatis saat Anda membuka jendela PowerShell di sesi PowerShell ini. (otomatisgenerated)

```powershell <!-- Aladdin Generated Example -->
Enable-AzContextAutosave -Scope Process
```

## PARAMETERS

### -DefaultProfile

Kredensial, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

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

### -Lingkup

Menentukan lingkup perubahan konteks. Misalnya, apakah perubahan diterapkan hanya pada proses saat ini, atau pada semua sesi yang dimulai oleh pengguna ini. Perubahan yang dibuat dengan `CurrentUser` lingkup akan mempengaruhi semua sesi PowerShell yang dimulai oleh pengguna. Jika sesi tertentu perlu memiliki pengaturan yang berbeda, gunakan lingkup `Process` .

```yaml
Type: Microsoft.Azure.Commands.Profile.Common.ContextModificationScope
Parameter Sets: (All)
Aliases:
Accepted values: Process, CurrentUser

Required: False
Position: Named
Default value: CurrentUser
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
Default value: None
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
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.Common.Authentication.ContextAutosaveSettings

## CATATAN

## RELATED LINKS
