---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Automation.dll-Help.xml
Module Name: Az.Automation
ms.assetid: A06D36D7-3F72-4D21-8995-9DBBB9A9B880
online version: https://docs.microsoft.com/powershell/module/az.automation/set-azautomationmodule
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Automation/Automation/help/Set-AzAutomationModule.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Automation/Automation/help/Set-AzAutomationModule.md
ms.openlocfilehash: 765389f6f9ba0ad72577f781a36aae14094633a8
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140557839"
---
# Set-AzAutomationModule

## SYNOPSIS
Memperbarui modul dalam Otomatisasi.

## SYNTAX

```
Set-AzAutomationModule [-Name] <String> [-ContentLinkUri <Uri>] [-ContentLinkVersion <String>]
 [-ResourceGroupName] <String> [-AutomationAccountName] <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzAutomationModule** memperbarui modul di Azure Automation.
Perintah ini menerima file terkompresi yang memiliki .zip nama file.
File berisi folder yang menyertakan file yang merupakan salah satu tipe berikut ini: 
- wps_2 baru, yang memiliki ekstensi nama file .psm1 .dll atau yang lebih baru 
- wps_2 manifes modul, yang memiliki ekstensi nama file .psd1 Nama file .zip, nama folder, dan nama file dalam folder harus sama.
Tentukan file .zip sebagai URL yang bisa diakses oleh layanan Otomatisasi.
Jika Anda mengimpor modul wps_2 ke otomatisasi dengan menggunakan cmdlet ini atau cmdlet New-AzAutomationModule, operasinya adalah asinkron.
Perintah menyelesaikan apakah impor berhasil atau gagal.
Untuk memeriksa apakah properti berhasil, jalankan perintah berikut: `PS C:\\\> $ModuleInstance = Get-AzAutomationModule -Name `ModuleName Periksa properti **ProvisioningState** untuk nilai Berhasil.

## EXAMPLES

### Contoh 1: Memperbarui modul
```
PS C:\>Set-AzAutomationModule -AutomationAccountName "Contoso17" -Name "ContosoModule" -ContentLinkUri "http://contosostorage.blob.core.windows.net/modules/ContosoModule.zip" -ContentLinkVersion "1.1" -ResourceGroupName "ResourceGroup01"
```

Perintah ini mengimpor versi terbaru modul yang sudah ada yang bernama ContosoModule ke akun Otomatisasi yang bernama Contoso17.  Modul ini disimpan di Azure blob dalam akun penyimpanan yang bernama contosostorage dan wadah yang bernama modul.

## PARAMETERS

### -AutomationAccountName
Menentukan nama akun Otomatisasi yang akan diperbarui cmdlet ini.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ContentLinkUri
Menentukan URL file .zip yang berisi versi modul baru yang diimpor cmdlet ini.

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases: ContentLink

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ContentLinkVersion
Menentukan versi modul tempat cmdlet memperbarui Otomatisasi.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Menentukan nama modul yang diimpor cmdlet ini.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya di mana cmdlet ini memperbarui modul.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

### System.Uri

## OUTPUTS

### Microsoft.Azure.Commands.Automation.Model.Module

## CATATAN

## RELATED LINKS

[Get-AzAutomationModule](./Get-AzAutomationModule.md)

[New-AzAutomationModule](./New-AzAutomationModule.md)

[Remove-AzAutomationModule](./Remove-AzAutomationModule.md)


