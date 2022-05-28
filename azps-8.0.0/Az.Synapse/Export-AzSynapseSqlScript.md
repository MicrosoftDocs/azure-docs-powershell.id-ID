---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/export-azsynapsesqlscript
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Export-AzSynapseSqlScript.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Export-AzSynapseSqlScript.md
ms.openlocfilehash: 73302e2f07899cd54c9682cba050b2b7098216db
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145556414"
---
# Export-AzSynapseSqlScript

## SYNOPSIS
Mengekspor skrip sql dari ruang kerja Synapse.

## SYNTAX

### ExportByName (Default)
```
Export-AzSynapseSqlScript -WorkspaceName <String> -OutputFolder <String> [-Name <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ExportByObject
```
Export-AzSynapseSqlScript -WorkspaceObject <PSSynapseWorkspace> -OutputFolder <String> [-Name <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### ExportByInputObject
```
Export-AzSynapseSqlScript -InputObject <PSSqlScriptResource> -OutputFolder <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Export-AzSynapseSqlScript** mengekspor skrip sql Azure Synapse ke file kueri SQL Server(.sql). Jika Anda menentukan nama skrip sql, cmdlet mengekspor skrip sql yang ditentukan. Jika Anda tidak menentukan nama, cmdlet mengekspor semua skrip sql di ruang kerja.

## EXAMPLES

### Contoh 1
```powershell
Export-AzSynapseSqlScript -WorkspaceName ContosoWorkspace -OutputFolder "C:\sqlscript"
```

Mengekspor semua skrip sql di ruang kerja ContosoWorkspace ke folder "C:\sqlscript".

### Contoh 2
```powershell
Export-AzSynapseSqlScript -WorkspaceName ContosoWorkspace -OutputFolder "C:\sqlscript" -Name "ContosoSqlScript"
```

Mengekspor skrip sql tunggal bernama ContosoSqlScript di ruang kerja ContosoWorkspace ke folder "C:\sqlscript".

### Contoh: 3
```powershell
$ws = Get-AzSynapseWorkspace -Name ContosoWorkspace
$ws | Export-AzSynapseSqlScript -Name ContosoSqlScript -OutputFolder "C:\sqlscript"
```

Mengekspor skrip sql tunggal yang disebut ContosoSqlScript di ruang kerja ContosoWorkspace ke folder "C:\sqlscript" melalui alur.

### Contoh 4
```powershell
$sqlscript = Get-AzSynapseSqlScript  -WorkspaceName ContosoWorkspace -Name ContosoSqlScript
$sqlscript | Export-AzSynapseSqlScript -OutputFolder "C:\sqlscript"
```

Mengekspor skrip sql tunggal yang disebut ContosoSqlScript di ruang kerja ContosoWorkspace ke folder "C:\sqlscript" melalui alur.

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
Objek skrip sql.

```yaml
Type: Microsoft.Azure.Commands.Synapse.Models.PSSqlScriptResource
Parameter Sets: ExportByInputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Nama skrip sql.

```yaml
Type: System.String
Parameter Sets: ExportByName, ExportByObject
Aliases: SqlScriptName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -OutputFolder
Folder tempat skrip sql harus ditempatkan.

```yaml
Type: System.String
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
Type: System.String
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
Type: Microsoft.Azure.Commands.Synapse.Models.PSSynapseWorkspace
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

### Microsoft.Azure.Commands.Synapse.Models.PSSqlScriptResource

## OUTPUTS

### System.String

## NOTES

## RELATED LINKS

[Get-AzSynapseSqlScript](./Get-AzSynapseSqlScript.md)

[Remove-AzSynapseSqlScript](./Remove-AzSynapseSqlScript.md)

[Set-AzSynapseSqlScript](./Set-AzSynapseSqlScript.md)