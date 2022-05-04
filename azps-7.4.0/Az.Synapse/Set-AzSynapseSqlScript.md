---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/set-azsynapsesqlscript
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Set-AzSynapseSqlScript.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Set-AzSynapseSqlScript.md
ms.openlocfilehash: a5dba9dca467fefe19c9a548d4d179635a2876bf
ms.sourcegitcommit: e32efb81b37827496f5fe4e57cd9a67004b5a271
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/04/2022
ms.locfileid: "144691708"
---
# Set-AzSynapseSqlScript

## SYNOPSIS
Membuat atau memperbarui skrip SQL di ruang kerja.

> [!NOTE]
>Ini adalah versi sebelumnya dari dokumentasi kami. Silakan lihat [versi terbaru](/powershell/module/az.synapse/set-azsynapsesqlscript) untuk informasi terbaru.

## SYNTAX

### SetByName (Default)
```
Set-AzSynapseSqlScript -WorkspaceName <String> [-Name <String>] -DefinitionFile <String> [-ResultLimit <Int32>]
 [-FolderPath <String>] [-Description <String>] [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### SetByNameAndSqlPool
```
Set-AzSynapseSqlScript -WorkspaceName <String> -SqlPoolName <String> -SqlDatabaseName <String> [-Name <String>]
 -DefinitionFile <String> [-ResultLimit <Int32>] [-FolderPath <String>] [-Description <String>] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SetByObject
```
Set-AzSynapseSqlScript -WorkspaceObject <PSSynapseWorkspace> [-Name <String>] -DefinitionFile <String>
 [-ResultLimit <Int32>] [-FolderPath <String>] [-Description <String>] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### SetByObjectAndSqlPool
```
Set-AzSynapseSqlScript -WorkspaceObject <PSSynapseWorkspace> -SqlPoolName <String> -SqlDatabaseName <String>
 [-Name <String>] -DefinitionFile <String> [-ResultLimit <Int32>] [-FolderPath <String>]
 [-Description <String>] [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzSynapseSqlScript** membuat atau memperbarui skrip SQL di ruang kerja.

## EXAMPLES

### Contoh 1
```powershell
Set-AzSynapseSqlScript -WorkspaceName ContosoWorkspace -DefinitionFile "C:\\samples\\sqlscript.sql"
```

Perintah ini membuat atau memperbarui skrip SQL dari file skrip SQL sqlscript.sql di ruang kerja bernama ContosoWorkspace.

### Contoh 2
```powershell
$ws = Get-AzSynapseWorkspace -Name ContosoWorkspace
$ws | Set-AzSynapseSqlScript -DefinitionFile "C:\\samples\\sqlscript.sql"
```

Perintah ini membuat atau memperbarui skrip SQL dari file skrip SQL sqlscript.sql di ruang kerja bernama ContosoWorkspace.

### Contoh 3
```powershell
Set-AzSynapseSqlScript -WorkspaceName ContosoWorkspace -DefinitionFile "C:\\samples\\sqlscript.sql"  -SqlPoolName Contososqlpool -SqlDatabaseName Contosodatabase
```

Perintah ini membuat atau memperbarui skrip SQL dari file skrip SQL sqlscript.sql yang terhubung ke ContosoSqlPool dan menggunakan database bernama Contosodatabase di ruang kerja bernama ContosoWorkspace.

## PARAMETERS

### -AsJob
Jalankan cmdlet di latar belakang

```yaml
Type: System.Management.Automation.SwitchParameter
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
Type: Microsoft.Azure.Commands.Common.Authentication.Abstractions.Core.IAzureContextContainer
Parameter Sets: (All)
Aliases: AzContext, AzureRmContext, AzureCredential

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -DefinitionFile
Jalur file SQL.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: File

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Deskripsi
Deskripsi skrip SQL.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -FolderPath
Folder tempat skrip SQL ini berada.
Jika menentukan jalur multi-tingkat seperti \[rootFolder/subFolder\], SqlScript akan muncul di tingkat bawah.
Jika tidak ditentukan, skrip SQL ini akan muncul di tingkat akar.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: FolderName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Nama skrip sql.

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: SqlScriptName

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -ResultLimit
Batas hasil, '-1' tanpa batas.

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SqlDatabaseName
Database mana yang akan digunakan skrip sql.

```yaml
Type: System.String
Parameter Sets: SetByNameAndSqlPool, SetByObjectAndSqlPool
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SqlPoolName
Kumpulan sql mana yang akan disambungkan oleh skrip sql.

```yaml
Type: System.String
Parameter Sets: SetByNameAndSqlPool, SetByObjectAndSqlPool
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
Parameter Sets: SetByName, SetByNameAndSqlPool
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
Parameter Sets: SetByObject, SetByObjectAndSqlPool
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Confirm
Meminta Anda mengonfirmasi sebelum menjalankan cmdlet.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WhatIf
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
Cmdlet tidak dijalankan.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSSynapseWorkspace

## OUTPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSSqlScriptResource

## NOTES

## RELATED LINKS

[Export-AzSynapseSqlScript](./Export-AzSynapseSqlScript.md)

[Get-AzSynapseSqlScript](./Get-AzSynapseSqlScript.md)

[Remove-AzSynapseSqlScript](./Remove-AzSynapseSqlScript.md)
