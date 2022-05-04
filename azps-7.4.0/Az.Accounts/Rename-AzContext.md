---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Accounts.dll-Help.xml
Module Name: Az.Accounts
online version: https://docs.microsoft.com/powershell/module/az.accounts/rename-azcontext
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Accounts/Accounts/help/Rename-AzContext.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Accounts/Accounts/help/Rename-AzContext.md
ms.openlocfilehash: a6647c6c971481751a2911d9939fa032d964168e
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144668212"
---
# Rename-AzContext

## SYNOPSIS
Mengganti nama konteks Azure.  Secara default konteks dinamai oleh akun pengguna dan langganan.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.accounts/rename-azcontext) untuk informasi terbaru.

## SYNTAX

### RenameByInputObject (Default)
```
Rename-AzContext -InputObject <PSAzureContext> [-Force] [-PassThru] [-Scope <ContextModificationScope>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [-TargetName] <String> [<CommonParameters>]
```

### Ganti NamaByName
```
Rename-AzContext [-Force] [-PassThru] [-Scope <ContextModificationScope>]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [-SourceName] <String> [-TargetName] <String>
 [<CommonParameters>]
```

## DESCRIPTION
Mengganti nama konteks Azure.  Secara default konteks dinamai oleh akun pengguna dan langganan.

## EXAMPLES

### Contoh 1: Mengganti nama konteks menggunakan parameter bernama
```powershell
Rename-AzContext -SourceName "[user1@contoso.org; 12345-6789-2345-3567890]" -TargetName "Work"
```

Ganti nama konteks untuk 'user1@contoso.org' dengan langganan '12345-6789-2345-3567890' menjadi 'Work'.  Setelah perintah ini, Anda akan dapat menargetkan konteks menggunakan 'Select-AzContext Work'.  Perhatikan bahwa Anda dapat menelusuri nilai untuk 'SourceName' menggunakan penyelesaian tab.

### Contoh 2: Mengganti nama konteks menggunakan parameter posisi
```powershell
Rename-AzContext "My context" "Work"
```

Ganti nama konteks bernama "Konteks saya" menjadi "Kerja".  Setelah perintah ini, Anda akan dapat menargetkan konteks menggunakan Select-AzContext Work

## PARAMETERS

### -DefaultProfile
Kredensial, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

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

### -Force
Ganti nama konteks meskipun konteks target sudah ada

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

### -InputObject
Objek konteks, biasanya melewati alur.

```yaml
Type: Microsoft.Azure.Commands.Profile.Models.Core.PSAzureContext
Parameter Sets: RenameByInputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PassThru
Mengembalikan konteks yang diganti namanya.

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
Menentukan cakupan perubahan konteks, misalnya, apakah perubahan hanya berlaku untuk proses saat ini, atau untuk semua sesi yang dimulai oleh pengguna ini

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

### -SourceName
Nama konteks

```yaml
Type: System.String
Parameter Sets: RenameByName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -TargetName
Nama baru konteks

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
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

### Microsoft.Azure.Commands.Profile.Models.Core.PSAzureContext

## OUTPUTS

### Microsoft.Azure.Commands.Profile.Models.Core.PSAzureContext

## NOTES

## RELATED LINKS
