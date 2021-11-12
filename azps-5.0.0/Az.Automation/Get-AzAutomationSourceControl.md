---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Automation.dll-Help.xml
Module Name: Az.Automation
online version: https://docs.microsoft.com/en-us/powershell/module/az.automation/get-azautomationsourcecontrol
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Automation/Automation/help/Get-AzAutomationSourceControl.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Automation/Automation/help/Get-AzAutomationSourceControl.md
ms.openlocfilehash: 42472efdde4ccf96f12a0617d9a86175eed13d1c
ms.sourcegitcommit: b4a38bcb0501a9016a4998efd377aa75d3ef9ce8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/27/2020
ms.locfileid: "132408409"
---
# Get-AzAutomationSourceControl

## SYNOPSIS
Mendapatkan daftar kontrol sumber Otomatisasi Azure.

## SINTAKS

### SecaraSemua (Default)
```
Get-AzAutomationSourceControl [-SourceType <String>] [-ResourceGroupName] <String>
 [-AutomationAccountName] <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByName
```
Get-AzAutomationSourceControl -Name <String> [-ResourceGroupName] <String> [-AutomationAccountName] <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESKRIPSI
Cmdlet Get-AzAutomationSourceControl mendapatkan kontrol sumber Otomatisasi.
Untuk mendapatkan kontrol sumber tertentu, tentukan namanya.

## CONTOH

### Contoh 1
Perintah ini mendapatkan kontrol sumber Otomatisasi yang bernama VSTSNative dalam akun yang bernama devAccount.


```powershell
PS C:\> Get-AzAutomationSourceControl -ResourceGroupName "rg1" `
                                           -AutomationAccountName "devAccount" `
                                           -Name "VSTSNative" 


Name            SourceType Branch FolderPath  AutoSync PublishRunbook RepoUrl
----            ---------- ------ ----------  -------- -------------- -------
VSTSNative      VsoTfvc           /MyRunbooks False    True           https://contoso.visualstudio.com/_git/Fin...
```

## PARAMETERS

### -AutomationAccountName
Nama akun otomatisasi.

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

### -Nama
Nama kontrol sumber.

```yaml
Type: System.String
Parameter Sets: ByName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Nama grup sumber daya.

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

### -SourceType
Tipe kontrol sumber.

```yaml
Type: System.String
Parameter Sets: ByAll
Aliases:
Accepted values: GitHub, VsoGit, VsoTfvc

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUT

### System.String

## OUTPUT

### Microsoft.Azure.Commands.Automation.Model.SourceControl

## CATATAN

## LINK TERKAIT
