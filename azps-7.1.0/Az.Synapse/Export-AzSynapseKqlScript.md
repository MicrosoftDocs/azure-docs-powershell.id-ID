---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/export-azsynapsekqlscript
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Export-AzSynapseKqlScript.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Export-AzSynapseKqlScript.md
ms.openlocfilehash: 477e684ba647f74f322e804a975d7441cf18d875
ms.sourcegitcommit: e109cc5320478db6aa8a52d49996b133007a65b9
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 01/12/2022
ms.locfileid: "136728173"
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
Cmdlet **Export-AzSynapseKqlScript** mengekspor skrip Azure Synapse KQL ke file kueri kusto (.kql). Nama skrip KQL menjadi nama file yang diekspor. Jika Anda menentukan nama skrip KQL, cmdlet akan mengekspor skrip KQL tersebut. Jika Anda tidak menentukan nama, ekspor semua skrip KQL di ruang kerja.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Export-AzSynapseKqlScript -WorkspaceName ContosoWorkspace -OutputFolder "C:\KqlScirpt"
```

Mengekspor semua skrip KQL di ruang kerja ContosoWorkspace ke folder "C:\KqlScirpt".

### Contoh 2
```powershell
PS C:\> Export-AzSynapseKqlScript -WorkspaceName ContosoWorkspace -Name ContosoKqlScript -OutputFolder "C:\KqlScript"
```

Mengekspor skrip KQL tunggal yang disebut ContosoKqlScript di ruang kerja ContosoWorkspace ke folder "C:\KqlScript".

### Contoh 3
```powershell
PS C:\> $ws = Get-AzSynapseWorkspace -Name ContosoWorkspace
PS C:\> $ws | Export-AzSynapseKqlScript -Name ContosoKqlScript -OutputFolder "C:\KqlScript"
```

Mengekspor skrip KQL tunggal yang disebut ContosoKqlScript di ruang kerja ContosoWorkspace ke folder "C:\KqlScript" melalui pipeline.

### Contoh 4
```powershell
PS C:\> $KqlScript = Get-AzSynapseKqlScript -WorkspaceName ContosoWorkspace -Name ContosoKqlScript
PS C:\> $KqlScript | Export-AzSynapseKqlScript -OutputFolder "C:\KqlScript"
```

Mengekspor skrip KQL tunggal yang disebut ContosoKqlScript di ruang kerja ContosoWorkspace ke folder "C:\KqlScript" melalui pipeline.

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
Objek skrip KQL.

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

### -Nama
Nama skrip KQL.

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
Folder tempat skrip KQL harus diletakkan.

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
objek input ruang kerja, biasanya melewati saluran.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, [lihat about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSSynapseWorkspace

### Microsoft.Azure.Commands.Synapse.Models.PSKqlScriptResource

## OUTPUTS

### System.IO.FileInfo

## CATATAN

## RELATED LINKS
