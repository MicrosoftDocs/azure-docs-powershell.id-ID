---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/get-azsynapsemanagedprivateendpoint
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Get-AzSynapseManagedPrivateEndpoint.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Get-AzSynapseManagedPrivateEndpoint.md
ms.openlocfilehash: 3690cbdc78340d7ec43a99181113bbe0e8036e16
ms.sourcegitcommit: 7e47562b11e670049c3a18af7498414da853a921
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 02/09/2022
ms.locfileid: "138291660"
---
# Get-AzSynapseManagedPrivateEndpoint

## SYNOPSIS
Mendapatkan informasi tentang titik akhir privat manang dalam ruang kerja

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
Cmdlet **Get-AzSynapseManagedPrivateEndpoint** mendapatkan informasi tentang titik akhir privat manang dalam ruang kerja. Jika Anda menentukan nama titik akhir privat mananged, cmdlet akan mendapatkan informasi tentang titik akhir privat mananged tersebut. Jika Anda tidak menentukan nama, cmdlet akan mendapatkan informasi tentang semua titik akhir privat manang dalam ruang kerja.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Get-AzSynapseManagedPrivateEndpoint -WorkspaceName ContosoWorkspace -Name ContosoManagedPrivateEndpoint
```

Mendapatkan titik akhir privat tunggal yang disebut ContosoManagedPrivateEndpoint di ruang kerja ContosoWorkspace.

### Contoh 2
```powershell
PS C:\> Get-AzSynapseManagedPrivateEndpoint -WorkspaceName ContosoWorkspace
```

Mendapatkan daftar semua titik akhir privat manang di ruang kerja ContosoWorkspace.

### Contoh 3
```powershell
PS C:\> $ws = Get-AzSynapseWorkspace -Name ContosoWorkspace
PS C:\> $ws | Get-AzSynapseManagedPrivateEndpoint -Name ContosoManagedPrivateEndpoint
```

Mendapatkan titik akhir privat tunggal yang disebut ContosoManagedPrivateEndpoint di ruang kerja ContosoWorkspace melalui pipeline.

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
Nama titik akhir privat yang dikelola Synapse.

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
Managed Virtual Network Name is default.

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
objek input ruang kerja, biasanya melewati saluran.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSSynapseWorkspace

## OUTPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSManagedPrivateEndpointResource

## CATATAN

## RELATED LINKS
