---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/get-azsynapsesqlpoolauditsetting
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Get-AzSynapseSqlPoolAuditSetting.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Get-AzSynapseSqlPoolAuditSetting.md
ms.openlocfilehash: ee07f5a929d2617f9cefadef7fba6ab339b20582
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144209954"
---
# Get-AzSynapseSqlPoolAuditSetting

## SYNOPSIS
Mendapatkan pengaturan audit kumpulan SQL Azure Synapse Analytics.

## SYNTAX

### SqlPoolParameterSet (Default)
```
Get-AzSynapseSqlPoolAuditSetting [[-ResourceGroupName] <String>] [-WorkspaceName] <String>
 -SqlPoolName <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### SqlPoolParentObjectParameterSet
```
Get-AzSynapseSqlPoolAuditSetting -WorkspaceObject <PSSynapseWorkspace> -SqlPoolName <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### SqlPoolObjectParameterSet
```
Get-AzSynapseSqlPoolAuditSetting -SqlPoolObject <PSSynapseSqlPool> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### SqlPoolResourceIdParameterSet
```
Get-AzSynapseSqlPoolAuditSetting -ResourceId <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzSynapseSqlPoolAuditSetting** mendapatkan pengaturan audit kumpulan SQL Analitik Azure Synapse.

## EXAMPLES

### Contoh 1
```powershell
Get-AzSynapseSqlPoolAuditSetting -WorkspaceName ContosoWorkspace -Name ContosoSqlPool
```

Perintah ini mendapatkan pengaturan audit kumpulan SQL yang disebut ContosoSqlPool di ruang kerja ContosoWorkspace.

### Contoh 2
```powershell
Get-AzSynapseSqlPool -WorkspaceName ContosoWorkspace -Name ContosoSqlPool | Get-AzSynapseSqlPoolAuditSetting
```

Perintah ini mendapatkan pengaturan audit kumpulan SQL yang disebut ContosoSqlPool di ruang kerja ContosoWorkspace melalui alur.

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

### -ResourceGroupName
Nama grup sumber daya.

```yaml
Type: System.String
Parameter Sets: SqlPoolParameterSet
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
Pengidentifikasi sumber daya Kumpulan SQL Synapse.

```yaml
Type: System.String
Parameter Sets: SqlPoolResourceIdParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SqlPoolName
Nama kumpulan SQL Synapse.

```yaml
Type: System.String
Parameter Sets: SqlPoolParameterSet, SqlPoolParentObjectParameterSet
Aliases: Name

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SqlPoolObject
SQL objek input kumpulan, biasanya melewati alur.

```yaml
Type: Microsoft.Azure.Commands.Synapse.Models.PSSynapseSqlPool
Parameter Sets: SqlPoolObjectParameterSet
Aliases: InputObject

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -WorkspaceName
Nama ruang kerja Synapse.

```yaml
Type: System.String
Parameter Sets: SqlPoolParameterSet
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WorkspaceObject
objek input ruang kerja, biasanya melewati alur.

```yaml
Type: Microsoft.Azure.Commands.Synapse.Models.PSSynapseWorkspace
Parameter Sets: SqlPoolParentObjectParameterSet
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

### Microsoft.Azure.Commands.Synapse.Models.PSSynapseSqlPool

## OUTPUTS

### Microsoft.Azure.Commands.Synapse.Models.SqlPoolAuditModel

## NOTES

## RELATED LINKS
