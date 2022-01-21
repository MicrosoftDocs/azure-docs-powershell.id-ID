---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
module name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/get-azsynapseworkspacekey
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Get-AzSynapseWorkspaceKey.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Get-AzSynapseWorkspaceKey.md
ms.openlocfilehash: a457a139e1c202e2dd0dec234d2aa7aeda9c9290
ms.sourcegitcommit: 579224f3f35e223624deb694bceb0033c84a5856
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 12/07/2021
ms.locfileid: "136543325"
---
# Get-AzSynapseWorkspaceKey

## SYNOPSIS
Mendapatkan kunci ruang kerja.

## SYNTAX

### GetByNameParameterSet (Default)
```
Get-AzSynapseWorkspaceKey [-ResourceGroupName <String>] -WorkspaceName <String> [-Name <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### GetByParentObjectParameterSet
```
Get-AzSynapseWorkspaceKey [-Name <String>] -WorkspaceObject <PSSynapseWorkspace>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### GetByResourceIdParameterSet
```
Get-AzSynapseWorkspaceKey -ResourceId <String> [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzSynapseWorkspaceKey** mendapatkan kunci ruang kerja.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Get-AzSynapseWorkspaceKey -WorkspaceName ContosoWorkspace
```

Perintah ini mendapatkan informasi tentang semua kunci ruang kerja dalam ruang kerja bernama ContosoWorkspace.

### Contoh 2
```powershell
PS C:\> Get-AzSynapseWorkspaceKey -WorkspaceName ContosoWorkspace -Name ContosoWorkspaceKey
```

Perintah ini mendapatkan informasi tentang kunci ruang kerja bernama ContosoWorkspaceKey dalam ruang kerja yang bernama ContosoWorkspace.

### Contoh 3
```powershell
PS C:\> $ws = Get-AzSynapseWorkspace -Name ContosoWorkspace
PS C:\> $ws | Get-AzSynapseWorkspaceKey -Name ContosoWorkspaceKey
```

Perintah ini mendapatkan informasi tentang kunci ruang kerja bernama ContosoWorkspaceKey dalam ruang kerja yang bernama ContosoWorkspace melalui pipeline.

### Contoh 4
```powershell
PS C:\> Get-AzSynapseSqlPool -ResourceId "/subscriptions/21686af7-58ec-4f4d-9c68-f431f4db4edd/resourceGroups/ContosoResourceGroup/providers/Microsoft.Synapse/workspaces/ContosoWorkspace/keys/ContosoWorkspaceKey"
```

Perintah ini akan memasukkan kunci ruang kerja dengan ID sumber daya yang ditentukan.

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
Nama kunci enkripsi ruang kerja.

```yaml
Type: System.String
Parameter Sets: GetByNameParameterSet, GetByParentObjectParameterSet
Aliases: KeyName

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
Parameter Sets: GetByNameParameterSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResourceId
Pengidentifikasi sumber daya dari Synapse SQL Pool.

```yaml
Type: System.String
Parameter Sets: GetByResourceIdParameterSet
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
Parameter Sets: GetByNameParameterSet
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
Parameter Sets: GetByParentObjectParameterSet
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

### Microsoft.Azure.Commands.Synapse.Models.WorkspaceKey.PSWorkspaceKey

## CATATAN

## RELATED LINKS
