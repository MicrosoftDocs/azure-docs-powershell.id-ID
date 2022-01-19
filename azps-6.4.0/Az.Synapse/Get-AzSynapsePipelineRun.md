---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/get-azsynapsepipelinerun
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Get-AzSynapsePipelineRun.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Get-AzSynapsePipelineRun.md
ms.openlocfilehash: fa8746f423fa46cfdeb32ad94fa1f29f71796539
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136207713"
---
# Get-AzSynapsePipelineRun

## SYNOPSIS
Mendapatkan informasi tentang pipeline yang berjalan.

## SYNTAX

### GetByNameAndId (Default)
```
Get-AzSynapsePipelineRun -WorkspaceName <String> -PipelineRunId <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### GetByNameAndTime
```
Get-AzSynapsePipelineRun -WorkspaceName <String> -RunStartedAfter <DateTimeOffset>
 -RunStartedBefore <DateTimeOffset> [-PipelineName <String>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### GetByObjectAndId
```
Get-AzSynapsePipelineRun -WorkspaceObject <PSSynapseWorkspace> -PipelineRunId <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### GetByObjectAndTime
```
Get-AzSynapsePipelineRun -WorkspaceObject <PSSynapseWorkspace> -RunStartedAfter <DateTimeOffset>
 -RunStartedBefore <DateTimeOffset> [-PipelineName <String>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Perintah **Get-AzSynapsePipelineRun** mengembalikan informasi tentang berjalan untuk saluran yang ditentukan. Jika PipelineRunId ditentukan, id akan memperlihatkan detail untuk proses dengan ID tersebut. Jika PipelineRunId tidak ditentukan, itu memperlihatkan informasi tentang semua berjalan untuk saluran yang terjadi antara nilai RunStartedAfter dan RunStartedBefore.

## EXAMPLES

### Contoh 1: Dapatkan pipeline run by ID
```powershell
PS C:\> Get-AzSynapsePipelineRun -WorkspaceName ContosoWorkspace -PipelineRunId "61eb095a-fe23-4591-8a97-fade6c65ca72"
```

Perintah ini mendapatkan detail tentang pipeline yang dijalankan dengan ID "61eb095a-fe23-4591-8a97-fade6c65ca72".

### Contoh 2: Dapatkan saluran berjalan di antara tanggal
```powershell
PS C:\> $ws = Get-AzSynapseWorkspace -Name ContosoWorkspace
PS C:\> $ws | Get-AzSynapsePipelineRun -RunStartedAfter "4/2/2007 7:23:57 PM" -RunStartedBefore "4/2/2027 7:23:57 PM"
```

Perintah ini mendapatkan detail tentang menjalankan semua saluran di ruang kerja ContosoWorkspace yang dimulai antara "2/4/2007 7:23:57 PM" dan "4/2/2027 7:23:57 PM"

### Contoh 3: Menjalankan satu pipeline di antara tanggal
```powershell
PS C:\> Get-AzSynapsePipelineRun -WorkspaceName ContosoWorkspace -Name ContosoPipeline -RunStartedAfter "4/2/2007 7:23:57 PM" -RunStartedBefore "4/2/2027 7:23:57 PM"
```

Perintah ini mendapatkan detail tentang berjalannya saluran ContosoPipeline di ruang kerja ContosoWorkspace yang dimulai antara "2/4/2007 7:23:57 PM" dan "4/2/2027 7:23:57 PM"

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

### -PipelineName
Nama saluran.

```yaml
Type: System.String
Parameter Sets: GetByNameAndTime, GetByObjectAndTime
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PipelineRunId
Pengidentifikasi saluran berjalan.

```yaml
Type: System.String
Parameter Sets: GetByNameAndId, GetByObjectAndId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunStartedAfter
Waktu pada atau setelahnya acara jalankan diperbarui dalam format 'ISO 8601'.

```yaml
Type: System.DateTimeOffset
Parameter Sets: GetByNameAndTime, GetByObjectAndTime
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -RunStartedBefore
Waktu pada atau sebelum acara yang dijalankan diperbarui dalam format 'ISO 8601'.

```yaml
Type: System.DateTimeOffset
Parameter Sets: GetByNameAndTime, GetByObjectAndTime
Aliases:

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
Parameter Sets: GetByNameAndId, GetByNameAndTime
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
Parameter Sets: GetByObjectAndId, GetByObjectAndTime
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSSynapseWorkspace

## OUTPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSPipelineRun

## CATATAN

## RELATED LINKS
