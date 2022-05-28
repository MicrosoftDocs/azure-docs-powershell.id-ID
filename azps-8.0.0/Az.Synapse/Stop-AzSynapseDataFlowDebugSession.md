---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/stop-azsynapsedataflowdebugsession
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Stop-AzSynapseDataFlowDebugSession.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Stop-AzSynapseDataFlowDebugSession.md
ms.openlocfilehash: 011e3a6b55df357c7f6b70f452e7a341c7602a52
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145498060"
---
# Stop-AzSynapseDataFlowDebugSession

## SYNOPSIS
Menghentikan sesi debug aliran data di ruang kerja.

## SYNTAX

### StopByName (Default)
```
Stop-AzSynapseDataFlowDebugSession -WorkspaceName <String> -SessionId <String> [-PassThru] [-Force]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### StoptByObject
```
Stop-AzSynapseDataFlowDebugSession -WorkspaceObject <PSSynapseWorkspace> -SessionId <String> [-PassThru]
 [-Force] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Stop-AzSynapseDataFlowDebugSession** menghentikan sesi debug aliran data di ruang kerja yang ditentukan dengan SessionId.

## EXAMPLES

### Contoh 1
```powershell
Stop-AzSynapseDataFlowDebugSession -workspacename ContosoWorkspace -sessionid c744f68d-a101-4115-9cd5-8b11314fe4b8
```

```output
Confirm
Are you sure you want to stop data flow debug session 'c744f68d-a101-4115-9cd5-8b11314fe4b8' in workspace 'ContosoWorkspace'?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): y
```

Perintah ini menghentikan sesi debug aliran data "c744f68d-a101-4115-9cd5-8b11314fe4b8" di ruang kerja ContosoWorkspace.

### Contoh 2
```powershell
$ws = Get-AzSynapseWorkspace -Name ContosoWorkspace -ResourceGroupName ContosoGroup
$ws | Stop-AzSynapseDataFlowDebugSession -sessionid c744f68d-a101-4115-9cd5-8b11314fe4b8
```

```output
Confirm
Are you sure you want to stop data flow debug session 'c744f68d-a101-4115-9cd5-8b11314fe4b8' in workspace 'ContosoWorkspace'?
[Y] Yes  [N] No  [S] Suspend  [?] Help (default is "Y"): y
```

Perintah ini menghentikan sesi debug aliran data "c744f68d-a101-4115-9cd5-8b11314fe4b8" melalui alur.

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

### -Force
Jangan meminta konfirmasi.

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

### -PassThru
Cmdlet ini tidak mengembalikan objek secara default.
Jika sakelar ini ditentukan, sakelar akan mengembalikan true jika berhasil.

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

### -SessionId
Pengidentifikasi sesi Spark.

```yaml
Type: System.String
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
Parameter Sets: StopByName
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
Parameter Sets: StoptByObject
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
Menunjukkan yang akan terjadi jika cmdlet dijalankan. Cmdlet tidak dijalankan.

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

### System.Boolean

## NOTES

## RELATED LINKS
