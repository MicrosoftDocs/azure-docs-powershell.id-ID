---
external help file: Microsoft.Azure.Commands.Automation.dll-Help.xml
ms.assetid: C69558DB-78C3-4162-99C3-1300C3FE5287
online version: ''
schema: 2.0.0
ms.openlocfilehash: 9c321f672095a415067b4d62f44c3621370f08de
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142245817"
---
# Get-AzureAutomationCredential

## SYNOPSIS

Mendapatkan kredensial Azure Automation.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

### ByAll (Default)
```
Get-AzureAutomationCredential -AutomationAccountName <String> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

### ByName
```
Get-AzureAutomationCredential -Name <String> -AutomationAccountName <String> [-Profile <AzureSMProfile>]
 [<CommonParameters>]
```

## DESCRIPTION

[!INCLUDE [aa-deprecation](../include/aa-deprecation.md)]

Cmdlet **Get-AzureAutomationCredential** mendapatkan satu atau beberapa kredensial Otomatisasi Microsoft Azure.
Secara default, semua kredensial dikembalikan.
Untuk mendapatkan kredensial tertentu, tentukan namanya.

## EXAMPLES

### Contoh 1: Dapatkan semua kredensial
```
PS C:\> Get-AzureAutomationCredential -AutomationAccountName "Contoso17"
```

Perintah ini mendapatkan semua kredensial di akun Otomatisasi bernama Contoso17.

### Contoh 2: Mendapatkan kredensial
```
PS C:\> Get-AzureAutomationCredential -AutomationAccountName "Contoso17" -Name "MyCredential"
```

Perintah ini mendapatkan kredensial bernama MyCredential.

## PARAMETERS

### -AutomationAccountName
Menentukan nama akun otomatisasi dengan kredensial untuk diambil.

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
Menentukan nama kredensial untuk diambil.

```yaml
Type: String
Parameter Sets: ByName
Aliases: 

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

### Microsoft.Azure.Commands.Automation.Model.CredentialInfo

## CATATAN

## RELATED LINKS

[AzureAutomationCredential Baru](./New-AzureAutomationCredential.md)

[Hapus-AzureAutomationCredential](./Remove-AzureAutomationCredential.md)

[Set-AzureAutomationCredential](./Set-AzureAutomationCredential.md)


