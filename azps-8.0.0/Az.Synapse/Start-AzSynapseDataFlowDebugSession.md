---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/start-azsynapsedataflowdebugsession
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Start-AzSynapseDataFlowDebugSession.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Start-AzSynapseDataFlowDebugSession.md
ms.openlocfilehash: 970054ad6d8b549f5a9418a89f08eefcce4b557b
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145498029"
---
# Start-AzSynapseDataFlowDebugSession

## SYNOPSIS
Memulai sesi debug aliran data Synapse Analytics di Ruang Kerja Synapse.

## SYNTAX

### StartByName (Default)
```
Start-AzSynapseDataFlowDebugSession -WorkspaceName <String> [-IntegrationRuntimeFile <String>] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### StartByObject
```
Start-AzSynapseDataFlowDebugSession -WorkspaceObject <PSSynapseWorkspace> [-IntegrationRuntimeFile <String>]
 [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Perintah jangka panjang ini memulai sesi debug aliran data untuk perintah debug yang akan datang. Perintah ini dapat melampirkan dengan definisi runtime integrasi untuk mengonfigurasi ukuran/jenis kluster sesi debug.
Urutan perintah PowerShell untuk alur kerja debug aliran data harus:  
1. Start-AzSynapseDataFlowDebugSession  
2. Add-AzSynapseDataFlowDebugSessionPackage  
3. Invoke-AzSynapseDataFlowDebugSessionCommand (ulangi langkah ini untuk perintah/target yang berbeda, atau ulangi langkah 2-3 untuk mengubah file paket)  
4. Stop-AzSynapseDataFlowDebugSession  

## EXAMPLES

### Contoh 1
```powershell
Start-AzSynapseDataFlowDebugSession -WorkspaceName ContosoWorkspace
```

Perintah ini memulai sesi debug aliran data Azure Synapse Analytics.

### Contoh 2
```powershell
$ws = Get-AzSynapseWorkspace -Workspacename ContosoWorkspace -ResourceGroupName GroupName  
$result = $ws | Start-AzSynapseDataFlowDebugSession  
$result
```

```output
SessionId
---------
b75f917c-1a5e-432e-a1b9-ec6aabb1f546
```

Perintah ini memulai sesi debug aliran data Azure Synapse Analytics melalui alur.

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

### -IntegrationRuntimeFile
Jalur file JSON.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: File

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
Parameter Sets: StartByName
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
Parameter Sets: StartByObject
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

### Microsoft.Azure.Commands.Synapse.Models.PSSynapseWorkspace

## OUTPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSCreateDataFlowDebugSessionResponse

## NOTES

## RELATED LINKS
