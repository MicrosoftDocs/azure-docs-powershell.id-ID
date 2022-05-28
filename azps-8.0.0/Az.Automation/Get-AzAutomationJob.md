---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Automation.dll-Help.xml
Module Name: Az.Automation
ms.assetid: BD32B909-296B-4E46-A24F-6E2BD4B9764B
online version: https://docs.microsoft.com/powershell/module/az.automation/get-azautomationjob
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Automation/Automation/help/Get-AzAutomationJob.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Automation/Automation/help/Get-AzAutomationJob.md
ms.openlocfilehash: 6f9930596ce42097ce10862469f50cdfd8c6c452
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145620619"
---
# Get-AzAutomationJob

## SYNOPSIS
Mendapatkan pekerjaan runbook Automation.

## SYNTAX

### ByAll (Default)
```
Get-AzAutomationJob [-Status <String>] [-StartTime <DateTimeOffset>] [-EndTime <DateTimeOffset>]
 [-ResourceGroupName] <String> [-AutomationAccountName] <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### ByJobId
```
Get-AzAutomationJob -Id <Guid> [-ResourceGroupName] <String> [-AutomationAccountName] <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByRunbookName
```
Get-AzAutomationJob -RunbookName <String> [-Status <String>] [-StartTime <DateTimeOffset>]
 [-EndTime <DateTimeOffset>] [-ResourceGroupName] <String> [-AutomationAccountName] <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzAutomationJob** mendapatkan pekerjaan runbook di Azure Automation.

## EXAMPLES

### Contoh 1: Mendapatkan pekerjaan runbook tertentu
```powershell
Get-AzAutomationJob -AutomationAccountName "Contoso17" -Id 2989b069-24fe-40b9-b3bd-cb7e5eac4b647
```

Perintah ini mendapatkan pekerjaan yang memiliki GUID yang ditentukan.

### Contoh 2: Mendapatkan semua pekerjaan untuk runbook
```powershell
Get-AzAutomationJob -AutomationAccountName "Contoso17" -ResourceGroupName "ResourceGroup01" -RunbookName "Runbook02"
```

Perintah ini mendapatkan semua pekerjaan yang terkait dengan runbook bernama Runbook02.

### Contoh 3: Mendapatkan semua pekerjaan yang sedang berjalan
```powershell
Get-AzAutomationJob -AutomationAccountName "Contoso17" -ResourceGroupName "ResourceGroup01" -Status "Running"
```

Perintah ini mendapatkan semua pekerjaan yang berjalan di akun Automation bernama Contoso17.

## PARAMETERS

### -AutomationAccountName
Menentukan nama akun Automation tempat cmdlet ini mendapatkan pekerjaan.

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

### -EndTime
Menentukan waktu akhir untuk pekerjaan sebagai objek **DateTimeOffset** .
Anda dapat menentukan string yang dapat dikonversi ke **DateTimeOffset** yang valid.
Cmdlet ini mendapatkan pekerjaan yang memiliki waktu akhir pada atau sebelum nilai yang ditentukan parameter ini.

```yaml
Type: System.Nullable`1[System.DateTimeOffset]
Parameter Sets: ByAll, ByRunbookName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
Menentukan ID pekerjaan yang didapatkan cmdlet ini.

```yaml
Type: System.Guid
Parameter Sets: ByJobId
Aliases: JobId

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya tempat cmdlet ini mendapatkan pekerjaan.

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
Menentukan nama runbook tempat cmdlet ini mendapatkan pekerjaan.

```yaml
Type: System.String
Parameter Sets: ByRunbookName
Aliases: Name

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StartTime
Menentukan waktu mulai pekerjaan sebagai objek **DateTimeOffset** .
Cmdlet ini mendapatkan pekerjaan yang memiliki waktu mulai pada atau setelah nilai yang ditentukan parameter ini.

```yaml
Type: System.Nullable`1[System.DateTimeOffset]
Parameter Sets: ByAll, ByRunbookName
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Status
Menentukan status pekerjaan.
Cmdlet ini mendapatkan pekerjaan yang memiliki status yang cocok dengan parameter ini.
Nilai yang valid adalah: 
- Mengaktifkan
- Selesai
- Gagal
- Dalam antrean
- Melanjutkan
- Jalankan
- Memulai
- Dihentikan
- Menghentikan
- Ditangguhkan
- Menangguhkan

```yaml
Type: System.String
Parameter Sets: ByAll, ByRunbookName
Aliases:
Accepted values: Completed, Failed, Queued, Starting, Resuming, Running, Stopped, Stopping, Suspended, Suspending, Activating

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.Guid

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Automation.Model.Job

## NOTES

## RELATED LINKS

[Get-AzAutomationJobOutput](./Get-AzAutomationJobOutput.md)

[Resume-AzAutomationJob](./Resume-AzAutomationJob.md)

[Stop-AzAutomationJob](./Stop-AzAutomationJob.md)

[Suspend-AzAutomationJob](./Suspend-AzAutomationJob.md)


