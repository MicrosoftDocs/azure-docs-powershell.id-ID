---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/en-us/powershell/module/az.synapse/stop-azsynapsepipelinerun
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Synapse/Synapse/help/Stop-AzSynapsePipelineRun.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/master/src/Synapse/Synapse/help/Stop-AzSynapsePipelineRun.md
ms.openlocfilehash: f907afbc573d558a08d514c019cbcbe3fa999bf6
ms.sourcegitcommit: b4a38bcb0501a9016a4998efd377aa75d3ef9ce8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 10/27/2020
ms.locfileid: "132407155"
---
# Stop-AzSynapsePipelineRun

## SYNOPSIS
Menghentikan jalannya saluran di ruang kerja.

## SINTAKS

### RemoveByName (Default)
```
Stop-AzSynapsePipelineRun -WorkspaceName <String> -PipelineRunId <String> [-PassThru] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### RemoveByObject
```
Stop-AzSynapsePipelineRun -WorkspaceObject <PSSynapseWorkspace> -PipelineRunId <String> [-PassThru] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### RemoveByInputObject
```
Stop-AzSynapsePipelineRun -InputObject <PSPipelineRun> [-PassThru] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESKRIPSI
Cmdlet **Stop-AzSynapsePipelineRun** menghentikan proses pipeline dalam ruang kerja yang ditentukan dengan ID berjalannya pipeline.

## CONTOH

### Contoh 1
```powershell
PS C:\> Stop-AzSynapsePipelineRun -WorkspaceName ContosoWorkspace -PipelineRunId b9730a13-aa12-4926-a8b3-8e3a974ab0bd
```

Perintah ini menghentikan pipeline yang dijalankan dengan id b9730a13-aa12-4926-a8b3-8e3a974ab0bd di ruang kerja ContosoWorkspace.

### Contoh 2
```powershell
PS C:\> $ws = Get-AzSynapseWorkspace -Name ContosoWorkspace
PS C:\> $ws | Stop-AzSynapsePipelineRun -PipelineRunId b9730a13-aa12-4926-a8b3-8e3a974ab0bd
```

Perintah ini menghentikan proses pipeline dengan id b9730a13-aa12-4926-a8b3-8e3a974ab0bd di ruang kerja ContosoWorkspace melalui pipeline.

### Contoh 3
```powershell
PS C:\> $pipelineRun = Get-AzSynapsePipelineRun -WorkspaceName ContosoWorkspace -PipelineRunId b9730a13-aa12-4926-a8b3-8e3a974ab0bd
PS C:\> $pipelineRun | Stop-AzSynapsePipelineRun
```

Perintah ini menghentikan proses pipeline dengan id b9730a13-aa12-4926-a8b3-8e3a974ab0bd di ruang kerja ContosoWorkspace melalui pipeline.

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

### -InputObject
Informasi tentang saluran berjalan.

```yaml
Type: Microsoft.Azure.Commands.Synapse.Models.PSPipelineRun
Parameter Sets: RemoveByInputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -PassThru
Cmdlet ini tidak mengembalikan objek secara default.
Jika sakelar ini ditentukan, maka true akan dikembalikan jika berhasil.

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

### -PipelineRunId
Pengidentifikasi saluran berjalan.

```yaml
Type: System.String
Parameter Sets: RemoveByName, RemoveByObject
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
Parameter Sets: RemoveByName
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
Parameter Sets: RemoveByObject
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

## INPUT

### Microsoft.Azure.Commands.Synapse.Models.PSSynapseWorkspace

### Microsoft.Azure.Commands.Synapse.Models.PSPipelineRun

## OUTPUT

### System.Boolean

## CATATAN

## LINK TERKAIT
