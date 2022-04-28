---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Accounts.dll-Help.xml
Module Name: Az.Accounts
online version: https://docs.microsoft.com/powershell/module/az.accounts/save-azcontext
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Accounts/Accounts/help/Save-AzContext.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Accounts/Accounts/help/Save-AzContext.md
ms.openlocfilehash: b5e9f716241e34d16a9610bb5daa2256b2407350
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144193432"
---
# Save-AzContext

## SYNOPSIS
Menyimpan informasi autentikasi saat ini untuk digunakan dalam sesi PowerShell lainnya.

## SYNTAX

```
Save-AzContext [[-Profile] <AzureRmProfile>] [-Path] <String> [-Force]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet Save-AzContext menyimpan informasi autentikasi saat ini untuk digunakan dalam sesi PowerShell lainnya.

## EXAMPLES

### Contoh 1: Menyimpan konteks sesi saat ini
```powershell
Connect-AzAccount
Save-AzContext -Path C:\test.json
```

Contoh ini menyimpan konteks Azure sesi saat ini ke file JSON yang disediakan.

### Contoh 2: Menyimpan konteks tertentu
```powershell
Save-AzContext -Profile (Connect-AzAccount) -Path C:\test.json
```

Contoh ini menyimpan konteks Azure yang diteruskan ke cmdlet ke file JSON yang disediakan.

## PARAMETERS

### -DefaultProfile
Kredensial, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure.

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
Timpa file yang diberikan jika ada

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

### -Jalur
Menentukan jalur file untuk menyimpan informasi autentikasi.

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

### -Profil
Menentukan konteks Azure dari mana cmdlet ini dibaca.
Jika Anda tidak menentukan konteks, cmdlet ini akan membaca dari konteks default lokal.

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Models.AzureRmProfile
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
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

### Microsoft.Azure.Commands.Common.Authentication.Models.AzureRmProfile

## OUTPUTS

### Microsoft.Azure.Commands.Profile.Models.Core.PSAzureProfile

## NOTES

## RELATED LINKS
