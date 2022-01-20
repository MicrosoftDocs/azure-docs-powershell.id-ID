---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/start-azsynapsedataflowdebugsession
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Start-AzSynapseDataFlowDebugSession.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Start-AzSynapseDataFlowDebugSession.md
ms.openlocfilehash: fbff49a00ba5ebc9561be4d7e82b3d1c86d80e5f
ms.sourcegitcommit: 53ef403038f665f1b3a9f616185b31f5de9bd7bb
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 11/03/2021
ms.locfileid: "136357629"
---
# Start-AzSynapseDataFlowDebugSession

## SYNOPSIS
Memulai sesi debug aliran data Analitik Synapse di Ruang Kerja Synapse.

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
Perintah yang berjalan lama ini memulai sesi debug aliran data untuk perintah debug yang akan datang. Perintah ini dapat melampirkan definisi runtime integrasi untuk mengonfigurasi ukuran/tipe kluster sesi debug.
Urutan perintah PowerShell untuk alur kerja debug aliran data harus:  
1. Start-AzSynapseDataFlowDebugSession  
2. Add-AzSynapseDataFlowDebugSessionPackage  
3. Invoke-AzSynapseDataFlowDebugSessionCommand (ulangi langkah ini untuk perintah/target yang berbeda, atau ulangi langkah 2-3 untuk mengubah file paket)  
4. Stop-AzSynapseDataFlowDebugSession  

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Start-AzSynapseDataFlowDebugSession -WorkspaceName ContosoWorkspace
```

Perintah ini memulai sesi debug aliran data Analitik Azure Synapse.

### Contoh 2
```powershell
PS C:\> $ws = Get-AzSynapseWorkspace -Workspacename ContosoWorkspace -ResourceGroupName GroupName  
PS C:\> $result = $ws | Start-AzSynapseDataFlowDebugSession  
PS C:\> $result

SessionId
---------
b75f917c-1a5e-432e-a1b9-ec6aabb1f546
```

Perintah ini memulai sesi debug aliran data Analitik Azure Synapse melalui pipeline.

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
objek input ruang kerja, biasanya melewati saluran.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSSynapseWorkspace

## OUTPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSCreateDataFlowDeflowSessionResponse

## CATATAN

## RELATED LINKS
