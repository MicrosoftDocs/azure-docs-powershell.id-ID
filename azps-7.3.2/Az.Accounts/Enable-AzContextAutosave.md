---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Accounts.dll-Help.xml
Module Name: Az.Accounts
online version: https://docs.microsoft.com/powershell/module/az.accounts/enable-azcontextautosave
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Accounts/Accounts/help/Enable-AzContextAutosave.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Accounts/Accounts/help/Enable-AzContextAutosave.md
ms.openlocfilehash: f6e2fcdea01c9bb97c8a65c4b8899537bd9bfbba
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141900135"
---
# Enable-AzContextAutosave

## SYNOPSIS
Konteks Azure adalah objek PowerShell yang mewakili langganan aktif Anda untuk menjalankan perintah, dan informasi autentikasi yang diperlukan untuk menyambungkan ke awan Azure. Dengan konteks Azure, Azure PowerShell tidak perlu menulis ulang akun setiap kali Anda beralih langganan. Untuk informasi selengkapnya, lihat [Azure PowerShell objek konteks](https://docs.microsoft.com/powershell/azure/context-persistence).

Cmdlet ini memungkinkan informasi konteks Azure disimpan dan dimuat secara otomatis saat Anda memulai proses PowerShell. Misalnya, saat membuka jendela baru.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.accounts/enable-azcontextautosave) untuk informasi terbaru.

## SYNTAX

```
Enable-AzContextAutosave [-Scope <ContextModificationScope>] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Memungkinkan informasi konteks Azure disimpan dan dimuat secara otomatis saat proses PowerShell dimulai. Konteks disimpan di akhir eksekusi cmdlet apa pun yang mempengaruhi konteks. Misalnya, cmdlet profil apa pun. Jika Anda menggunakan autentikasi pengguna, token dapat diperbarui selama menjalankan cmdlet apa pun.

## EXAMPLES

### Contoh 1: Mengaktifkan penyimpanan otomatis kredensial untuk pengguna saat ini

Aktifkan penyimpanan otomatis kredensial untuk pengguna saat ini. Setiap kali jendela PowerShell dibuka, konteks Anda saat ini diingat tanpa masuk.

```powershell
Enable-AzContextAutosave
```

### Contoh 2

Izinkan informasi kredensial, akun, dan langganan Azure, disimpan dan dimuat secara otomatis saat Anda membuka jendela PowerShell dalam sesi PowerShell ini. (autogenerasi)

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

Menentukan lingkup perubahan konteks. Misalnya, apakah perubahan hanya berlaku untuk proses saat ini, atau ke semua sesi yang dimulai oleh pengguna ini. Perubahan yang dibuat dengan lingkup `CurrentUser` akan mempengaruhi semua sesi PowerShell yang dimulai oleh pengguna. Jika sesi tertentu perlu memiliki pengaturan yang berbeda, gunakan lingkup `Process`.

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

Meminta konfirmasi sebelum menjalankan cmdlet.

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
Cmdlet tidak dijalankan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Tidak

## OUTPUTS

### Microsoft.Azure.Commands.Common.Authentication.ContextAutosaveSettings

## CATATAN

## RELATED LINKS
