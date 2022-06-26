---
external help file: Microsoft.Azure.Commands.ResourceManager.Automation.dll-Help.xml
Module Name: AzureRM.Automation
ms.assetid: 32CF9BF7-519F-4B5D-9F2B-3CC556A77A48
online version: https://docs.microsoft.com/en-us/powershell/module/azurerm.automation/start-azurermautomationdsccompilationjob
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Automation/Commands.Automation/help/Start-AzureRmAutomationDscCompilationJob.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/preview/src/ResourceManager/Automation/Commands.Automation/help/Start-AzureRmAutomationDscCompilationJob.md
ms.openlocfilehash: 4cfcd5574e86e1a3750b09ebe433ce9614dde5f1
ms.sourcegitcommit: 5df8b100721844736630242c724da453a2168434
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 06/26/2022
ms.locfileid: "146610490"
---
# Start-AzureRmAutomationDscCompilationJob

## SYNOPSIS
Mengompilasi konfigurasi DSC di Automation.

[!INCLUDE [migrate-to-az-banner](../../includes/migrate-to-az-banner.md)]

## SYNTAX

```
Start-AzureRmAutomationDscCompilationJob [-ConfigurationName] <String> [-Parameters <IDictionary>]
 [-ConfigurationData <IDictionary>] [-ResourceGroupName] <String> [-AutomationAccountName] <String>
 [-DefaultProfile <IAzureContextContainer>] [-IncrementNodeConfigurationBuild] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Start-AzureRmAutomationDscCompilationJob** mengkompilasi konfigurasi APS Desired State Configuration (DSC) di Azure Automation.

## EXAMPLES

### Contoh 1: Mengompilasi konfigurasi Azure DSC di Automation
```
PS C:\>$Params = @{"StringParam"="Hello World";"IntegerParam"=32}
PS C:\> Start-AzureRmAutomationDscCompilationJob -ConfigurationName "Config01" -Parameters $Params -ResourceGroupName "ResourceGroup01"
```

Perintah pertama membuat kamus parameter, dan menyimpannya dalam variabel $Params.
Perintah kedua mengkompilasi konfigurasi DSC bernama Config01.
Perintah ini menyertakan nilai dalam $Params untuk parameter konfigurasi DSC.

### Contoh 2: Kompilasi konfigurasi Azure DSC di Automation dengan versi build Konfigurasi Simpul baru.
```
PS C:\>$Params = @{"StringParam"="Hello World";"IntegerParam"=32}
PS C:\> Start-AzureRmAutomationDscCompilationJob -ConfigurationName "Config01" -Parameters $Params -ResourceGroupName "ResourceGroup01" -IncrementNodeConfigurationBuild
```

Mirip dengan contoh pertama, perintah pertama membuat kamus parameter, dan menyimpannya dalam variabel $Params.
Perintah kedua mengkompilasi konfigurasi DSC bernama Config01.
Perintah ini menyertakan nilai dalam $Params untuk parameter konfigurasi DSC.
Ini tidak mengambil alih Konfigurasi Simpul yang ada sebelumnya dengan membuat Konfigurasi Simpul baru dengan nama `Config01[<2>].<NodeName>`.
Nomor versi ditambahkan berdasarkan nomor versi yang sudah ada.

## PARAMETERS

### -AutomationAccountName
Menentukan nama akun Automation yang berisi konfigurasi DSC yang dikompilasi cmdlet ini.

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

### -ConfigurationData
Menentukan kamus data konfigurasi untuk konfigurasi DSC.

```yaml
Type: System.Collections.IDictionary
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ConfigurationName
Menentukan nama konfigurasi DSC yang dikompilasi cmdlet ini.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: Name

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan azure

```yaml
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -IncrementNodeConfigurationBuild
Membuat versi build Konfigurasi Simpul baru.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### -Parameters
Menentukan kamus parameter yang digunakan cmdlet ini untuk mengkompilasi konfigurasi DSC.

```yaml
Type: System.Collections.IDictionary
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceGroupName
Menentukan nama grup sumber daya tempat cmdlet ini mengkompilasi konfigurasi.

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

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Menunjukkan yang akan terjadi jika cmdlet dijalankan. Cmdlet tidak dijalankan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat about_CommonParameters (https://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Automation.Model.CompilationJob

## NOTES

## RELATED LINKS

[Get-AzureRmAutomationDscCompilationJob](./Get-AzureRmAutomationDscCompilationJob.md)

[Get-AzureRmAutomationDscCompilationJobOutput](./Get-AzureRmAutomationDscCompilationJobOutput.md)


