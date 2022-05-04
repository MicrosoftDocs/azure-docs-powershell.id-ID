---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Automation.dll-Help.xml
Module Name: Az.Automation
ms.assetid: 9EA7F710-36FB-435C-BF28-1015E5D3155F
online version: https://docs.microsoft.com/powershell/module/az.automation/set-azautomationwebhook
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Automation/Automation/help/Set-AzAutomationWebhook.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Automation/Automation/help/Set-AzAutomationWebhook.md
ms.openlocfilehash: 6613ba518699d613b59796c4c21cffa0af521d20
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144563122"
---
# Set-AzAutomationWebhook

## SYNOPSIS
Memodifikasi webhook untuk runbook Automation.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.automation/set-azautomationwebhook) untuk informasi terbaru.

## SYNTAX

```
Set-AzAutomationWebhook [-Name] <String> [-IsEnabled] <Boolean> [[-Parameters] <IDictionary>] [-RunOn <String>]
 [-ResourceGroupName] <String> [-AutomationAccountName] <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzAutomationWebhook** memodifikasi webhook untuk runbook Azure Automation.

## EXAMPLES

### Contoh 1: Menonaktifkan webhook
```powershell
PS C:\>Set-AzAutomationWebhook -Name "Webhook01" -ResourceGroupName "ResourceGroup01" -AutomationAccountName "AutomationAccount01" -IsEnabled $False
```

Perintah ini menonaktifkan webhook bernama Webhook01 di akun Automation bernama AutomationAccount01.

### Contoh 2
```powershell
PS C:\>Set-AzAutomationWebhook -Name "Webhook01" -ResourceGroupName "ResourceGroup01" -AutomationAccountName "AutomationAccount01" -RunOn 'Windows'
```

Perintah ini mengatur nilai run on untuk webhook dan memaksa runbook dijalankan pada grup Hybrid Worker yang disebut Windows.

### Contoh 3
```powershell
PS C:\>Set-AzAutomationWebhook -Name "Webhook01" -ResourceGroupName "ResourceGroup01" -AutomationAccountName "AutomationAccount01" -RunOn $null
```

Perintah ini memperbarui nilai jalankan pada webhook dan memaksa runbook dijalankan pada pekerja runbook Azure. 

## PARAMETERS

### -AutomationAccountName
Menentukan nama akun Automation tempat cmdlet ini memodifikasi webhook.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

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

### -IsEnabled
Menentukan apakah webhook diaktifkan.

```yaml
Type: System.Nullable`1[System.Boolean]
Parameter Sets: (All)
Aliases:

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Name
Menentukan nama webhook yang diubah cmdlet ini.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Parameters
Menentukan kamus pasangan kunci/nilai.
Kuncinya adalah nama parameter runbook.
Nilainya adalah nilai parameter runbook.
Ketika runbook dimulai sebagai respons terhadap webhook, parameter ini diteruskan ke runbook.

```yaml
Type: System.Collections.IDictionary
Parameter Sets: (All)
Aliases:

Required: False
Position: 4
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya yang cmdlet ini memodifikasi webhook.

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

### -RunOn
Nama opsional agen hibrid yang harus menjalankan runbook

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: HybridWorker

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### System.String

### System.Nullable'1[[System.Boolean, System.Private.CoreLib, Version=4.0.0.0, Culture=netral, PublicKeyToken=7cec85d7bea7798e]]

### System.Collections.IDictionary

## OUTPUTS

### Microsoft.Azure.Commands.Automation.Model.Webhook

## NOTES

## RELATED LINKS

[Get-AzAutomationWebhook](./Get-AzAutomationWebhook.md)

[New-AzAutomationWebhook](./New-AzAutomationWebhook.md)

[Remove-AzAutomationWebhook](./Remove-AzAutomationWebhook.md)


