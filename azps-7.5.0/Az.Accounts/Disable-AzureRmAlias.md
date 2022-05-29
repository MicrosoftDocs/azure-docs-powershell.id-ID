---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Accounts.dll-Help.xml
Module Name: Az.Accounts
online version: https://docs.microsoft.com/powershell/module/az.accounts/disable-azurermalias
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Accounts/Accounts/help/Disable-AzureRmAlias.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Accounts/Accounts/help/Disable-AzureRmAlias.md
ms.openlocfilehash: eaa01a23fb1f7bf171a4f6808d59747f46700ad6
ms.sourcegitcommit: 321c644cf2161807a71e1af318fc5c5311d22e25
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/25/2022
ms.locfileid: "145798791"
---
# Disable-AzureRmAlias

## SYNOPSIS
Menonaktifkan alias awalan AzureRm untuk modul Az.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.accounts/disable-azurermalias) untuk informasi terbaru.

## SYNTAX

```
Disable-AzureRmAlias [-Scope <String>] [-Module <String[]>] [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Menonaktifkan alias awalan AzureRm untuk modul Az. Jika -Modul ditentukan, hanya modul yang tercantum yang akan menonaktifkan alias. Jika tidak, semua alias AzureRm dinonaktifkan.

## EXAMPLES

### Contoh 1
```powershell
Disable-AzureRmAlias
```

Menonaktifkan semua awalan AzureRm untuk sesi PowerShell saat ini.

### Contoh 2
```powershell
Disable-AzureRmAlias -Module Az.Accounts -Scope CurrentUser
```

Menonaktifkan alias AzureRm untuk modul Az.Accounts untuk proses saat ini dan untuk pengguna saat ini.

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

### -Module
Menunjukkan modul mana yang akan dinonaktifkan aliasnya.
Jika tidak ada yang ditentukan, defaultnya adalah semua modul yang diaktifkan.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Jika ditentukan, cmdlet akan mengembalikan semua alias yang dinonaktifkan

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

### -Cakupan
Menunjukkan alias cakupan apa yang harus dinonaktifkan. Defaultnya adalah 'Proses'

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Process, CurrentUser, LocalMachine

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

### System.String

## NOTES

## RELATED LINKS
