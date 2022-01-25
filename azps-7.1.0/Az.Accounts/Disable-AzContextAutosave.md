---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Accounts.dll-Help.xml
Module Name: Az.Accounts
online version: https://docs.microsoft.com/powershell/module/az.accounts/disable-azcontextautosave
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Accounts/Accounts/help/Disable-AzContextAutosave.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Accounts/Accounts/help/Disable-AzContextAutosave.md
ms.openlocfilehash: dfd6ed464c7591b26269fe6320d734e06f5328bb
ms.sourcegitcommit: e109cc5320478db6aa8a52d49996b133007a65b9
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 01/12/2022
ms.locfileid: "136730581"
---
# Disable-AzContextAutosave

## SYNOPSIS
Nonaktifkan penyimpanan otomatis kredensial Azure.  Informasi masuk Anda akan lupa saat berikutnya Anda membuka jendela PowerShell

## SYNTAX

```
Disable-AzContextAutosave [-Scope <ContextModificationScope>] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Nonaktifkan penyimpanan otomatis kredensial Azure.  Informasi masuk Anda akan lupa saat berikutnya Anda membuka jendela PowerShell

## EXAMPLES

### Contoh 1: Menonaktifkan pengarsipan otomatis konteks
```powershell
PS C:\> Disable-AzContextAutosave
```

Menonaktifkan simpan otomatis untuk pengguna saat ini.

### Contoh 2

Nonaktifkan kredensial Azure otomatis di sesi powershell ini. (otomatisgenerated)

```powershell <!-- Aladdin Generated Example --> 
Disable-AzContextAutosave -Scope Process
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
Menentukan lingkup perubahan konteks, misalnya, apakah perubahan diterapkan hanya pada proses saat ini, atau pada semua sesi yang dimulai oleh pengguna ini

```yaml
Type: Microsoft.Azure.Commands.Profile.Common.ContextModificationScope
Parameter Sets: (All)
Aliases:
Accepted values: Process, CurrentUser

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
