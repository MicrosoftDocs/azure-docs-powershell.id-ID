---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/get-azsynapsetriggerrun
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Get-AzSynapseTriggerRun.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Get-AzSynapseTriggerRun.md
ms.openlocfilehash: 152a40651a46dbbe5d7f7e668ef628017c11c6d1
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136187147"
---
# Get-AzSynapseTriggerRun

## SYNOPSIS
Mengembalikan informasi tentang pemicu yang dijalankan.

## SYNTAX

### GetByName (Default)
```
Get-AzSynapseTriggerRun -WorkspaceName <String> -Name <String> -RunStartedAfter <DateTimeOffset>
 -RunStartedBefore <DateTimeOffset> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### GetByObject
```
Get-AzSynapseTriggerRun -WorkspaceObject <PSSynapseWorkspace> -Name <String> -RunStartedAfter <DateTimeOffset>
 -RunStartedBefore <DateTimeOffset> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Perintah **Get-AzSynapseTriggerRun mengembalikan** informasi mendetail tentang pemicu yang dijalankan untuk pemicu yang ditentukan dalam jangka waktu yang ditentukan.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Get-AzSynapseTriggerRun -WorkspaceName ContosoWorkspace -Name ContosoTrigger -RunStartedAfter "2018-09-01T21:00" -RunStartedBefore "2019-09-01T21:00"
```

Perintah ini memperlihatkan informasi tentang berjalan untuk ContosoTrigger di ruang kerja ContosoWorkspace yang dimulai antara "2018-09-01T21:00" dan "2019-09-01T21:00".

### Contoh 2
```powershell
PS C:\> $ws = Get-AzSynapseWorkspace -Name ContosoWorkspace
PS C:\> $ws | Get-AzSynapseTriggerRun -Name ContosoTrigger -RunStartedAfter "2018-09-01T21:00" -RunStartedBefore "2019-09-01T21:00"
```

Perintah ini memperlihatkan informasi tentang berjalan untuk ContosoTrigger di ruang kerja ContosoWorkspace yang dimulai antara "2018-09-01T21:00" dan "2019-09-01T21:00" melalui pipeline.

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
Nama pemicu.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: TriggerName

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
Parameter Sets: (All)
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
Parameter Sets: (All)
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSSynapseWorkspace

## OUTPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSTriggerRun

## CATATAN

## RELATED LINKS
