---
external help file: Microsoft.Azure.Commands.Automation.dll-Help.xml
ms.assetid: 1F875179-E3CA-4BBB-822A-600777B2D980
online version: ''
schema: 2.0.0
ms.openlocfilehash: b8b88a85e024898dedfae51309c0d75d7a603819
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142278205"
---
# New-AzureAutomationModule

## SYNOPSIS

Mengimpor modul ke Dalam Otomatisasi.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
New-AzureAutomationModule -Name <String> -ContentLink <Uri> [-Tags <IDictionary>]
 -AutomationAccountName <String> [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION

[!INCLUDE [aa-deprecation](../include/aa-deprecation.md)]

Cmdlet **New-AzureAutomationModule** mengimpor modul ke Azure Automation.
Modul adalah file yang dipadatkan, dengan ekstensi .zip, yang berisi folder yang menyertakan salah satu tipe file berikut:

- Modul Windows PowerShell (file psm1). 

- Manifes modul Windows PowerShell (file psd1). 

- Perakitan (file dll).

Nama file zip, folder dalam file zip, dan file dalam folder (.psm1, psd.1, atau .dll) harus cocok.

## EXAMPLES

### Contoh 1: Mengimpor modul
```
PS C:\> New-AzureAutomationModule -AutomationAccountName "Contoso17" -Name "ContosoModule" -ContentLink "http://contosostorage.blob.core.windows.net/modules/ContosoModule.zip"
```

Perintah ini mengimpor modul bernama ContosoModule ke akun Otomatisasi bernama Contoso17.
Modul disimpan dalam blob Azure di akun penyimpanan bernama contosostorage dan kontainer bernama modul.

## PARAMETERS

### -AutomationAccountName
Menentukan nama akun Otomatisasi tempat modul akan disimpan.

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

### -ContentLink
URL publik seperti situs web atau penyimpanan blob Azure yang menentukan jalur ke file modul.
Lokasi ini harus dapat diakses secara publik.

```yaml
Type: Uri
Parameter Sets: (All)
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Nama
Menentukan nama untuk modul.

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

### -Tags
Menentukan satu atau beberapa tag yang terkait dengan modul.

```yaml
Type: IDictionary
Parameter Sets: (All)
Aliases: Tag

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

### Microsoft.Azure.Commands.Automation.Model.Module

## CATATAN

## RELATED LINKS

[Get-AzureAutomationModule](./Get-AzureAutomationModule.md)

[Hapus-AzureAutomationModule](./Remove-AzureAutomationModule.md)

[Set-AzureAutomationModule](./Set-AzureAutomationModule.md)


