---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Automation.dll-Help.xml
Module Name: Az.Automation
ms.assetid: 2DC97415-D59A-428E-8FFE-56B17B320DAF
online version: https://docs.microsoft.com/powershell/module/az.automation/new-azautomationmodule
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Automation/Automation/help/New-AzAutomationModule.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Automation/Automation/help/New-AzAutomationModule.md
ms.openlocfilehash: b5042fedc412314f9cdfd2012b52f9f175c03c08
ms.sourcegitcommit: e109cc5320478db6aa8a52d49996b133007a65b9
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 01/12/2022
ms.locfileid: "136711765"
---
# New-AzAutomationModule

## SYNOPSIS
Mengimpor modul ke dalam Otomatisasi.

## SYNTAX

```
New-AzAutomationModule [-Name] <String> [-ContentLinkUri] <Uri> [-ResourceGroupName] <String>
 [-AutomationAccountName] <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzAutomationModule** mengimpor modul ke Azure Automation.
Perintah ini menerima file terkompresi yang memiliki .zip nama file.
File berisi folder yang menyertakan file yang merupakan salah satu tipe berikut ini: 
- Windows PowerShell ini, yang memiliki ekstensi nama file .psm1 .dll 
- Windows PowerShell manifes modul, yang memiliki ekstensi nama file .psd1 Nama file .zip, nama folder, dan nama file dalam folder harus sama.
Tentukan file .zip sebagai URL yang bisa diakses oleh layanan Otomatisasi.
Jika Anda mengimpor modul Windows PowerShell ke Otomatisasi dengan menggunakan cmdlet ini atau cmdlet Set-AzAutomationModule, operasinya adalah asinkron.
Perintah menyelesaikan apakah impor berhasil atau gagal.
Untuk memeriksa apakah properti berhasil, jalankan perintah berikut: ModuleName Periksa properti `PS C:\\\> $ModuleInstance = Get-AzAutomationModule -Name ` **ProvisioningState** untuk nilai Berhasil.

## EXAMPLES

### Contoh 1: Mengimpor modul
```
PS C:\>New-AzAutomationModule -AutomationAccountName "Contoso17" -Name "ContosoModule" -ContentLink "http://contosostorage.blob.core.windows.net/modules/ContosoModule.zip" -ResourceGroupName "ResourceGroup01"
```

Perintah ini mengimpor modul yang bernama ContosoModule ke akun Otomatisasi yang bernama Contoso17.
Modul ini disimpan di Azure blob dalam akun penyimpanan yang bernama contosostorage dan wadah yang bernama modul.

## PARAMETERS

### -AutomationAccountName
Menentukan nama akun Otomatisasi yang akan diimpor cmdlet ini modul.

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
Url ke paket zip modul

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases: ContentLink

Required: True
Position: 3
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
Menentukan nama grup sumber daya yang akan diimpor cmdlet ini.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters ( http://go.microsoft.com/fwlink/?LinkID=113216) .

## INPUTS

### System.String

### System.Uri

## OUTPUTS

### Microsoft.Azure.Commands.Automation.Model.Module

## CATATAN

## RELATED LINKS

[Get-AzAutomationModule](./Get-AzAutomationModule.md)

[Remove-AzAutomationModule](./Remove-AzAutomationModule.md)

[Set-AzAutomationModule](./Set-AzAutomationModule.md)


