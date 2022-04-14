---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/get-azsynapsepipelinerun
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Get-AzSynapsePipelineRun.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Get-AzSynapsePipelineRun.md
ms.openlocfilehash: b1b9e5936304304aec3f140a74ff72fb954e51fc
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141988986"
---
# Get-AzSynapsePipelineRun

## SYNOPSIS
Mendapatkan informasi tentang jalur pipa yang berjalan.

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
Perintah **Get-AzSynapsePipelineRun** mengembalikan informasi tentang jalankan untuk saluran yang ditentukan. Jika PipelineRunId ditentukan, pipelineRunId memperlihatkan detail untuk dijalankan dengan ID tersebut. Jika PipelineRunId tidak ditentukan, pipelineRunId memperlihatkan informasi tentang semua alur yang terjadi antara nilai RunStartedAfter dan RunStartedBefore.

## EXAMPLES

### Contoh 1: Dapatkan pipeline yang dijalankan oleh ID
```powershell
Get-AzSynapsePipelineRun -WorkspaceName ContosoWorkspace -PipelineRunId "61eb095a-fe23-4591-8a97-fade6c65ca72"
```

Perintah ini mendapatkan detail tentang pipeline run dengan ID "61eb095a-fe23-4591-8a97-fade6c65ca72".

### Contoh 2: Mendapatkan pipeline berjalan di antara tanggal
```powershell
$ws = Get-AzSynapseWorkspace -Name ContosoWorkspace
$ws | Get-AzSynapsePipelineRun -RunStartedAfter "4/2/2007 7:23:57 PM" -RunStartedBefore "4/2/2027 7:23:57 PM"
```

Perintah ini mendapatkan detail tentang jalannya semua saluran di ruang kerja ContosoWorkspace yang dimulai antara "4/2/2007 7:23:57 PM" dan "4/2/2027 19:23:57 PM"

### Contoh 3: Mendapatkan satu pipeline berjalan di antara tanggal
```powershell
Get-AzSynapsePipelineRun -WorkspaceName ContosoWorkspace -Name ContosoPipeline -RunStartedAfter "4/2/2007 7:23:57 PM" -RunStartedBefore "4/2/2027 7:23:57 PM"
```

Perintah ini mendapatkan detail tentang alur ContosoPipeline dalam ruang kerja ContosoWorkspace yang dimulai antara "4/2/2007 7:23:57 PM" dan "4/2/2027 7:23:57 PM"

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
Pengidentifikasi proses saluran.

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
Waktu pada atau setelah acara jalankan diperbarui dalam format 'ISO 8601'.

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
Waktu pada atau sebelum acara jalankan diperbarui dalam format 'ISO 8601'.

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

### -Nama Ruang Kerja
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSSynapseWorkspace

## OUTPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSPipelineRun

## CATATAN

## RELATED LINKS
