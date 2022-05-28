---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/get-azsynapselinkconnection
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Get-AzSynapseLinkConnection.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Get-AzSynapseLinkConnection.md
ms.openlocfilehash: d32b848249201a8c46674a6270201d397d0390bf
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145549806"
---
# Get-AzSynapseLinkConnection

## SYNOPSIS
Mendapatkan informasi tentang koneksi tautan di ruang kerja.

## SYNTAX

### GetByName (Default)
```
Get-AzSynapseLinkConnection -WorkspaceName <String> [-Name <String>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### GetByObject
```
Get-AzSynapseLinkConnection -WorkspaceObject <PSSynapseWorkspace> [-Name <String>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzSynapseLinkConnection** mendapatkan informasi tentang koneksi tautan di ruang kerja. Jika Anda menentukan nama koneksi tautan, cmdlet mendapatkan informasi tentang koneksi tautan tersebut. Jika Anda tidak menentukan nama, cmdlet mendapatkan informasi tentang semua koneksi tautan di ruang kerja.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Get-AzSynapseLinkConnection -WorkspaceName ContosoWorkspace
```

Mendapatkan daftar semua koneksi tautan di ruang kerja ContosoWorkspace.

### Contoh 2
```powershell
PS C:\> Get-AzSynapseLinkConnection -WorkspaceName ContosoWorkspace -Name ContosoLinkConnection
```

Mendapatkan koneksi tautan tunggal bernama ContosoLinkConnection di ruang kerja ContosoWorkspace.

### Contoh: 3
```powershell
PS C:\> $ws = Get-AzSynapseWorkspace -Name ContosoWorkspace
PS C:\> $ws | Get-AzSynapseLinkConnection
```

Perintah ini mendapatkan semua koneksi tautan di bawah ruang kerja melalui alur.

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
Nama koneksi tautan Synapse untuk Azure Sql Database.

```yaml
Type: String
Parameter Sets: (All)
Aliases: LinkConnectionName

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

### Microsoft.Azure.Commands.Synapse.Models.PSLinkConnectionResource

## NOTES

## RELATED LINKS
