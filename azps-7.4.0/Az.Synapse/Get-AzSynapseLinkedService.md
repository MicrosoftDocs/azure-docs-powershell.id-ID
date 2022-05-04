---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/get-azsynapselinkedservice
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Get-AzSynapseLinkedService.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Get-AzSynapseLinkedService.md
ms.openlocfilehash: 5cd62c36b0744b9d2bf724d247d225902b5cb1b7
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144621084"
---
# Get-AzSynapseLinkedService

## SYNOPSIS
Mendapatkan informasi tentang layanan tertaut di ruang kerja.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.synapse/get-azsynapselinkedservice) untuk informasi terbaru.

## SYNTAX

### GetByName (Default)
```
Get-AzSynapseLinkedService -WorkspaceName <String> [-Name <String>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### GetByObject
```
Get-AzSynapseLinkedService -WorkspaceObject <PSSynapseWorkspace> [-Name <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzSynapseLinkedService** mendapatkan informasi tentang layanan tertaut di ruang kerja.
Jika Anda menentukan nama layanan tertaut, cmdlet ini mendapatkan informasi tentang layanan tertaut tersebut.
Jika Anda tidak menentukan nama, cmdlet ini mendapatkan informasi tentang semua layanan tertaut di ruang kerja.

## EXAMPLES

### Contoh 1
```powershell
Get-AzSynapseLinkedService -WorkspaceName ContosoWorkspace
```

Perintah ini mendapatkan informasi tentang semua layanan tertaut di ruang kerja bernama ContosoWorkspace.

### Contoh 2
```powershell
Get-AzSynapseLinkedService -WorkspaceName ContosoWorkspace -Name ContosoLinkedService
```

Perintah ini mendapatkan informasi tentang layanan tertaut bernama ContosoLinkedService di ruang kerja bernama ContosoWorkspace.

### Contoh 3
```powershell
$ws = Get-AzSynapseWorkspace -Name ContosoWorkspace
$ws | Get-AzSynapseLinkedService -Name ContosoLinkedService
```

Perintah ini mendapatkan informasi tentang layanan tertaut bernama ContosoLinkedService di ruang kerja bernama ContosoWorkspace melalui alur.

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
Nama layanan tertaut.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: LinkedServiceName

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

### Microsoft.Azure.Commands.Synapse.Models.PSLinkedServiceResource

## NOTES

## RELATED LINKS
