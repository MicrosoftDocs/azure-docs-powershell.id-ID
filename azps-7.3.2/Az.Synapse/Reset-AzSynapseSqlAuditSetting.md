---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/reset-azsynapsesqlauditsetting
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Reset-AzSynapseSqlAuditSetting.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Reset-AzSynapseSqlAuditSetting.md
ms.openlocfilehash: 888611dcfa943758ee5cf05007df113fd5fbbebe
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143322011"
---
# Reset-AzSynapseSqlAuditSetting

## SYNOPSIS
Menghapus pengaturan pengaudungan Azure Synapse Ruang Kerja Analitik.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.synapse/reset-azsynapsesqlauditsetting) untuk informasi terbaru.

## SYNTAX

### WorkspaceParameterSet (Default)
```
Reset-AzSynapseSqlAuditSetting [[-ResourceGroupName] <String>] [-WorkspaceName] <String> [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Ruang KerjaObjectParameterSet
```
Reset-AzSynapseSqlAuditSetting -WorkspaceObject <PSSynapseWorkspace> [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### Ruang KerjaResourceIdParameterSetName
```
Reset-AzSynapseSqlAuditSetting -ResourceId <String> [-AsJob] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Pengaturan Ulang-AzSynapseSqlAuditSetting** menghapus pengaturan pengauditan ruang kerja analitik Azure Synapse.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Reset-AzSynapseSqlAuditSetting -WorkspaceName ContosoWorkspace
```

Perintah ini menghapus pengaturan audit ruang kerja analitik Azure Synapse bernama ContosoWorkspace.

### Contoh 2
```powershell
PS C:\> Get-AzSynapseWorkspace -Name ContosoWorkspace | Reset-AzSynapseSqlAuditSetting
```

Perintah ini menghapus pengaturan audit ruang kerja analitik Azure Synapse bernama ContosoWorkspace melalui pipeline.

## PARAMETERS

### -AsJob
Menjalankan cmdlet di latar belakang

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

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: WorkspaceParameterSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
Pengidentifikasi sumber daya ruang kerja Synapse.

```yaml
Type: System.String
Parameter Sets: WorkspaceResourceIdParameterSetName
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
Parameter Sets: WorkspaceParameterSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WorkspaceObject
objek input ruang kerja, biasanya melewati saluran.

```yaml
Type: Microsoft.Azure.Commands.Synapse.Models.PSSynapseWorkspace
Parameter Sets: WorkspaceObjectParameterSet
Aliases: InputObject

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSSynapseWorkspace

## OUTPUTS

### System.Boolean

## NOTES

## RELATED LINKS
