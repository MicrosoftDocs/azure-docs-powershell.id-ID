---
external help file: Microsoft.Azure.Commands.Automation.dll-Help.xml
ms.assetid: BCF8DAB4-3E14-463B-A18F-E91C740B0D3A
online version: ''
schema: 2.0.0
ms.openlocfilehash: da5421fbfac6595e15398532879d7f40de428d58
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142093959"
---
# Remove-AzureAutomationCertificate

## SYNOPSIS

Menghapus sertifikat Otomatisasi.

[!INCLUDE [rdfe-banner](../../includes/rdfe-banner.md)]

## SYNTAX

```
Remove-AzureAutomationCertificate -Name <String> [-Force] -AutomationAccountName <String>
 [-Profile <AzureSMProfile>] [<CommonParameters>]
```

## DESCRIPTION

[!INCLUDE [aa-deprecation](../include/aa-deprecation.md)]

Cmdlet **Remove-AzureAutomationAccount** menghapus sertifikat dari Microsoft Azure Otomatisasi.

## EXAMPLES

### Contoh 1: Menghapus sertifikat
```
PS C:\> Remove-AzureAutomationCertificate -AutomationAccountName "Contoso17" -Name "Cert01"
```

Perintah ini menghapus sertifikat bernama Cert01 di akun Otomatisasi bernama Contoso17.

## PARAMETERS

### -AutomationAccountName
Menentukan nama akun Otomatisasi dengan sertifikat.

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

### -Paksa
Memaksa perintah untuk berjalan tanpa meminta konfirmasi pengguna.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: 

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Menentukan nama sertifikat.

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

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

## OUTPUTS

## CATATAN

## RELATED LINKS

[Get-AzureAutomationCertificate](./Get-AzureAutomationCertificate.md)

[AzureAutomation BaruPenerima](./New-AzureAutomationCertificate.md)

[Set-AzureAutomationCertificate](./Set-AzureAutomationCertificate.md)


