---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/get-azsynapsemanagedprivateendpoint
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Get-AzSynapseManagedPrivateEndpoint.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Get-AzSynapseManagedPrivateEndpoint.md
ms.openlocfilehash: d7d5615023052313a32cf8903dcdeedc88345af2
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "141945807"
---
# Get-AzSynapseManagedPrivateEndpoint

## SYNOPSIS
Mendapatkan informasi tentang titik akhir privat yang dimanangi dalam ruang kerja

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.synapse/get-azsynapsemanagedprivateendpoint) untuk informasi terbaru.

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
Cmdlet **Get-AzSynapseManagedPrivateEndpoint** mendapatkan informasi tentang titik akhir pribadi yang dimanang di ruang kerja. Jika Anda menentukan nama titik akhir pribadi yang dimanang, cmdlet mendapatkan informasi tentang titik akhir pribadi yang dimanang. Jika Anda tidak menentukan nama, cmdlet mendapatkan informasi tentang semua titik akhir privat yang dimanang di ruang kerja.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Get-AzSynapseManagedPrivateEndpoint -WorkspaceName ContosoWorkspace -Name ContosoManagedPrivateEndpoint
```

Mendapatkan satu titik akhir pribadi yang dimanang yang disebut ContosoManagedPrivateEndpoint di ruang kerja ContosoWorkspace.

### Contoh 2
```powershell
PS C:\> Get-AzSynapseManagedPrivateEndpoint -WorkspaceName ContosoWorkspace
```

Mendapatkan daftar semua titik akhir privat yang dimanang di ruang kerja ContosoWorkspace.

### Contoh 3
```powershell
PS C:\> $ws = Get-AzSynapseWorkspace -Name ContosoWorkspace
PS C:\> $ws | Get-AzSynapseManagedPrivateEndpoint -Name ContosoManagedPrivateEndpoint
```

Mendapatkan satu titik akhir privat yang dimanang yang disebut ContosoManagedPrivateEndpoint di ruang kerja ContosoWorkspace melalui pipeline.

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
Nama Titik Akhir Pribadi yang Dikelola Synapse.

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
Nama Virtual Network terkelola adalah default.

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

### -Nama Ruang Kerja
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSSynapseWorkspace

## OUTPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSManagedPrivateEndpointResource

## CATATAN

## RELATED LINKS
