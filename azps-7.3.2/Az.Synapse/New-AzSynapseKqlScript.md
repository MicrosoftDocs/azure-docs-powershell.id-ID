---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/new-azsynapsekqlscript
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/New-AzSynapseKqlScript.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/New-AzSynapseKqlScript.md
ms.openlocfilehash: 388e2bdbe2a57f09ae8316c020ad9ff273846c83
ms.sourcegitcommit: 1927316437817d48f97c62dceced0067c41b95f2
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 03/15/2022
ms.locfileid: "140005317"
---
# New-AzSynapseKqlScript

## SYNOPSIS
Membuat atau memperbarui skrip KQL di dalam ruang kerja.

## SYNTAX

### SetByName (Default)
```
New-AzSynapseKqlScript -WorkspaceName <String> [-Name <String>] -DefinitionFile <String> [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SetByNameAndKustoPoolDatabase
```
New-AzSynapseKqlScript -WorkspaceName <String> [-Name <String>] -KustoPoolName <String>
 -KustoPoolDatabaseName <String> -DefinitionFile <String> [-AsJob] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SetByObject
```
New-AzSynapseKqlScript -WorkspaceObject <PSSynapseWorkspace> [-Name <String>] -DefinitionFile <String> [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SetByObjectAndKustoPoolDatabase
```
New-AzSynapseKqlScript -WorkspaceObject <PSSynapseWorkspace> [-Name <String>] -KustoPoolName <String>
 -KustoPoolDatabaseName <String> -DefinitionFile <String> [-AsJob] [-DefaultProfile <IAzureContextContainer>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **New-AzSynapseKqlScript** membuat atau memperbarui skrip KQL di dalam ruang kerja.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> New-AzSynapseKqlScript -WorkspaceName ContosoWorkspace -DefinitionFile "C:\samples\KqlScript.kql"
```

Perintah ini membuat atau memperbarui skrip KQL dari file kueri Kusto KqlScript.kql di ruang kerja yang bernama ContosoWorkspace.

### Contoh 2
```powershell
PS C:\> $ws = Get-AzSynapseWorkspace -Name ContosoWorkspace
PS C:\> $ws | New-AzSynapseKqlScript -DefinitionFile "C:\samples\KqlScript.kql"
```

Perintah ini membuat atau memperbarui skrip KQL dari file kueri Kusto KqlScript.kql dalam ruang kerja yang bernama ContosoWorkspace melalui pipeline.

### Contoh 3
```powershell
PS C:\> New-AzSynapseKqlScript -WorkspaceName ContosoWorkspace -DefinitionFile "C:\samples\KqlScript.kql" -KustoPoolName ContosoKustoPool -KustoPoolDatabaseName ContosoKustoPoolDatabase
```

Perintah ini membuat atau memperbarui KqlScript dari file kueri Kusto KqlScript.kql yang terhubung ke ContosoKustoPoolDatabase di ruang kerja bernama ContosoWorkspace.

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

### -DefinitionFile
Jalur file KQL.

```yaml
Type: String
Parameter Sets: (All)
Aliases: File

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KustoPoolDatabaseName
Nama database Synapse Kusto.

```yaml
Type: String
Parameter Sets: SetByNameAndKustoPoolDatabase, SetByObjectAndKustoPoolDatabase
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -KustoPoolName
Nama pool Synapse Kusto.

```yaml
Type: String
Parameter Sets: SetByNameAndKustoPoolDatabase, SetByObjectAndKustoPoolDatabase
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Nama
Nama skrip KQL.

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
Parameter Sets: SetByName, SetByNameAndKustoPoolDatabase
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
Parameter Sets: SetByObject, SetByObjectAndKustoPoolDatabase
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Konfirmasi
Meminta konfirmasi Anda sebelum menjalankan cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
Cmdlet tidak berjalan.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSSynapseWorkspace

## OUTPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSKqlScriptResource

## CATATAN

## RELATED LINKS
