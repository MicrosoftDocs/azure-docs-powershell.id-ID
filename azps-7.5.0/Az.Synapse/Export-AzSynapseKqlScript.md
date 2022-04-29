---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/export-azsynapsekqlscript
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Export-AzSynapseKqlScript.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Export-AzSynapseKqlScript.md
ms.openlocfilehash: 86d8e031b2f933a9dbab923f3475b4bf1e3b7657
ms.sourcegitcommit: 2a912c720caf0db4501ccea98b71ccecb84af036
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/27/2022
ms.locfileid: "144228042"
---
# Export-AzSynapseKqlScript

## SYNOPSIS
Mengekspor skrip KQL.

## SYNTAX

### ExportByName (Default)
```
Export-AzSynapseKqlScript -WorkspaceName <String> [-Name <String>] -OutputFolder <String> [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ExportByObject
```
Export-AzSynapseKqlScript -WorkspaceObject <PSSynapseWorkspace> [-Name <String>] -OutputFolder <String>
 [-AsJob] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ExportByInputObject
```
Export-AzSynapseKqlScript -InputObject <PSKqlScriptResource> -OutputFolder <String> [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Export-AzSynapseKqlScript** mengekspor skrip Azure Synapse KQL ke file kueri kusto (.kql). Nama skrip KQL menjadi nama file yang diekspor. Jika Anda menentukan nama skrip KQL, cmdlet mengekspor skrip KQL. Jika Anda tidak menentukan nama, cmdlet mengekspor semua skrip KQL di ruang kerja.

## EXAMPLES

### Contoh 1
```powershell
Export-AzSynapseKqlScript -WorkspaceName ContosoWorkspace -OutputFolder "C:\KqlScirpt"
```

Mengekspor semua skrip KQL di ruang kerja ContosoWorkspace ke folder "C:\KqlScirpt".

### Contoh 2
```powershell
Export-AzSynapseKqlScript -WorkspaceName ContosoWorkspace -Name ContosoKqlScript -OutputFolder "C:\KqlScript"
```

Mengekspor satu skrip KQL yang disebut ContosoKqlScript di ruang kerja ContosoWorkspace ke folder "C:\KqlScript".

### Contoh 3
```powershell
$ws = Get-AzSynapseWorkspace -Name ContosoWorkspace
$ws | Export-AzSynapseKqlScript -Name ContosoKqlScript -OutputFolder "C:\KqlScript"
```

Mengekspor satu skrip KQL yang disebut ContosoKqlScript di ruang kerja ContosoWorkspace ke folder "C:\KqlScript" melalui alur.

### Contoh 4
```powershell
$KqlScript = Get-AzSynapseKqlScript -WorkspaceName ContosoWorkspace -Name ContosoKqlScript
$KqlScript | Export-AzSynapseKqlScript -OutputFolder "C:\KqlScript"
```

Mengekspor satu skrip KQL yang disebut ContosoKqlScript di ruang kerja ContosoWorkspace ke folder "C:\KqlScript" melalui alur.

## PARAMETERS

### -AsJob
Jalankan cmdlet di latar belakang

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

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

### -InputObject
KQL objek skrip.

```yaml
Type: PSKqlScriptResource
Parameter Sets: ExportByInputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
KQL nama skrip.

```yaml
Type: String
Parameter Sets: ExportByName, ExportByObject
Aliases: KqlScriptName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OutputFolder
Folder tempat skrip KQL harus ditempatkan.

```yaml
Type: String
Parameter Sets: (All)
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
Type: String
Parameter Sets: ExportByName
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
Parameter Sets: ExportByObject
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

### Microsoft.Azure.Commands.Synapse.Models.PSKqlScriptResource

## OUTPUTS

### System.IO.FileInfo

## NOTES

## RELATED LINKS
