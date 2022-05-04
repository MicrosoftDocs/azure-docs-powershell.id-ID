---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Automation.dll-Help.xml
Module Name: Az.Automation
ms.assetid: 38BB4F4E-B72B-460E-8DF2-2A7A9CACDB41
online version: https://docs.microsoft.com/powershell/module/az.automation/get-azautomationjoboutputrecord
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Automation/Automation/help/Get-AzAutomationJobOutputRecord.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Automation/Automation/help/Get-AzAutomationJobOutputRecord.md
ms.openlocfilehash: cc4be181d9c44e0f6db0836d3445c4ee3a944299
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144680702"
---
# Get-AzAutomationJobOutputRecord

## SYNOPSIS
Mendapatkan output lengkap dari rekaman output pekerjaan Automation.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.automation/get-azautomationjoboutputrecord) untuk informasi terbaru.

## SYNTAX

```
Get-AzAutomationJobOutputRecord [-JobId] <Guid> [-Id] <String> [-ResourceGroupName] <String>
 [-AutomationAccountName] <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzAutomationJobOutputRecord** mendapatkan output penuh dari rekaman output pekerjaan Automation.
Meskipun cmdlet **Get-AzAutomationJobOutput** mencantumkan satu atau beberapa rekaman output pekerjaan, cmdlet ini hanya mengembalikan ringkasan, sebagai string, dari nilai rekaman output apa pun.
Ini tidak mengembalikan nilai penuh dari nilai output rekaman output dalam jenis aslinya.
Selain itu, ringkasan memiliki panjang maksimum, yang nilai lengkapnya mungkin melebihi output cmdlet ini.

## EXAMPLES

### Contoh 1: Mendapatkan output lengkap dari pekerjaan Automation
```
PS C:\>Get-AzAutomationJobOutput -AutomationAccountName "Contoso17" -Id 2989b069-24fe-40b9-b3bd-cb7e5eac4b64 -ResourceGroupName "ResourceGroup01" -Stream "Any" | Get-AzAutomationJobOutputRecord
```

Perintah ini mendapatkan output lengkap dari pekerjaan yang memiliki ID pekerjaan yang ditentukan.

## PARAMETERS

### -AutomationAccountName
Menentukan nama akun Automation yang cmdlet ini mendapatkan catatan output pekerjaan.

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

### -Id
Menentukan ID rekaman output pekerjaan untuk diambil cmdlet ini.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: StreamRecordId

Required: True
Position: 3
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -JobId
Menentukan ID pekerjaan di mana cmdlet ini mendapatkan rekaman output.

```yaml
Type: System.Guid
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya tempat cmdlet ini mendapatkan catatan output pekerjaan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.Guid

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Automation.Model.JobStreamRecord

## NOTES

## RELATED LINKS

[Get-AzAutomationJobOutput](./Get-AzAutomationJobOutput.md)


