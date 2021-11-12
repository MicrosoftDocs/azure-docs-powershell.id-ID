---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Automation.dll-Help.xml
Module Name: Az.Automation
ms.assetid: EDB918EA-4FF3-44EF-A4CA-5BFBD14340EA
online version: https://docs.microsoft.com/en-us/powershell/module/az.automation/get-azautomationrunbook
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Automation/Automation/help/Get-AzAutomationRunbook.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Automation/Automation/help/Get-AzAutomationRunbook.md
ms.openlocfilehash: edae476893de5a64e950902d2de7b31fe53b51ea
ms.sourcegitcommit: b4a38bcb0501a9016a4998efd377aa75d3ef9ce8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/27/2020
ms.locfileid: "132410263"
---
# Get-AzAutomationRunbook

## SYNOPSIS
Mendapatkan buku runbook.

## SINTAKS

### SecaraSemua (Default)
```
Get-AzAutomationRunbook [-ResourceGroupName] <String> [-AutomationAccountName] <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByRunbookName
```
Get-AzAutomationRunbook [-Name] <String> [-ResourceGroupName] <String> [-AutomationAccountName] <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESKRIPSI
Cmdlet **Get-AzAutomationRunbook** mendapatkan runbooks Azure Automation.
Untuk mendapatkan runbook spesifik, tentukan namanya.

## CONTOH

### Contoh 1: Dapatkan semua runbooks
```
PS C:\>Get-AzAutomationRunbook -AutomationAccountName "Contoso17" -ResourceGroupName "ResourceGroup01"
```

Perintah ini mendapatkan semua runbooks dalam akun Azure Automation yang bernama Contoso17.

## PARAMETERS

### -AutomationAccountName
Menentukan nama akun Otomatisasi yang akan mendapatkan runbooks oleh cmdlet ini.

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
Menentukan nama runbook yang akan dapatkan cmdlet ini.

```yaml
Type: System.String
Parameter Sets: ByRunbookName
Aliases: RunbookName

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya yang akan menjalankan cmdlet ini.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUT

### System.String

## OUTPUT

### Microsoft.Azure.Commands.Automation.Model.Runbook

## CATATAN

## LINK TERKAIT

[Export-AzAutomationRunbook](./Export-AzAutomationRunbook.md)

[Import-AzAutomationRunbook](./Import-AzAutomationRunbook.md)

[New-AzAutomationRunbook](./New-AzAutomationRunbook.md)

[New-AzAutomationRunbook](./New-AzAutomationRunbook.md)

[Publish-AzAutomationRunbook](./Publish-AzAutomationRunbook.md)

[Remove-AzAutomationRunbook](./Remove-AzAutomationRunbook.md)

[Set-AzAutomationRunbook](./Set-AzAutomationRunbook.md)

[Start-AzAutomationRunbook](./Start-AzAutomationRunbook.md)


