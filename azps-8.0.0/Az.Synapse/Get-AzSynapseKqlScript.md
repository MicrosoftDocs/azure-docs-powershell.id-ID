---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/get-azsynapsekqlscript
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Get-AzSynapseKqlScript.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Get-AzSynapseKqlScript.md
ms.openlocfilehash: c2182102f1c4082c5b4e6ebf0651a096f825c9f9
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145514782"
---
# Get-AzSynapseKqlScript

## SYNOPSIS
Mendapatkan informasi tentang skrip KQL di ruang kerja.

## SYNTAX

### GetByName (Default)
```
Get-AzSynapseKqlScript -WorkspaceName <String> [-Name <String>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### GetByObject
```
Get-AzSynapseKqlScript -WorkspaceObject <PSSynapseWorkspace> [-Name <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzSynapseKqlScript** mendapatkan informasi tentang skrip KQL di ruang kerja. Jika Anda menentukan nama skrip KQL, cmdlet mendapatkan informasi tentang skrip KQL tersebut. Jika Anda tidak menentukan nama, cmdlet mendapatkan informasi tentang semua skrip KQL di ruang kerja.

## EXAMPLES

### Contoh 1
```powershell
Get-AzSynapseKqlScript -WorkspaceName ContosoWorkspace
```

Mendapatkan daftar semua skrip KQL di ruang kerja ContosoWorkspace.

### Contoh 2
```powershell
Get-AzSynapseKqlScript -WorkspaceName ContosoWorkspace -Name ContosoKqlScript
```

Mendapatkan satu skrip KQL yang disebut ContosoKqlScript di ruang kerja ContosoWorkspace.

### Contoh: 3
```powershell
$ws = Get-AzSynapseWorkspace -Name ContosoWorkspace
$ws | Get-AzSynapseKqlScript -Name ContosoKqlScript
```

Mendapatkan satu skrip KQL yang disebut ContosoKqlScript di ruang kerja ContosoWorkspace melalui alur.

## PARAMETERS

### -DefaultProfile
Kredensial, akun, penyewa, dan langganan yang digunakan untuk komunikasi dengan Azure.

```yaml
Type: IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
KQL nama skrip.

```yaml
Type: String
Parameter Sets: (All)
Aliases: KqlScriptName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WorkspaceName
Nama ruang kerja Synapse.

```yaml
Type: String
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
Type: PSSynapseWorkspace
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

### Microsoft.Azure.Commands.Synapse.Models.PSKqlScriptResource

## NOTES

## RELATED LINKS
