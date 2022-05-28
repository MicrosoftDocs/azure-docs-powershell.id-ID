---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/get-azsynapsemanagedprivateendpoint
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Get-AzSynapseManagedPrivateEndpoint.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Get-AzSynapseManagedPrivateEndpoint.md
ms.openlocfilehash: 87632330ae0fdac9e2244127115d412be1f62993
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145562882"
---
# Get-AzSynapseManagedPrivateEndpoint

## SYNOPSIS
Mendapatkan informasi tentang titik akhir privat yang dimanangi di ruang kerja

## SYNTAX

### GetByName (Default)
```
Get-AzSynapseManagedPrivateEndpoint -WorkspaceName <String> [-Name <String>] [-VirtualNetworkName <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### GetByObject
```
Get-AzSynapseManagedPrivateEndpoint -WorkspaceObject <PSSynapseWorkspace> [-Name <String>]
 [-VirtualNetworkName <String>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzSynapseManagedPrivateEndpoint** mendapatkan informasi tentang titik akhir privat yang dimanangi di ruang kerja. Jika Anda menentukan nama titik akhir privat yang termanang, cmdlet mendapatkan informasi tentang titik akhir privat yang termanang. Jika Anda tidak menentukan nama, cmdlet mendapatkan informasi tentang semua titik akhir privat yang dimanangi di ruang kerja.

## EXAMPLES

### Contoh 1
```powershell
Get-AzSynapseManagedPrivateEndpoint -WorkspaceName ContosoWorkspace -Name ContosoManagedPrivateEndpoint
```

Mendapatkan satu titik akhir privat termanang yang disebut ContosoManagedPrivateEndpoint di ruang kerja ContosoWorkspace.

### Contoh 2
```powershell
Get-AzSynapseManagedPrivateEndpoint -WorkspaceName ContosoWorkspace
```

Mendapatkan daftar semua titik akhir privat yang dimanangi di ruang kerja ContosoWorkspace.

### Contoh: 3
```powershell
$ws = Get-AzSynapseWorkspace -Name ContosoWorkspace
$ws | Get-AzSynapseManagedPrivateEndpoint -Name ContosoManagedPrivateEndpoint
```

Mendapatkan satu titik akhir privat termanang yang disebut ContosoManagedPrivateEndpoint di ruang kerja ContosoWorkspace melalui alur.

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
Nama Titik Akhir Privat Terkelola Synapse.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: ManagedPrivateEndpointName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -VirtualNetworkName
Nama Virtual Network Terkelola adalah default.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: VNetName

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

### Microsoft.Azure.Commands.Synapse.Models.PSManagedPrivateEndpointResource

## NOTES

## RELATED LINKS
