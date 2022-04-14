---
external help file: Microsoft.Azure.Commands.Automation.dll-Help.xml
ms.assetid: 436A6D6E-2280-475C-A1F5-6A6D72DAD9E7
online version: ''
schema: 2.0.0
ms.openlocfilehash: b24d3379b64160c7b0d05bbac4a38bd923beb81b
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141922335"
---
# Get-AzureAutomationSchedule

## SYNOPSIS

Mendapatkan jadwal Azure Automation.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### ByAll (Default)
```
Get-AzureAutomationSchedule -AutomationAccountName <String> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### ByName
```
Get-AzureAutomationSchedule -Name <String> -AutomationAccountName <String> [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION

[!INCLUDE [aa-deprecation](../include/aa-deprecation.md)]

Cmdlet **Get-AzureAutomationSchedule** mendapatkan jadwal Otomatisasi Microsoft Azure.

## EXAMPLES

### Contoh 1: Dapatkan jadwal
```
PS C:\> Get-AzureAutomationSchedule -AutomationAccountName "Contoso17" -Name "DailySchedule08"
```

Perintah ini mendapatkan jadwal yang bernama DailySchedule08.

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

### -Nama
Menentukan nama jadwal.

```yaml
Type: String
Parameter Sets: ByName
Aliases: ScheduleName

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.Commands.Automation.Model.Schedule

## CATATAN

## RELATED LINKS

[AzureAutomationSchedule Baru](./New-AzureAutomationSchedule.md)

[Hapus-AzureAutomationSchedule](./Remove-AzureAutomationSchedule.md)

[Atur-AzureAutomationSchedule](./Set-AzureAutomationSchedule.md)


