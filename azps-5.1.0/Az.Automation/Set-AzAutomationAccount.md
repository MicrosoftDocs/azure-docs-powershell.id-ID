---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Automation.dll-Help.xml
Module Name: Az.Automation
ms.assetid: B1897EFC-0184-4A8B-B8E4-203CC8E3B179
online version: https://docs.microsoft.com/en-us/powershell/module/az.automation/set-azautomationaccount
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Automation/Automation/help/Set-AzAutomationAccount.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Automation/Automation/help/Set-AzAutomationAccount.md
ms.openlocfilehash: f32e9c0d76e88fba5475abb39595b0a6c4bea834
ms.sourcegitcommit: d81c3b0f0f7289104be03869eb675128b61db7d3
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/17/2020
ms.locfileid: "136023124"
---
# Set-AzAutomationAccount

## SYNOPSIS
Memodifikasi akun Otomatisasi.

## SINTAKS

```
Set-AzAutomationAccount [-ResourceGroupName] <String> [-Name] <String> [-Plan <String>] [-Tags <IDictionary>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESKRIPSI
Cmdlet **Set-AzAutomationAccount** mengubah akun Otomatisasi Azure.
Untuk informasi selengkapnya tentang akun Otomatisasi, lihat cmdlet New-AzAutomationAccount baru.

## CONTOH

### Contoh 1: Mengatur tag untuk akun Otomatisasi
```
PS C:\>$Tags = @{"tag01"="value01";"tag02"="value02"}
PS C:\> Set-AzAutomationAccount -Name "AutomationAccount01" -ResourceGroupName "ResourceGroup01" -Tags $Tags
```

Perintah pertama menetapkan dua pasangan kunci/nilai ke $Tags nilai.
Perintah kedua mengatur tag dalam $Tags akun Otomatisasi bernama AutomationAccount01.

### Contoh 2: Mengubah rencana untuk akun Otomatisasi
```
PS C:\>Set-AzAutomationAccount -Name "AutomationAccount01" -ResourceGroupName "ResourceGroup01" -Plan Basic
```

Perintah ini mengubah rencana ke Dasar untuk akun Otomatisasi bernama AutomationAccount01.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

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

### -Nama
Menentukan nama akun Otomatisasi yang dimodifikasi cmdlet ini.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: AutomationAccountName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Rencana
Menentukan rencana untuk akun Otomatisasi.
Nilai valid adalah:
- Dasar
- Gratis

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: Free, Basic

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya yang berisi akun Otomatisasi yang dimodifikasi cmdlet ini.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Tag
Pasangan nilai kunci dalam bentuk tabel hash. Misalnya: @{key0="value0";key1=$null;key2="value2"}

```yaml
Type: System.Collections.IDictionary
Parameter Sets: (All)
Aliases: Tag

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUT

### System.String

### System.Collections.IDictionary

## OUTPUT

### Microsoft.Azure.Commands.Automation.Model.AutomationAccount

## CATATAN

## LINK TERKAIT

[Get-AzAutomationAccount](./Get-AzAutomationAccount.md)

[New-AzAutomationAccount](./New-AzAutomationAccount.md)

[Remove-AzAutomationAccount](./Remove-AzAutomationAccount.md)
