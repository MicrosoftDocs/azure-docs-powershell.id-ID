---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Accounts.dll-Help.xml
Module Name: Az.Accounts
online version: https://docs.microsoft.com/powershell/module/az.accounts/enable-azcontextautosave
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Accounts/Accounts/help/Enable-AzContextAutosave.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Accounts/Accounts/help/Enable-AzContextAutosave.md
ms.openlocfilehash: c836dc197bd55141e174424df69b8775d08b5a28
ms.sourcegitcommit: 22f85a560177b7234f114dd21a108e3bc8b1608b
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/01/2022
ms.locfileid: "145972579"
---
# Enable-AzContextAutosave

## SYNOPSIS
Konteks Azure adalah objek PowerShell yang mewakili langganan aktif Anda untuk menjalankan perintah, dan informasi autentikasi yang diperlukan untuk tersambung ke cloud Azure. Dengan konteks Azure, Azure PowerShell tidak perlu mengautentikasi ulang akun Anda setiap kali beralih langganan. Untuk informasi selengkapnya, lihat [Azure PowerShell objek konteks](https://docs.microsoft.com/powershell/azure/context-persistence).

Cmdlet ini memungkinkan informasi konteks Azure disimpan dan dimuat secara otomatis saat Anda memulai proses PowerShell. Misalnya, saat membuka jendela baru.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.accounts/enable-azcontextautosave) untuk informasi terbaru.

## SYNTAX

```
Enable-AzContextAutosave [-Scope <ContextModificationScope>] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION

Memungkinkan informasi konteks Azure disimpan dan dimuat secara otomatis saat proses PowerShell dimulai. Konteks disimpan di akhir eksekusi cmdlet apa pun yang memengaruhi konteks. Misalnya, cmdlet profil apa pun. Jika Anda menggunakan autentikasi pengguna, maka token dapat diperbarui selama menjalankan cmdlet apa pun.

## EXAMPLES

### Contoh 1: Aktifkan simpan otomatis kredensial untuk pengguna saat ini

Aktifkan penyimpanan otomatis kredensial untuk pengguna saat ini. Setiap kali jendela PowerShell dibuka, konteks Anda saat ini diingat tanpa masuk.

```powershell
Enable-AzContextAutosave
```

### Contoh 2

Izinkan informasi masuk, akun, dan langganan Azure, disimpan dan dimuat secara otomatis saat Anda membuka jendela PowerShell di sesi PowerShell ini. (dibuat otomatis)

<!-- Aladdin Generated Example -->
```powershell
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

### -Cakupan

Menentukan cakupan perubahan konteks. Misalnya, apakah perubahan hanya berlaku untuk proses saat ini, atau untuk semua sesi yang dimulai oleh pengguna ini. Perubahan yang dibuat dengan cakupan `CurrentUser` akan memengaruhi semua sesi PowerShell yang dimulai oleh pengguna. Jika sesi tertentu perlu memiliki pengaturan yang berbeda, gunakan cakupan `Process`.

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

### -Confirm

Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

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

Menunjukkan yang akan terjadi jika cmdlet dijalankan.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Tidak ada

## OUTPUTS

### Microsoft.Azure.Commands.Common.Authentication.ContextAutosaveSettings

## NOTES

## RELATED LINKS
