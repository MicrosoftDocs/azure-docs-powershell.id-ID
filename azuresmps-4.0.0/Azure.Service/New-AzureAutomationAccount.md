---
external help file: Microsoft.Azure.Commands.Automation.dll-Help.xml
ms.assetid: 59CDE74B-EFB3-4904-A482-466B0EA17F4B
online version: ''
schema: 2.0.0
ms.openlocfilehash: c95b35d1b85da953bd4f60064e02b40ea68a38f2
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141920847"
---
# New-AzureAutomationAccount

## SYNOPSIS

Membuat akun Otomatisasi.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
New-AzureAutomationAccount -Name <String> -Location <String> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION

[!INCLUDE [aa-deprecation](../include/aa-deprecation.md)]

Cmdlet **New-AzureAutomationAccount** membuat akun baru di Microsoft Azure Automation.

## EXAMPLES

### Contoh 1: Membuat akun Otomatisasi
```
PS C:\> New-AzureAutomationAccount -Name "MyAutomationAccount" -Location "East US"
```

Perintah ini membuat akun Otomatisasi bernama MyAutomationAccount di kawasan AS Timur.

## PARAMETERS

### -Lokasi
Menentukan lokasi akun.

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
Menentukan nama akun.

```yaml
Type: String
Parameter Sets: (All)
Aliases: AutomationAccountName

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

### Microsoft.Azure.Commands.Automation.Model.AutomationAccount

## CATATAN

## RELATED LINKS

[Get-AzureAutomationAccount](./Get-AzureAutomationAccount.md)

[Hapus-AzureAutomationAccount](./Remove-AzureAutomationAccount.md)


