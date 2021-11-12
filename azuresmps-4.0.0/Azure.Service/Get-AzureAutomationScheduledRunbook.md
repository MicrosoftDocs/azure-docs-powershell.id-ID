---
external help file: Microsoft.Azure.Commands.Automation.dll-Help.xml
ms.assetid: 2F66B0F2-37F3-4046-9FB0-B8C4B90D84A3
online version: ''
schema: 2.0.0
ms.openlocfilehash: d8c8da3745d398dd2acdd6c8bf3564eafadda6329cbedd724f0377c362a020de
ms.sourcegitcommit: 49f8ffe5d8e08ba3d22e3b2e76db0e54dd55d4f0
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 08/11/2021
ms.locfileid: "132418979"
---
# Get-AzureAutomationScheduledRunbook

## SYNOPSIS

Mendapatkan runbooks Azure Automation dan jadwal terkait.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### SecaraSemua (Default)
```
Get-AzureAutomationScheduledRunbook -AutomationAccountName <String> [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

### ByJobScheduleId
```
Get-AzureAutomationScheduledRunbook -JobScheduleId <Guid> -AutomationAccountName <String>
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### ByRunbookName
```
Get-AzureAutomationScheduledRunbook -RunbookName <String> -AutomationAccountName <String>
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### ByRunbookNameAndScheduleName
```
Get-AzureAutomationScheduledRunbook -RunbookName <String> -ScheduleName <String>
 -AutomationAccountName <String> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### ByScheduleName
```
Get-AzureAutomationScheduledRunbook -ScheduleName <String> -AutomationAccountName <String>
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION

[!INCLUDE [aa-deprecation](../include/aa-deprecation.md)]

**Get-AzureAutomationScheduledRunbook** mendapatkan satu atau beberapa runbooks Azure Automation dan jadwal terkait.
Secara default, semua runbooks terjadwal akan dikembalikan.

Untuk mendapatkan buku runbook terjadwal tertentu, tentukan nama runbook dan nama jadwal.
Untuk mendapatkan semua jadwal yang terkait dengan runbook, tentukan hanya nama runbook.
Untuk mendapatkan semua runbooks yang terkait dengan jadwal, tentukan nama jadwal saja.

## EXAMPLES

### Contoh 1: Dapatkan semua runbooks terjadwal
```
PS C:\> Get-AzureAutomationScheduledRunbook -AutomationAccountName "Contoso17"
```

Perintah ini mendapatkan semua runbooks terjadwal dalam akun Otomatisasi bernama Contoso17.

### Contoh 2: Mendapatkan semua jadwal yang terkait dengan runbook
```
PS C:\> Get-AzureAutomationScheduledRunbook -AutomationAccountName "Contoso17" -RunbookName "Runbk01"
```

Perintah ini mendapatkan semua runbooks terjadwal untuk runbook Runbk01 dalam akun Otomatisasi yang bernama Contoso17.

### Contoh 3: Mendapatkan semua runbooks yang terkait dengan jadwal
```
PS C:\> Get-AzureAutomationScheduledRunbook -AutomationAccountName "Contoso17" -ScheduleName "Schedule01"
```

Perintah ini mendapatkan semua runbooks terjadwal untuk jadwal Schedule01 dalam akun Otomatisasi yang bernama Contoso17.

## PARAMETERS

### -AutomationAccountName
Menentukan nama akun Otomatisasi Azure.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -JobScheduleId
Menentukan ID pekerjaan yang dijadwalkan.

```yaml
Type: Guid
Parameter Sets: ByJobScheduleId
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Profil
Menentukan profil Azure yang akan dibaca cmdlet ini.
Jika Anda tidak menentukan profil, cmdlet ini akan membaca dari profil default lokal.

```yaml
Type: AzureSMProfile
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunbookName
Menentukan nama runbook.

```yaml
Type: String
Parameter Sets: ByRunbookName, ByRunbookNameAndScheduleName
Aliases: Name

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ScheduleName
Menentukan nama jadwal.

```yaml
Type: String
Parameter Sets: ByRunbookNameAndScheduleName, ByScheduleName
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

### Microsoft.Azure.Commands.Automation.Model.JobSchedule

## CATATAN

## RELATED LINKS

[Register-AzureAutomationScheduledRunbook](./Register-AzureAutomationScheduledRunbook.md)

[Unregister-AzureAutomationScheduledRunbook](./Unregister-AzureAutomationScheduledRunbook.md)


