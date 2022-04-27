---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/get-azsynapseworkspacepackage
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Get-AzSynapseWorkspacePackage.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Get-AzSynapseWorkspacePackage.md
ms.openlocfilehash: d01a6fd03a649ce77c08be1289828d019ea5fb1a
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144109151"
---
# Get-AzSynapseWorkspacePackage

## SYNOPSIS
Mendapatkan paket ruang kerja.

## SYNTAX

### GetByName (Default)
```
Get-AzSynapseWorkspacePackage -WorkspaceName <String> [-Name <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### GetByObject
```
Get-AzSynapseWorkspacePackage -WorkspaceObject <PSSynapseWorkspace> [-Name <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzSynapseWorkspacePackage** mendapatkan paket ruang kerja.

## EXAMPLES

### Contoh 1
```powershell
Get-AzSynapseWorkspacePackage -WorkspaceName ContosoWorkspace
```

Perintah ini mendapatkan informasi tentang semua paket ruang kerja di ruang kerja bernama ContosoWorkspace.

### Contoh 2
```powershell
Get-AzSynapseWorkspacePackage -WorkspaceName ContosoWorkspace -Name ContosoWorkspacePackage
```

Perintah ini mendapatkan informasi tentang paket ruang kerja bernama ContosoWorkspacePackage di ruang kerja bernama ContosoWorkspace.

### Contoh 3
```powershell
$ws = Get-AzSynapseWorkspace -Name ContosoWorkspace
$ws | Get-AzSynapseWorkspacePackage -Name ContosoWorkspacePackage
```

Perintah ini mendapatkan informasi tentang paket ruang kerja bernama ContosoWorkspacePackage di ruang kerja bernama ContosoWorkspace melalui alur.

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

### -Name
Nama paket ruang kerja.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: PackageName, Package

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
Parameter Sets: GetByName
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
Parameter Sets: GetByObject
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

### Microsoft.Azure.Commands.Synapse.Models.WorkspacePackages.PSSynapseWorkspacePackage

## NOTES

## RELATED LINKS
