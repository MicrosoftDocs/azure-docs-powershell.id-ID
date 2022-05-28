---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Automation.dll-Help.xml
Module Name: Az.Automation
ms.assetid: EE854F8A-4B6B-4831-992A-6EC318BEE234
online version: https://docs.microsoft.com/powershell/module/az.automation/get-azautomationscheduledrunbook
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Automation/Automation/help/Get-AzAutomationScheduledRunbook.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Automation/Automation/help/Get-AzAutomationScheduledRunbook.md
ms.openlocfilehash: 23a55b64ed5b5db6b02f338ee71def1410dd11af
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145513855"
---
# Get-AzAutomationScheduledRunbook

## SYNOPSIS
Mendapatkan runbook Automation dan jadwal terkait.

## SYNTAX

### ByAll (Default)
```
Get-AzAutomationScheduledRunbook [-ResourceGroupName] <String> [-AutomationAccountName] <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByJobScheduleId
```
Get-AzAutomationScheduledRunbook -JobScheduleId <Guid> [-ResourceGroupName] <String>
 [-AutomationAccountName] <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByRunbookName
```
Get-AzAutomationScheduledRunbook -RunbookName <String> [-ResourceGroupName] <String>
 [-AutomationAccountName] <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByRunbookNameAndScheduleName
```
Get-AzAutomationScheduledRunbook -RunbookName <String> -ScheduleName <String> [-ResourceGroupName] <String>
 [-AutomationAccountName] <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByScheduleName
```
Get-AzAutomationScheduledRunbook -ScheduleName <String> [-ResourceGroupName] <String>
 [-AutomationAccountName] <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzAutomationScheduledRunbook** mendapatkan satu atau beberapa runbook Azure Automation dan jadwal terkait.
Secara default, cmdlet ini mendapatkan semua runbook terjadwal.
Tentukan nama runbook atau jadwal atau keduanya untuk melihat jadwal runbook tertentu.

## EXAMPLES

### Contoh 1: Mendapatkan semua runbook terjadwal
```powershell
Get-AzAutomationScheduledRunbook -AutomationAccountName "Contoso17" -ResourceGroupName "ResourceGroup01"
```

Perintah ini mendapatkan semua runbook terjadwal di akun Azure Automation bernama Contoso17.

### Contoh 2: Mendapatkan semua jadwal yang terkait dengan runbook
```powershell
Get-AzAutomationScheduledRunbook -AutomationAccountName "Contoso17" -ResourceGroupName "ResourceGroup01" -RunbookName "Runbk01"
```

Perintah ini mendapatkan semua runbook terjadwal untuk runbook Runbk01 di akun Azure Automation bernama Contoso17.

### Contoh 3: Mendapatkan semua runbook yang terkait dengan jadwal
```powershell
Get-AzAutomationScheduledRunbook -AutomationAccountName "Contoso17" -ResourceGroupName "ResourceGroup01" -ScheduleName "Schedule01"
```

Perintah ini mendapatkan semua runbook terjadwal untuk jadwal Schedule01 di akun Azure Automation bernama Contoso17.

### Contoh 4: Dapatkan Parameter yang diberikan ke Runbook Terjadwal

Output perintah di bawah ini menyediakan JobScheduleId yang terkait dengan runbook Runbk01.

```powershell
Get-AzAutomationScheduledRunbook -AutomationAccountName "Contoso17" -ResourceGroupName "ResourceGroup01" -RunbookName "Runbk01"
```

### Contoh 5: Gunakan JobScheduleId yang diperoleh di atas untuk mendapatkan parameter runbook terjadwal Runbk01.

```powershell
$x = Get-AzAutomationScheduledRunbook -AutomationAccountName "Contoso17" -ResourceGroupName "ResourceGroup01" -JobScheduleId “2b1d7738-093d-4ff7-b87b-e4b2321319e5”
$x.Parameters
```

Metode ini saat ini tidak didukung untuk pekerjaan yang dibuat dengan parameter kompleks (misalnya - array) melalui portal Azure.

## PARAMETERS

### -AutomationAccountName
Menentukan akun Automation untuk runbook tempat cmdlet ini beroperasi.

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

### -JobScheduleId
Menentukan ID pekerjaan terjadwal yang didapat cmdlet ini.

```yaml
Type: System.Nullable`1[System.Guid]
Parameter Sets: ByJobScheduleId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya untuk runbook terjadwal yang didapat cmdlet ini.

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

### -RunbookName
Menentukan nama runbook tempat cmdlet ini mendapatkan runbook terjadwal.

```yaml
Type: System.String
Parameter Sets: ByRunbookName, ByRunbookNameAndScheduleName
Aliases: Name

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ScheduleName
Menentukan nama jadwal di mana cmdlet ini mendapatkan runbook terjadwal.

```yaml
Type: System.String
Parameter Sets: ByRunbookNameAndScheduleName, ByScheduleName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.Nullable'1[[System.Guid, System.Private.CoreLib, Version=4.0.0.0, Culture=netral, PublicKeyToken=7cec85d7bea7798e]]

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Automation.Model.JobSchedule

## NOTES

## RELATED LINKS

[Register-AzAutomationScheduledRunbook](./Register-AzAutomationScheduledRunbook.md)

[Unregister-AzAutomationScheduledRunbook](./Unregister-AzAutomationScheduledRunbook.md)


