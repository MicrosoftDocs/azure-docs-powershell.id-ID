---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/get-azsynapsepipelinerun
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Get-AzSynapsePipelineRun.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Get-AzSynapsePipelineRun.md
ms.openlocfilehash: 54ec1c3cd03a6fe06317818bb215fc1b13512b2b
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144649894"
---
# Get-AzSynapsePipelineRun

## SYNOPSIS
Mendapatkan informasi tentang eksekusi alur.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.synapse/get-azsynapsepipelinerun) untuk informasi terbaru.

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
Perintah **Get-AzSynapsePipelineRun** mengembalikan informasi tentang eksekusi untuk alur yang ditentukan. Jika PipelineRunId ditentukan, pipelineRunId akan menampilkan detail untuk eksekusi dengan ID tersebut. Jika PipelineRunId tidak ditentukan, maka pipelineRunId menunjukkan informasi tentang semua eksekusi untuk alur yang terjadi antara nilai RunStartedAfter dan RunStartedBefore.

## EXAMPLES

### Contoh 1: Dapatkan eksekusi alur berdasarkan ID
```powershell
Get-AzSynapsePipelineRun -WorkspaceName ContosoWorkspace -PipelineRunId "61eb095a-fe23-4591-8a97-fade6c65ca72"
```

Perintah ini mendapatkan detail tentang eksekusi alur dengan ID "61eb095a-fe23-4591-8a97-fade6c65ca72".

### Contoh 2: Mendapatkan alur yang berjalan di antara tanggal
```powershell
$ws = Get-AzSynapseWorkspace -Name ContosoWorkspace
$ws | Get-AzSynapsePipelineRun -RunStartedAfter "4/2/2007 7:23:57 PM" -RunStartedBefore "4/2/2027 7:23:57 PM"
```

Perintah ini mendapatkan detail tentang eksekusi semua alur di ruang kerja ContosoWorkspace yang dimulai antara "4/2/2007 7:23:57 PM" dan "4/2/2027 19:23:57 PM"

### Contoh 3: Mendapatkan eksekusi alur tunggal di antara tanggal
```powershell
Get-AzSynapsePipelineRun -WorkspaceName ContosoWorkspace -Name ContosoPipeline -RunStartedAfter "4/2/2007 7:23:57 PM" -RunStartedBefore "4/2/2027 7:23:57 PM"
```

Perintah ini mendapatkan detail tentang eksekusi alur ContosoPipeline di ruang kerja ContosoWorkspace yang dimulai antara "4/2/2007 7:23:57 PM" dan "4/2/2027 7:23:57 PM"

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
Nama alur.

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
Pengidentifikasi eksekusi alur.

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
Waktu pada atau setelah peristiwa eksekusi diperbarui dalam format 'ISO 8601'.

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
Waktu pada atau sebelum peristiwa eksekusi diperbarui dalam format 'ISO 8601'.

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
objek input ruang kerja, biasanya melewati alur.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSSynapseWorkspace

## OUTPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSPipelineRun

## NOTES

## RELATED LINKS
