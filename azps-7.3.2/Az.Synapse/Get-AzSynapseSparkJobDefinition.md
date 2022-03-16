---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/get-azsynapsesparkjobdefinition
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Get-AzSynapseSparkJobDefinition.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Get-AzSynapseSparkJobDefinition.md
ms.openlocfilehash: 06a42ccc1c32bcf0d30fadaa52e7557d23c2104d
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "139998085"
---
# Get-AzSynapseSparkJobDefinition

## SYNOPSIS
Mendapatkan definisi pekerjaan Grafik Spark di ruang kerja.

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
Cmdlet **Get-AzSynapseSparkJobDefinition** mendapatkan informasi tentang definisi pekerjaan Grafik Spark di ruang kerja. Jika Anda menentukan nama definisi pekerjaan Grafik Apik, cmdlet ini mendapatkan informasi tentang definisi pekerjaan Spark tersebut. Jika Anda tidak menentukan nama, cmdlet ini mendapatkan informasi tentang semua definisi Pekerjaan grafik apik di dalam ruang kerja.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Get-AzSynapseSparkJobDefinition -WorkspaceName ContosoWorkspace
```

Perintah ini mendapatkan informasi tentang semua definisi pekerjaan Spark di ruang kerja bernama ContosoWorkspace.

### Contoh 2
```powershell
PS C:\> Get-AzSynapseSparkJobDefinition -WorkspaceName ContosoWorkspace -Name ContosoJobDefinition
```

Perintah ini mendapatkan informasi tentang definisi pekerjaan Grafik Apik yang bernama ContosoSparkJobDefinition di ruang kerja yang bernama ContosoWorkspace.

### Contoh 3
```powershell
PS C:\> $ws = Get-AzSynapseWorkspace -Name ContosoWorkspace
PS C:\> $ws | Get-AzSynapseSparkJobDefinition -Name ContosoSparkJobDefinition
```

Perintah ini mendapatkan informasi tentang definisi pekerjaan Grafik Apik yang bernama ContosoSparkJobDefinition di ruang kerja yang bernama ContosoWorkspace melalui pipeline.

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

### -Nama
Nama definisi pekerjaan Grafik Apik.

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
objek input ruang kerja, biasanya melewati saluran.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSSynapseWorkspace

## OUTPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSSparkJobDefinitionResource

## CATATAN

## RELATED LINKS
