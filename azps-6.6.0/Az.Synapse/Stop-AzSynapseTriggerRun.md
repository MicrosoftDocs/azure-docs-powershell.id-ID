---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/stop-azsynapsetriggerrun
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Stop-AzSynapseTriggerRun.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Stop-AzSynapseTriggerRun.md
ms.openlocfilehash: 029b85b7f89ee092415ab603659f4a89ce56bb7d
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140129211"
---
# Stop-AzSynapseTriggerRun

## SYNOPSIS
Menghentikan pemicu yang dijalankan di ruang kerja synapse.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan [lihat versi terbaru](/powershell/module/az.synapse/stop-azsynapsetriggerrun) untuk informasi terkini.

## SYNTAX

### StopByName (Default)
```
Stop-AzSynapseTriggerRun -WorkspaceName <String> -Name <String> -TriggerRunId <String> [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### StopByInputObject
```
Stop-AzSynapseTriggerRun -InputObject <PSTriggerRun> [-PassThru] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### StopByWorkspaceObject
```
Stop-AzSynapseTriggerRun -WorkspaceObject <PSSynapseWorkspace> -Name <String> -TriggerRunId <String>
 [-PassThru] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet Stop-AzSynapseTriggerRun menghentikan pemicu dijalankan di ruang kerja synapse yang ditentukan dengan nama pemicu dan ID jalankan pemicu. Saat ini hanya didukung untuk TumblingWindowTriggers dalam WaitingOnDependency State.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Stop-AzSynapseTriggerRun -WorkspaceName ContosoWorkspace -Name ContosoTrigger -TriggerRunId 000111222333abc
```

Perintah ini menghentikan pemicu dijalankan dengan id '00011122333abc' di ruang kerja Synapse ContosoWorkspace.

### Contoh 2
```powershell
PS C:\> $ws = Get-AzSynapseWorkspace -Name ContosoWorkspace
PS C:\> $ws | Stop-AzSynapseTriggerRun -Name ContosoTrigger -TriggerRunId 000111222333abc
```

Menghentikan pemicu dijalankan dengan id '000111222333abc' di ruang kerja Synapse ContosoWorkspace melalui pipeline.

### Contoh 3
```powershell
PS C:\> $triggerun = Get-AzSynapseTriggerRun -WorkspaceName ContosoWorkspace -Name ContosoTrigger -RunStartedAfter "2018-09-01T21:00" -RunStartedBefore "2019-09-01T21:00"
PS C:\> $triggerun | Stop-AzSynapseTriggerRun
```

Menghentikan pemicu dijalankan di ruang kerja Synapse ContosoWorkspace melalui saluran.

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

### -InputObject
Informasi mengenai pemicu berjalan.

```yaml
Type: Microsoft.Azure.Commands.Synapse.Models.PSTriggerRun
Parameter Sets: StopByInputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Nama
Nama pemicu.

```yaml
Type: System.String
Parameter Sets: StopByName, StopByWorkspaceObject
Aliases: TriggerName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Cmdlet ini tidak mengembalikan objek secara default. Jika sakelar ini ditentukan, maka true akan dikembalikan jika berhasil.

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

### -TriggerRunId
Id Jalankan dari pemicu.

```yaml
Type: System.String
Parameter Sets: StopByName, StopByWorkspaceObject
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
Parameter Sets: StopByName
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
Parameter Sets: StopByWorkspaceObject
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSTriggerRun

### Microsoft.Azure.Commands.Synapse.Models.PSSynapseWorkspace

## OUTPUTS

### System.Boolean

## CATATAN

## RELATED LINKS
