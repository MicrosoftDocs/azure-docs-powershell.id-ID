---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/set-azsynapsesparkjobdefinition
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Set-AzSynapseSparkJobDefinition.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Set-AzSynapseSparkJobDefinition.md
ms.openlocfilehash: a35d92094c7605ce6ade50861331cdab0f5460bd
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145525435"
---
# Set-AzSynapseSparkJobDefinition

## SYNOPSIS
Membuat definisi kerja Spark di ruang kerja.

## SYNTAX

### SetByName (Default)
```
Set-AzSynapseSparkJobDefinition -WorkspaceName <String> -Name <String> -DefinitionFile <String>
 [-FolderPath <String>] [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### SetByObject
```
Set-AzSynapseSparkJobDefinition -WorkspaceObject <PSSynapseWorkspace> -Name <String> -DefinitionFile <String>
 [-FolderPath <String>] [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzSynapseSparkJobDefinition** membuat definisi kerja Spark di ruang kerja.

## EXAMPLES

### Contoh 1
```powershell
Set-AzSynapseSparkJobDefinition -WorkspaceName ContosoWorkspace -Name ContosoSparkJobDefinition -DefinitionFile "C:\sparkJobDefinition.json"
```

Perintah ini membuat definisi kerja Spark bernama ContosoSparkJobDefinition di ruang kerja bernama ContosoWorkspace.
Perintah mendasarkan definisi kerja Spark pada informasi dalam file sparkJobDefinition.json.

### Contoh 2
```powershell
Set-AzSynapseSparkJobDefinition -WorkspaceName ContosoWorkspace -Name ContosoSparkJobDefinition -DefinitionFile "C:\sparkJobDefinition.json" -FolderPath ContosoFolder
```

Perintah ini membuat definisi kerja Spark bernama ContosoSparkJobDefinition dan menentukan jalur folder ContosoFolder tempat definisi kerja spark akan ditempatkan di ruang kerja bernama ContosoWorkspace.
Perintah mendasarkan definisi kerja Spark pada informasi dalam file sparkJobDefinition.json.

### Contoh: 3
```powershell
Set-AzSynapseSparkJobDefinition -WorkspaceName ContosoWorkspace -Name ContosoSparkJobDefinition -DefinitionFile "C:\sparkJobDefinition.json" -FolderPath ContosoFolder/SubFolder
```

Perintah ini membuat definisi kerja Spark bernama ContosoSparkJobDefinition dan menentukan jalur folder multi-level ContosoFolder/SubFolder tempat definisi kerja spark akan ditempatkan di ruang kerja bernama ContosoWorkspace.
Perintah mendasarkan definisi kerja Spark pada informasi dalam file sparkJobDefinition.json.

### Contoh 4
```powershell
$ws = Get-AzSynapseWorkspace -Name ContosoWorkspace
$ws | Set-AzSynapseSparkJobDefinition -Name ContosoSparkJobDefinition -DefinitionFile "C:\sparkJobDefinition.json"
```

Perintah ini membuat definisi kerja Spark bernama ContosoSparkJobDefinition di ruang kerja bernama ContosoWorkspace melalui alur.
Perintah mendasarkan definisi kerja Spark pada informasi dalam file sparkJobDefinition.json.

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

### -FolderPath
Folder tempat definisi kerja Spark ini berada. Jika menentukan jalur multi-level seperti [rootFolder/subFolder], definisi kerja Spark akan muncul di tingkat bawah. Jika tidak ditentukan, definisi kerja Spark ini akan muncul di tingkat akar.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Nama definisi kerja Spark.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: SparkJobDefinitionName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WorkspaceName
Nama ruang kerja Synapse.

```yaml
Type: System.String
Parameter Sets: SetByName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WorkspaceObject
objek input ruang kerja, biasanya melewati alur.

```yaml
Type: Microsoft.Azure.Commands.Synapse.Models.PSSynapseWorkspace
Parameter Sets: SetByObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSSynapseWorkspace

## OUTPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSSparkJobDefinitionResource

## NOTES

## RELATED LINKS
