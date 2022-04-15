---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/new-azsynapsesparkconfiguration
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/New-AzSynapseSparkConfiguration.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/New-AzSynapseSparkConfiguration.md
ms.openlocfilehash: 008aecdc61437780d4d402196fe7f71241c012fc
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142000654"
---
# New-AzSynapseSparkConfiguration

## SYNOPSIS
Membuat atau memperbarui konfigurasi percikan api dalam ruang kerja.

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
Cmdlet **New-AzSynapseSparkConfiguration** membuat atau memperbarui konfigurasi percikan api dalam ruang kerja.
Jika Anda menentukan nama konfigurasi percikan api, konfigurasi percikan baru akan dinamai sebagai yang ditentukan, jika Anda tidak menentukan nama, konfigurasi percikan baru akan sama dengan nama file definisi.

## EXAMPLES

### Contoh 1
```powershell
New-AzSynapseSparkConfiguration -WorkspaceName ContosoWorkspace -DefinitionFile "C:\\samples\\sparkconfiguration.json"
```

Perintah ini membuat atau memperbarui konfigurasi percikan api dari file sparkconfiguration.json di ruang kerja bernama ContosoWorkspace.

### Contoh 2
```powershell
New-AzSynapseSparkConfiguration -WorkspaceName ContosoWorkspace -Name ContosoSparkConfiguration -DefinitionFile "C:\\samples\\sparkconfiguration.json"
```

Perintah ini membuat atau memperbarui konfigurasi percikan api bernama ContosoSparkConfiguration dari file sparkconfiguration.json di ruang kerja bernama ContosoWorkspace.

### Contoh 3
```powershell
$ws = Get-AzSynapseWorkspace -Name ContosoWorkspace
$ws | New-AzSynapseSparkConfiguration -DefinitionFile "C:\\samples\\sparkconfiguration.json"
```

Perintah ini membuat atau memperbarui konfigurasi percikan api dari file sparkconfiguration.json di ruang kerja bernama ContosoWorkspace melalui pipeline.

## PARAMETERS

### -AsJob
Menjalankan cmdlet di latar belakang

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
Nama Konfigurasi Spark.

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

### -Nama Ruang Kerja
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
Meminta konfirmasi sebelum menjalankan cmdlet.

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
Cmdlet tidak dijalankan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSSynapseWorkspace

## OUTPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSSparkConfigurationResource

## CATATAN

## RELATED LINKS
