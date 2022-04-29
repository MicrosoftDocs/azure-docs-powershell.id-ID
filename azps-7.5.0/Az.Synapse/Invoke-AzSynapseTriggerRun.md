---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/invoke-azsynapsetriggerrun
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Invoke-AzSynapseTriggerRun.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Invoke-AzSynapseTriggerRun.md
ms.openlocfilehash: 4973b744689bd6cea6c458df112a274bc283ee3e
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144247401"
---
# Invoke-AzSynapseTriggerRun

## SYNOPSIS
Memanggil instans lain dari eksekusi pemicu.

## SYNTAX

### InvokeByName (Default)
```
Invoke-AzSynapseTriggerRun -WorkspaceName <String> -Name <String> -TriggerRunId <String> [-PassThru]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InvokByInputObject
```
Invoke-AzSynapseTriggerRun -InputObject <PSTriggerRun> [-PassThru] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### InvokeByWorkspaceObject
```
Invoke-AzSynapseTriggerRun -WorkspaceObject <PSSynapseWorkspace> -Name <String> -TriggerRunId <String>
 [-PassThru] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Perintah Invoke-AzSynapseTriggerRun memulai instans lain dari eksekusi pemicu dengan id eksekusi pemicu baru.

## EXAMPLES

### Contoh 1
```powershell
Invoke-AzSynapseTriggerRun -WorkspaceName ContosoWorkspace -Name ContosoTrigger -TriggerRunId 000111222333abc
```

Memulai instans lain dari eksekusi pemicu dengan id eksekusi pemicu baru, mempertahankan windowStartTime dan windowEndTime yang sama dengan eksekusi pemicu asli.

### Contoh 2
```powershell
$ws = Get-AzSynapseWorkspace -Name ContosoWorkspace
$ws | Invoke-AzSynapseTriggerRun -Name ContosoTrigger -TriggerRunId 000111222333abc
```

Memulai instans lain dari eksekusi pemicu dengan id eksekusi pemicu baru di ruang kerja Synapse ContosoWorkspace melalui alur.

### Contoh 3
```powershell
$triggerun = Get-AzSynapseTriggerRun -WorkspaceName ContosoWorkspace -Name ContosoTrigger -RunStartedAfter "2018-09-01T21:00" -RunStartedBefore "2019-09-01T21:00"
$triggerun | Invoke-AzSynapseTriggerRun
```

Memulai instans lain dari eksekusi pemicu dengan id eksekusi pemicu baru di ruang kerja Synapse ContosoWorkspace melalui alur.

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
Informasi tentang eksekusi pemicu.

```yaml
Type: Microsoft.Azure.Commands.Synapse.Models.PSTriggerRun
Parameter Sets: InvokByInputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Nama pemicu.

```yaml
Type: System.String
Parameter Sets: InvokeByName, InvokeByWorkspaceObject
Aliases: TriggerName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Cmdlet ini tidak mengembalikan objek secara default. Jika sakelar ini ditentukan, sakelar akan mengembalikan true jika berhasil.

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
ID Eksekusi pemicu.

```yaml
Type: System.String
Parameter Sets: InvokeByName, InvokeByWorkspaceObject
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
Parameter Sets: InvokeByName
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
Parameter Sets: InvokeByWorkspaceObject
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

### Microsoft.Azure.Commands.Synapse.Models.PSTriggerRun

### Microsoft.Azure.Commands.Synapse.Models.PSSynapseWorkspace

## OUTPUTS

### System.Boolean

## NOTES

## RELATED LINKS
