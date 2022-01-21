---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/new-azsynapsesparkconfiguration
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/New-AzSynapseSparkConfiguration.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/New-AzSynapseSparkConfiguration.md
ms.openlocfilehash: b9ac5488f033a06d18293eebd1ba82ba18fe18ac
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136530188"
---
# New-AzSynapseSparkConfiguration

## SYNOPSIS
Membuat atau memperbarui konfigurasi grafik api di ruang kerja.

## SYNTAX

### CreateByName (Default)
```
New-AzSynapseSparkConfiguration -WorkspaceName <String> [-Name <String>] -DefinitionFile <String> [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### CreateByObject
```
New-AzSynapseSparkConfiguration -WorkspaceObject <PSSynapseWorkspace> [-Name <String>] -DefinitionFile <String>
 [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzSynapseSparkConfiguration** membuat atau memperbarui konfigurasi grafik api di dalam ruang kerja.
Jika Anda menentukan nama konfigurasi grafik api, konfigurasi grafik api baru akan diberi nama seperti yang ditentukan, jika Anda tidak menentukan namanya, konfigurasi grafik api baru akan menjadi nama yang sama dengan file definisi.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> New-AzSynapseSparkConfiguration -WorkspaceName ContosoWorkspace -DefinitionFile "C:\\samples\\sparkconfiguration.json"
```

Perintah ini membuat atau memperbarui konfigurasi grafik api dari file sparkconfiguration.json di ruang kerja yang bernama ContosoWorkspace.

### Contoh 2
```powershell
PS C:\> New-AzSynapseSparkConfiguration -WorkspaceName ContosoWorkspace -Name ContosoSparkConfiguration -DefinitionFile "C:\\samples\\sparkconfiguration.json"
```

Perintah ini membuat atau memperbarui konfigurasi grafik api bernama ContosoSparkConfiguration dari file sparkconfiguration.json di ruang kerja yang bernama ContosoWorkspace.

### Contoh 3
```powershell
PS C:\> $ws = Get-AzSynapseWorkspace -Name ContosoWorkspace
PS C:\> $ws | New-AzSynapseSparkConfiguration -DefinitionFile "C:\\samples\\sparkconfiguration.json"
```

Perintah ini membuat atau memperbarui konfigurasi grafik api dari file sparkconfiguration.json di ruang kerja yang bernama ContosoWorkspace melalui pipeline.

## PARAMETERS

### -AsJob
Jalankan cmdlet di latar belakang

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

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

### -DefinitionFile
Jalur file JSON.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: File

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama Konfigurasi Grafik Api.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: SparkConfigurationName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WorkspaceName
Nama ruang kerja Synapse.

```yaml
Type: System.String
Parameter Sets: CreateByName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WorkspaceObject
objek input ruang kerja, biasanya melewati saluran.

```yaml
Type: Microsoft.Azure.Commands.Synapse.Models.PSSynapseWorkspace
Parameter Sets: CreateByObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak berjalan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSSynapseWorkspace

## OUTPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSSparkConfigurationResource

## CATATAN

## RELATED LINKS
