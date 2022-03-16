---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Automation.dll-Help.xml
Module Name: Az.Automation
ms.assetid: 38BB4F4E-B72B-460E-8DF2-2A7A9CACDB41
online version: https://docs.microsoft.com/powershell/module/az.automation/get-azautomationjoboutputrecord
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Automation/Automation/help/Get-AzAutomationJobOutputRecord.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Automation/Automation/help/Get-AzAutomationJobOutputRecord.md
ms.openlocfilehash: cc4be181d9c44e0f6db0836d3445c4ee3a944299
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140143341"
---
# Get-AzAutomationJobOutputRecord

## SYNOPSIS
Mendapatkan output penuh dari catatan output pekerjaan Otomatisasi.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.automation/get-azautomationjoboutputrecord) untuk informasi terkini.

## SYNTAX

```
Get-AzAutomationJobOutputRecord [-JobId] <Guid> [-Id] <String> [-ResourceGroupName] <String>
 [-AutomationAccountName] <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzAutomationJobOutputRecord** mendapatkan output penuh dari catatan output pekerjaan Otomatisasi.
Meskipun cmdlet **Get-AzAutomationJobOutput** mencantumkan satu atau beberapa rekaman output pekerjaan, cmdlet ini hanya mengembalikan ringkasan, sebagai string, dari nilai rekaman output apa pun.
Data ini tidak mengembalikan nilai penuh dari nilai output rekaman output dalam tipe aslinya.
Selain itu, ringkasan memiliki panjang maksimum, yang nilai penuh output cmdlet ini mungkin melebihi.

## EXAMPLES

### Contoh 1: Mendapatkan output penuh pekerjaan Otomatisasi
```
PS C:\>Get-AzAutomationJobOutput -AutomationAccountName "Contoso17" -Id 2989b069-24fe-40b9-b3bd-cb7e5eac4b64 -ResourceGroupName "ResourceGroup01" -Stream "Any" | Get-AzAutomationJobOutputRecord
```

Perintah ini mendapatkan output lengkap pekerjaan yang memiliki ID pekerjaan tertentu.

## PARAMETERS

### -AutomationAccountName
Menentukan nama akun Otomatisasi yang akan mendapatkan catatan output pekerjaan dari cmdlet ini.

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

### -Id
Menentukan ID rekaman output pekerjaan untuk cmdlet ini agar dapat diambil.

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
Menentukan ID pekerjaan bagi cmdlet ini untuk mendapatkan rekaman output.

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
Menentukan nama grup sumber daya di mana cmdlet ini mendapatkan catatan output pekerjaan.

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

## CATATAN

## RELATED LINKS

[Get-AzAutomationJobOutput](./Get-AzAutomationJobOutput.md)


