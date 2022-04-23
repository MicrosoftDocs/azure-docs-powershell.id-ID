---
external help file: Microsoft.Azure.Commands.Automation.dll-Help.xml
ms.assetid: 7B2D9768-919B-4F54-BBC7-8882CC2C973A
online version: ''
schema: 2.0.0
ms.openlocfilehash: 3fc7c4138722e0f95fc4542f2a6ac3f97302605f
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143212211"
---
# Get-AzureAutomationAccount

## SYNOPSIS

Mendapatkan akun Azure Automation.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Get-AzureAutomationAccount [-Name <String>] [-Location <String>] [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION

[!INCLUDE [aa-deprecation](../include/aa-deprecation.md)]

Cmdlet **Get-AzureAutomationAccount** mendapatkan akun Microsoft Azure Otomatisasi untuk langganan Anda.
Akun Otomatisasi adalah wadah untuk sumber daya Otomatisasi yang diisolasi dari sumber daya akun Otomatisasi lainnya.
Sumber daya otomatisasi mencakup runbook, pekerjaan, dan aset.

## EXAMPLES

### Contoh 1: Dapatkan akun Otomatisasi
```
PS C:\> Get-AzureAutomationAccount -Name "Contoso17"
```

Perintah ini mendapatkan akun Otomatisasi bernama Contoso17.

## PARAMETERS

### -Lokasi
Menentukan lokasi Azure yang terkait dengan akun Otomatisasi.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nama
Menentukan nama akun Azure Automation.

```yaml
Type: String
Parameter Sets: (All)
Aliases: AutomationAccountName

Required: False
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

### Microsoft.Azure.Commands.Automation.Model.AutomationAccount

## NOTES

## RELATED LINKS

[AzureAutomationAccount Baru](./New-AzureAutomationAccount.md)

[Hapus-AzureAutomationAccount](./Remove-AzureAutomationAccount.md)


