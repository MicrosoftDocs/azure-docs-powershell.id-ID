---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/set-azsynapselinkconnectionlinktables
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Set-AzSynapseLinkConnectionLinkTable.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Set-AzSynapseLinkConnectionLinkTable.md
ms.openlocfilehash: e1277c94228fc9e17a142f70fb9e33d1990f8ef4
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145550898"
---
# Set-AzSynapseLinkConnectionLinkTable

## SYNOPSIS
Mengedit tabel tautan di bawah koneksi tautan.

## SYNTAX

### SetByName (Default)
```
Set-AzSynapseLinkConnectionLinkTable -WorkspaceName <String> -EditTablesRequestFile <String>
 -LinkConnectionName <String> [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### SetByObject
```
Set-AzSynapseLinkConnectionLinkTable -WorkspaceObject <PSSynapseWorkspace> -EditTablesRequestFile <String>
 -LinkConnectionName <String> [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm]
 [<CommonParameters>]
```

### SetByInputObject
```
Set-AzSynapseLinkConnectionLinkTable -EditTablesRequestFile <String> -InputObject <PSLinkConnectionResource>
 [-AsJob] [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Set-AzSynapseLinkConnectionLinkTables** mengedit tabel tautan di bawah koneksi tautan.

## EXAMPLES

### Contoh 1
```powershell
Set-AzSynapseLinkConnectionLinkTables -WorkspaceName ContosoWorkspace -LinkConnectionName ContosoLinkConnection -EditTablesRequestFile "C:\\samples\\edittables.json"
```

Perintah ini mengedit tabel tautan di bawah koneksi tautan ContosoLinkConnection di ruang kerja ContosoWorkspace.
Perintah mendasarkan tabel tautan pada informasi dalam file edittables.json.
File ini mencakup informasi tentang tabel tautan yang diedit.

### Contoh 2
```powershell
$ws = Get-AzSynapseWorkspace -Name ContosoWorkspace
$ws | Set-AzSynapseLinkConnectionLinkTables -LinkConnectionName ContosoLinkConnection -EditTablesRequestFile "C:\\samples\\edittables.json"
```

Perintah ini mengedit tabel tautan di bawah koneksi tautan ContosoLinkConnection di ruang kerja ContosoWorkspace melalui alur.
Perintah mendasarkan tabel tautan pada informasi dalam file edittables.json.
File ini mencakup informasi tentang tabel tautan yang diedit.

### Contoh: 3
```powershell
$lc = Get-AzSynpaseLinkConnection -WorkspaceName ContosoWorkspace -Name ContosoLinkConnection
$lc | Set-AzSynapseLinkConnectionLinkTables -EditTablesRequestFile "C:\\samples\\edittables.json"
```

Perintah ini mengedit tabel tautan di bawah koneksi tautan melalui alur.
Perintah mendasarkan tabel tautan pada informasi dalam file edittables.json.
File ini mencakup informasi tentang tabel tautan yang diedit.

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

### -EditTablesRequestFile
Menentukan jalur file lokal untuk file untuk mengedit tabel tautan

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

### -InputObject
Informasi tentang koneksi tautan.

```yaml
Type: PSLinkConnectionResource
Parameter Sets: SetByInputObject
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
Type: String
Parameter Sets: SetByName, SetByObject
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
Parameter Sets: SetByName
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
Parameter Sets: SetByObject
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
Menunjukkan yang akan terjadi jika cmdlet dijalankan.
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
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, dan -WarningVariable. Selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216)

## INPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSSynapseWorkspace

### Microsoft.Azure.Commands.Synapse.Models.PSLinkConnectionResource

## OUTPUTS

### System.Void

## NOTES

## RELATED LINKS
