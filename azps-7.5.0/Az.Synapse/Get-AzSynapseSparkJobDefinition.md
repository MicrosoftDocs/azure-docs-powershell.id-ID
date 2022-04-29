---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/get-azsynapsesparkjobdefinition
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Get-AzSynapseSparkJobDefinition.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Get-AzSynapseSparkJobDefinition.md
ms.openlocfilehash: e7d6dbf5130db0a033d6b5ab23538306b2b3e838
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144212783"
---
# Get-AzSynapseSparkJobDefinition

## SYNOPSIS
Mendapatkan definisi kerja Spark di ruang kerja.

## SYNTAX

### GetByName (Default)
```
Get-AzSynapseSparkJobDefinition -WorkspaceName <String> [-Name <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### GetByObject
```
Get-AzSynapseSparkJobDefinition -WorkspaceObject <PSSynapseWorkspace> [-Name <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzSynapseSparkJobDefinition** mendapatkan informasi tentang definisi kerja Spark di ruang kerja. Jika Anda menentukan nama definisi kerja Spark, cmdlet ini mendapatkan informasi tentang definisi kerja Spark tersebut. Jika Anda tidak menentukan nama, cmdlet ini mendapatkan informasi tentang semua definisi pekerjaan Spark di ruang kerja.

## EXAMPLES

### Contoh 1
```powershell
Get-AzSynapseSparkJobDefinition -WorkspaceName ContosoWorkspace
```

Perintah ini mendapatkan informasi tentang semua definisi kerja Spark di ruang kerja bernama ContosoWorkspace.

### Contoh 2
```powershell
Get-AzSynapseSparkJobDefinition -WorkspaceName ContosoWorkspace -Name ContosoJobDefinition
```

Perintah ini mendapatkan informasi tentang definisi kerja Spark bernama ContosoSparkJobDefinition di ruang kerja bernama ContosoWorkspace.

### Contoh 3
```powershell
$ws = Get-AzSynapseWorkspace -Name ContosoWorkspace
$ws | Get-AzSynapseSparkJobDefinition -Name ContosoSparkJobDefinition
```

Perintah ini mendapatkan informasi tentang definisi kerja Spark bernama ContosoSparkJobDefinition di ruang kerja bernama ContosoWorkspace melalui alur.

## PARAMETERS

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

### -Name
Nama definisi kerja Spark.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: SparkJobDefinitionName

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
Parameter Sets: GetByName
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
Parameter Sets: GetByObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
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
