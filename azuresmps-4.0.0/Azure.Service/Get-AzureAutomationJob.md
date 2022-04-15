---
external help file: Microsoft.Azure.Commands.Automation.dll-Help.xml
ms.assetid: 6527FF45-9C16-47E8-8E70-619A0581D2F8
online version: ''
schema: 2.0.0
ms.openlocfilehash: 50a80f823981bb6946e3e93f838da610b3ae964b
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142313575"
---
# Get-AzureAutomationJob

## SYNOPSIS

Mendapatkan satu atau beberapa pekerjaan runbook Azure Automation.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### ByAll (Default)
```
Get-AzureAutomationJob [-Status <String>] [-StartTime <DateTimeOffset>] [-EndTime <DateTimeOffset>]
 -AutomationAccountName <String> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### ByJobId
```
Get-AzureAutomationJob -Id <Guid> -AutomationAccountName <String> [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

### ByRunbookName
```
Get-AzureAutomationJob -RunbookName <String> [-Status <String>] [-StartTime <DateTimeOffset>]
 [-EndTime <DateTimeOffset>] -AutomationAccountName <String> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION

[!INCLUDE [aa-deprecation](../include/aa-deprecation.md)]

Cmdlet **Get-AzureAutomationJob** mendapatkan satu atau beberapa pekerjaan runbook di Microsoft Azure Automation.

## EXAMPLES

### Contoh 1: Dapatkan pekerjaan runbook tertentu
```
PS C:\> Get-AzureAutomationJob -AutomationAccountName "Contoso17" -Id 2989b069-24fe-40b9-b3bd-cb7e5eac4b647
```

Perintah ini mendapatkan pekerjaan yang memiliki GUID yang ditentukan.

### Contoh 2: Dapatkan semua pekerjaan untuk runbook
```
PS C:\> Get-AzureAutomationJob -AutomationAccountName "Contoso17" -RunbookName "MyRunbook"
```

Perintah ini mendapatkan semua pekerjaan yang terkait dengan runbook bernama MyRunbook.

### Contoh 2: Dapatkan semua pekerjaan yang berjalan
```
PS C:\> Get-AzureAutomationJob -AutomationAccountName "Contoso17" -Status "Running"
```

Perintah ini mendapatkan semua pekerjaan yang berjalan di akun otomatisasi dengan nama Contoso17.

## PARAMETERS

### -AutomationAccountName
Menentukan nama akun Azure Automation.

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

### -EndTime
Menentukan waktu akhir untuk pekerjaan.

```yaml
Type: DateTimeOffset
Parameter Sets: ByAll, ByRunbookName
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Id
Menentukan ID pekerjaan.

```yaml
Type: Guid
Parameter Sets: ByJobId
Aliases: JobId

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Profil
Menentukan profil Azure tempat cmdlet ini dibaca.
Jika Anda tidak menentukan profil, cmdlet ini akan dibaca dari profil default lokal.

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
Parameter Sets: ByRunbookName
Aliases: Name

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -StartTime
Menentukan waktu mulai pekerjaan.

```yaml
Type: DateTimeOffset
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

- Selesai
- Gagal
- Antri
- Mulai
- Melanjutkan
- Menjalankan
- Berhenti
- Menghentikan
- Ditangguhkan
- Menangguhkan
- Mengaktifkan

```yaml
Type: String
Parameter Sets: ByAll, ByRunbookName
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.Commands.Automation.Model.Job

## CATATAN

## RELATED LINKS

[Resume-AzureAutomationJob](./Resume-AzureAutomationJob.md)

[Stop-AzureAutomationJob](./Stop-AzureAutomationJob.md)

[Suspend-AzureAutomationJob](./Suspend-AzureAutomationJob.md)


