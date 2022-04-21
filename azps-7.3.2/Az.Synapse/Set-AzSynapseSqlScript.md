---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/set-azsynapsesqlscript
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Set-AzSynapseSqlScript.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Set-AzSynapseSqlScript.md
ms.openlocfilehash: 0212dc7e9dc40a049c9b2ec654c00754d28cf587
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/18/2022
ms.locfileid: "142813374"
---
# Set-AzSynapseSqlScript

## SYNOPSIS
Membuat atau memperbarui skrip SQL dalam ruang kerja.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.synapse/set-azsynapsesqlscript) untuk informasi terbaru.

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
Cmdlet **Set-AzSynapseSqlScript** membuat atau memperbarui skrip SQL dalam ruang kerja.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Set-AzSynapseSqlScript -WorkspaceName ContosoWorkspace -DefinitionFile "C:\\samples\\sqlscript.sql"
```

Perintah ini membuat atau memperbarui skrip SQL dari file skrip SQL sqlscript.sql di ruang kerja bernama ContosoWorkspace.

### Contoh 2
```powershell
PS C:\> $ws = Get-AzSynapseWorkspace -Name ContosoWorkspace
PS C:\> $ws | Set-AzSynapseSqlScript -DefinitionFile "C:\\samples\\sqlscript.sql"
```

Perintah ini membuat atau memperbarui skrip SQL dari file skrip SQL sqlscript.sql di ruang kerja bernama ContosoWorkspace.

### Contoh 3
```powershell
PS C:\> Set-AzSynapseSqlScript -WorkspaceName ContosoWorkspace -DefinitionFile "C:\\samples\\sqlscript.sql"  -SqlPoolName Contososqlpool -SqlDatabaseName Contosodatabase
```

Perintah ini membuat atau memperbarui skrip SQL dari file skrip SQL sqlscript.sql yang tersambung ke ContosoSqlPool dan menggunakan database bernama Contosodatabase di ruang kerja bernama ContosoWorkspace.

## PARAMETERS

### -AsJob
Menjalankan cmdlet di latar belakang

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
Penjabaran dari skrip SQL.

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
Jika menentukan jalur multi-level seperti \[rootFolder/subFolder\], SqlScript akan muncul di tingkat bawah.
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

### -Nama
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
Sql pool mana skrip sql akan terhubung.

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

### -Nama Ruang Kerja
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
objek input ruang kerja, biasanya melewati saluran.

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

### -Konfirmasi
Meminta konfirmasi sebelum menjalankan cmdlet.

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
Memperlihatkan apa yang akan terjadi jika cmdlet berjalan.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSSynapseWorkspace

## OUTPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSSqlScriptResource

## NOTES

## RELATED LINKS

[Export-AzSynapseSqlScript](./Export-AzSynapseSqlScript.md)

[Get-AzSynapseSqlScript](./Get-AzSynapseSqlScript.md)

[Remove-AzSynapseSqlScript](./Remove-AzSynapseSqlScript.md)
