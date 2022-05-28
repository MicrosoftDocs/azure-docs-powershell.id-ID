---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Automation.dll-Help.xml
Module Name: Az.Automation
ms.assetid: A06D36D7-3F72-4D21-8995-9DBBB9A9B880
online version: https://docs.microsoft.com/powershell/module/az.automation/set-azautomationmodule
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Automation/Automation/help/Set-AzAutomationModule.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Automation/Automation/help/Set-AzAutomationModule.md
ms.openlocfilehash: 3bdfcbfb14ac3d0e59ad3ddd332f2b8ca42fa590
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145549582"
---
# Set-AzAutomationModule

## SYNOPSIS
Memperbarui modul di Automation.

## SYNTAX

```
Set-AzAutomationModule [-Name] <String> [-ContentLinkUri <Uri>] [-ContentLinkVersion <String>]
 [-ResourceGroupName] <String> [-AutomationAccountName] <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzAutomationModule** memperbarui modul dalam Azure Automation.
Perintah ini menerima file terkompresi yang memiliki ekstensi nama file .zip.
File berisi folder yang menyertakan file yang merupakan salah satu jenis berikut: 
- wps_2 modul, yang memiliki ekstensi nama file .psm1 atau .dll 
- wps_2 manifes modul, yang memiliki ekstensi nama file .psd1 Nama file .zip, nama folder, dan nama file dalam folder harus sama.
Tentukan file .zip sebagai URL yang dapat diakses oleh layanan Automation.
Jika Anda mengimpor modul wps_2 ke Automation dengan menggunakan cmdlet ini atau cmdlet New-AzAutomationModule, operasi tersebut tidak sinkron.
Perintah selesai apakah impor berhasil atau gagal.
Untuk memeriksa apakah berhasil, jalankan perintah berikut: `PS C:\\\> $ModuleInstance = Get-AzAutomationModule -Name `ModuleName Periksa properti **ProvisioningState** untuk nilai Berhasil.

## EXAMPLES

### Contoh 1: Memperbarui modul
```powershell
Set-AzAutomationModule -AutomationAccountName "Contoso17" -Name "ContosoModule" -ContentLinkUri "http://contosostorage.blob.core.windows.net/modules/ContosoModule.zip" -ContentLinkVersion "1.1" -ResourceGroupName "ResourceGroup01"
```

Perintah ini mengimpor versi terbaru dari modul yang ada bernama ContosoModule ke akun Automation bernama Contoso17.  Modul disimpan dalam blob Azure di akun penyimpanan bernama contosostorage dan kontainer bernama modul.

## PARAMETERS

### -AutomationAccountName
Menentukan nama akun Automation yang cmdlet ini memperbarui modul.

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
Menentukan URL file .zip yang berisi versi baru modul yang diimpor cmdlet ini.

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
Menentukan versi modul tempat cmdlet ini memperbarui Automation.

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
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

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

### -Name
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
Menentukan nama grup sumber daya tempat cmdlet ini memperbarui modul.

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

## NOTES

## RELATED LINKS

[Get-AzAutomationModule](./Get-AzAutomationModule.md)

[New-AzAutomationModule](./New-AzAutomationModule.md)

[Remove-AzAutomationModule](./Remove-AzAutomationModule.md)


