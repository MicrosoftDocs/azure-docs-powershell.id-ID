---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/get-azsynapselinkconnectionlinktable
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Get-AzSynapseLinkConnectionLinkTable.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Get-AzSynapseLinkConnectionLinkTable.md
ms.openlocfilehash: e2d60a0922349d4a51e2660968c98d78c81359e6
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145541826"
---
# Get-AzSynapseLinkConnectionLinkTable

## SYNOPSIS
Mendapatkan informasi tentang tabel tautan di bawah koneksi tautan.

## SYNTAX

### GetByName (Default)
```
Get-AzSynapseLinkConnectionLinkTable -WorkspaceName <String> -LinkConnectionName <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### GetByObject
```
Get-AzSynapseLinkConnectionLinkTable -WorkspaceObject <PSSynapseWorkspace> -LinkConnectionName <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### GetByInputObject
```
Get-AzSynapseLinkConnectionLinkTable -InputObject <PSLinkConnectionResource>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzSynapseLinkConnectionLinkTable** mendapatkan informasi tentang tabel tautan di bawah koneksi tautan.

## EXAMPLES

### Contoh 1
```powershell
Get-AzSynapseLinkConnectionLinkTable -WorkspaceName ContosoWorkspace -LinkConnectionName ContosoLinkConnection
```

Perintah ini mendapatkan informasi tentang tabel tautan di bawah koneksi tautan ContosoLinkConnection di ruang kerja ContosoWorkspace.

### Contoh 2
```powershell
$ws = Get-AzSynapseWorkspace -Name ContosoWorkspace
$ws | Get-AzSynapseLinkConnectionLinkTable -LinkConnectionName ContosoLinkConnection
```

Perintah ini mendapatkan informasi tentang tabel tautan di bawah koneksi tautan ContosoLinkConnection di ruang kerja ContosoWorkspace melalui alur.

### Contoh: 3
```powershell
$lc = Get-AzSynpaseLinkConnection -WorkspaceName ContosoWorkspace -Name ContosoLinkConnection
$lc | Get-AzSynapseLinkConnectionLinkTable
```

Perintah ini mendapatkan informasi tentang tabel tautan di bawah koneksi tautan melalui alur.

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

### -InputObject
Informasi tentang koneksi tautan.

```yaml
Type: Microsoft.Azure.Commands.Synapse.Models.PSLinkConnectionResource
Parameter Sets: GetByInputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -LinkConnectionName
Nama koneksi tautan.

```yaml
Type: System.String
Parameter Sets: GetByName, GetByObject
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

### Microsoft.Azure.Commands.Synapse.Models.PSLinkConnectionResource

## OUTPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSLinkTableResource

## NOTES

## RELATED LINKS
