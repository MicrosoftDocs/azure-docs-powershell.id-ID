---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/get-azsynapsemanagedidentitysqlcontrolsetting
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Get-AzSynapseManagedIdentitySqlControlSetting.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Get-AzSynapseManagedIdentitySqlControlSetting.md
ms.openlocfilehash: 2634c1c030704625c4d0fffc17942398ba4419cf
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144223667"
---
# Get-AzSynapseManagedIdentitySqlControlSetting

## SYNOPSIS
Mendapatkan Pengaturan Kontrol Sql Identitas Terkelola.

## SYNTAX

### ByNameParameterSet (Default)
```
Get-AzSynapseManagedIdentitySqlControlSetting [-ResourceGroupName <String>] -WorkspaceName <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByParentObjectParameterSet
```
Get-AzSynapseManagedIdentitySqlControlSetting -WorkspaceObject <PSSynapseWorkspace>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ByResourceIdParameterSet
```
Get-AzSynapseManagedIdentitySqlControlSetting -ResourceId <String> [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzSynapseManagedIdentitySqlControlSetting** mendapatkan identitas terkelola SQL pengaturan kontrol ruang kerja Azure Synapse Analytics.

## EXAMPLES

### Contoh 1
```powershell
Get-AzSynapseManagedIdentitySqlControlSetting -WorkspaceName ContosoWorkspace
```

Perintah ini mendapatkan pengaturan kontrol SQL identitas terkelola untuk ruang kerja.

### Contoh 2
```powershell
$ws = Get-AzSynapseWorkspace -Name ContosoWorkspace
$ws | Get-AzSynapseManagedIdentitySqlControlSetting
```

Perintah ini mendapatkan pengaturan kontrol SQL identitas terkelola untuk ruang kerja melalui alur.

### Contoh 3
```powershell
Get-AzSynapseManagedIdentitySqlControlSetting -ResourceId '/subscriptions/21686af7-58ec-4f4d-9c68-f431f4db4edd3/resourcegroups/ContosoResourceGroup/providers/Microsoft.Synapse/workspaces/ContosoWorkspace'
```

Perintah ini mendapatkan pengaturan kontrol SQL identitas terkelola untuk ruang kerja melalui ID sumber daya ruang kerja.

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
Parameter Sets: ByNameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
Pengidentifikasi sumber daya ruang kerja Synapse.

```yaml
Type: System.String
Parameter Sets: ByResourceIdParameterSet
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
Parameter Sets: ByNameParameterSet
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
Parameter Sets: ByParentObjectParameterSet
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

### Microsoft.Azure.Commands.Synapse.Models.PSManagedIdentitySqlControlSettingsModel

## NOTES

## RELATED LINKS
