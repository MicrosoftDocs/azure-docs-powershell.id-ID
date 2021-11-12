---
external help file: Microsoft.Azure.Commands.Automation.dll-Help.xml
ms.assetid: 6527FF45-9C16-47E8-8E70-619A0581D2F8
online version: ''
schema: 2.0.0
ms.openlocfilehash: 50a80f823981bb6946e3e93f838da610b3ae964b
ms.sourcegitcommit: 6dce6f7972b2236b87b25b31465bffaad2435711
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 09/13/2021
ms.locfileid: "132426556"
---
# Get-AzureAutomationJob

## SYNOPSIS

Mendapatkan satu atau beberapa pekerjaan runbook Otomatisasi Azure.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### SecaraSemua (Default)
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

Cmdlet **Get-AzureAutomationJob** mendapatkan satu atau beberapa pekerjaan runbook dalam Microsoft Azure Otomatisasi.

## EXAMPLES

### Contoh 1: Mendapatkan pekerjaan runbook tertentu
```
PS C:\> Get-AzureAutomationJob -AutomationAccountName "Contoso17" -Id 2989b069-24fe-40b9-b3bd-cb7e5eac4b647
```

Perintah ini mendapatkan pekerjaan dengan GUID tertentu.

### Contoh 2: Mendapatkan semua pekerjaan untuk runbook
```
PS C:\> Get-AzureAutomationJob -AutomationAccountName "Contoso17" -RunbookName "MyRunbook"
```

Perintah ini mendapatkan semua pekerjaan yang terkait dengan runbook bernama MyRunbook.

### Contoh 2: Mendapatkan semua pekerjaan yang sedang berjalan
```
PS C:\> Get-AzureAutomationJob -AutomationAccountName "Contoso17" -Status "Running"
```

Perintah ini akan menjalankan semua pekerjaan dalam akun otomatisasi dengan nama Contoso17.

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
Cmdlet ini mendapatkan pekerjaan dengan status yang cocok dengan parameter ini.
Nilai valid adalah: 

- Selesai
- Gagal
- Diantrekan
- Memulai
- Melanjutkan
- Berjalan
- Dihentikan
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( https://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

## OUTPUTS

### Microsoft.Azure.Commands.Automation.Model.Job

## CATATAN

## RELATED LINKS

[Resume-AzureAutomationJob](./Resume-AzureAutomationJob.md)

[Stop-AzureAutomationJob](./Stop-AzureAutomationJob.md)

[Suspend-AzureAutomationJob](./Suspend-AzureAutomationJob.md)


