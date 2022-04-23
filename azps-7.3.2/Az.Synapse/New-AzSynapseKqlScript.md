---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/new-azsynapsekqlscript
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/New-AzSynapseKqlScript.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/New-AzSynapseKqlScript.md
ms.openlocfilehash: 87bf41221d7d8924ae2bcc5cd186d51dce9fe8b1
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "143130887"
---
# New-AzSynapseKqlScript

## SYNOPSIS
Membuat atau memperbarui skrip KQL dalam ruang kerja.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.synapse/new-azsynapsekqlscript) untuk informasi terbaru.

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
Cmdlet **New-AzSynapseKqlScript** membuat atau memperbarui skrip KQL dalam ruang kerja.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> New-AzSynapseKqlScript -WorkspaceName ContosoWorkspace -DefinitionFile "C:\samples\KqlScript.kql"
```

Perintah ini membuat atau memperbarui skrip KQL dari file kueri Kusto KqlScript.kql di ruang kerja bernama ContosoWorkspace.

### Contoh 2
```powershell
PS C:\> $ws = Get-AzSynapseWorkspace -Name ContosoWorkspace
PS C:\> $ws | New-AzSynapseKqlScript -DefinitionFile "C:\samples\KqlScript.kql"
```

Perintah ini membuat atau memperbarui skrip KQL dari file kueri Kusto KqlScript.kql di ruang kerja bernama ContosoWorkspace melalui pipeline.

### Contoh 3
```powershell
PS C:\> New-AzSynapseKqlScript -WorkspaceName ContosoWorkspace -DefinitionFile "C:\samples\KqlScript.kql" -KustoPoolName ContosoKustoPool -KustoPoolDatabaseName ContosoKustoPoolDatabase
```

Perintah ini membuat atau memperbarui KqlScript dari file kueri Kusto KqlScript.kql yang dilampirkan ke ContosoKustoPoolDatabase di ruang kerja bernama ContosoWorkspace.

## PARAMETERS

### -AsJob
Menjalankan cmdlet di latar belakang

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
Nama database Kusto Synapse.

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
Nama kolam Kusto Synapse.

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

### -Nama Ruang Kerja
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
Meminta konfirmasi sebelum menjalankan cmdlet.

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
Cmdlet tidak dijalankan.

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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSSynapseWorkspace

## OUTPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSKqlScriptResource

## NOTES

## RELATED LINKS
