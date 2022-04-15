---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/get-azsynapserolescope
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Get-AzSynapseRoleScope.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Get-AzSynapseRoleScope.md
ms.openlocfilehash: e59eb39853b4814fbd8ecd34129044aeff85e163
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142164354"
---
# Get-AzSynapseRoleScope

## SYNOPSIS
Mendapatkan lingkup peran Analitik Synapse.

## SYNTAX

### GetByWorkspaceNameParameterSet (Default)
```
Get-AzSynapseRoleScope -WorkspaceName <String> [-ResourceId <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### GetByWorkspaceObjectParameterSet
```
Get-AzSynapseRoleScope -WorkspaceObject <PSSynapseWorkspace> [-ResourceId <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzSynapseRoleScope** mendapatkan Lingkup Peran Analitik Azure Synapse.

## EXAMPLES

### Contoh 1
```powershell
Get-AzSynapseRoleScope -WorkspaceName ContosoWorkspace
```

Perintah ini mendapatkan semua lingkup peran di bawah ruang kerja.

### Contoh 2
```powershell
$ws = Get-AzSynapseWorkspace -Name ContosoWorkspace
$ws | Get-AzSynapseRoleScope
```

Perintah ini mendapatkan semua lingkup peran di bawah ruang kerja melalui saluran.

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

### -ResourceId
Pengidentifikasi sumber daya ruang kerja Synapse.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama Ruang Kerja
Nama ruang kerja Synapse.

```yaml
Type: System.String
Parameter Sets: GetByWorkspaceNameParameterSet
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
Parameter Sets: GetByWorkspaceObjectParameterSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSSynapseWorkspace

## OUTPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSSynapseRole

## CATATAN

## RELATED LINKS
