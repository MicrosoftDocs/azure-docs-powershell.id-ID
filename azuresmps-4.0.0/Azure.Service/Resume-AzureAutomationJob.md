---
external help file: Microsoft.Azure.Commands.Automation.dll-Help.xml
ms.assetid: 5E5B8102-9E7E-4128-8160-3AA3803B118F
online version: ''
schema: 2.0.0
ms.openlocfilehash: f74e33822d2e175b0c04caa638606294ca6cd356
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142915949"
---
# Resume-AzureAutomationJob

## SYNOPSIS

Melanjutkan tugas Otomatisasi yang ditangguhkan.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Resume-AzureAutomationJob -Id <Guid> -AutomationAccountName <String> [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION

[!INCLUDE [aa-deprecation](../include/aa-deprecation.md)]

Cmdlet **Resume-AzureAutomationJob** melanjutkan pekerjaan Microsoft Azure Otomatisasi yang ditangguhkan.
Gunakan parameter *Id* untuk menentukan pekerjaan yang ditangguhkan.

Untuk menangguhkan pekerjaan, gunakan cmdlet Suspend-AzureAutomationJob.

## EXAMPLES

### Contoh 1: Melanjutkan pekerjaan yang ditangguhkan
```
PS C:\> Resume-AzureAutomationJob -AutomationAccountName "Contoso17" -Id 2989b069-24fe-40b9-b3bd-cb7e5eac4b64
```

Perintah ini melanjutkan pekerjaan yang memiliki ID yang ditentukan.

## PARAMETERS

### -AutomationAccountName
Menentukan nama akun Otomatisasi.

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

### -Id
Menentukan ID pekerjaan.

```yaml
Type: Guid
Parameter Sets: (All)
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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## NOTES

## RELATED LINKS

[Get-AzureAutomationJob](./Get-AzureAutomationJob.md)

[Stop-AzureAutomationJob](./Stop-AzureAutomationJob.md)

[Suspend-AzureAutomationJob](./Suspend-AzureAutomationJob.md)


