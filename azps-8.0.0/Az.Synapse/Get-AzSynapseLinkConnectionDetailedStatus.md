---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/get-azsynapselinkconnectiondetailedstatus
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Get-AzSynapseLinkConnectionDetailedStatus.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Get-AzSynapseLinkConnectionDetailedStatus.md
ms.openlocfilehash: cd76ed33ac3dca5f2a03048dee6094d1c32342ff
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145507738"
---
# Get-AzSynapseLinkConnectionDetailedStatus

## SYNOPSIS
Mendapatkan status detail tentang koneksi tautan di ruang kerja.

## SYNTAX

### GetByName (Default)
```
Get-AzSynapseLinkConnectionDetailedStatus -WorkspaceName <String> -Name <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

### GetByObject
```
Get-AzSynapseLinkConnectionDetailedStatus -WorkspaceObject <PSSynapseWorkspace> -Name <String>
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzSynapseLinkConnectionDetailedStatus** mendapatkan status detail tentang koneksi tautan di ruang kerja. Setelah memulai/menghentikan koneksi tautan, Anda dapat menggunakan cmdlet ini untuk mendapatkan status koneksi tautan.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Get-AzSynapseLinkConnectionDetailedStatus -WorkspaceName ContosoWorkspace -Name ContosoLinkConnection
```

Mendapatkan status detail tentang koneksi tautan ContosoLinkConnection di ruang kerja ContosoWorkspace.

### Contoh 2
```powershell
PS C:\> $ws = Get-AzSynapseWorkspace -Name ContosoWorkspace
PS C:\> $ws | Get-AzSynapseLinkConnectionDetailedStatus -Name ContosoLinkConnection
```

Perintah ini mendapatkan status detail tentang koneksi tautan ContosoLinkConnection di bawah ruang kerja melalui alur.

### Contoh: 3
```powershell
PS C:\> Start-AzSynapseLinkConnection -WorkspaceName ContosoWorkspace -Name ContosoLinkConnection
PS C:\> Get-AzSynapseLinkConnectionDetailedStatus -WorkspaceName ContosoWorkspace -Name ContosoLinkConnection
```

Memulai koneksi tautan bernama ContosoLinkConnection di ruang kerja ContosoWorkspace, itu akan menghabiskan waktu untuk memulai, kemudian Anda dapat memanggil **Get-AzSynapseLinkConnectionDetailedStatus** untuk memantau statusnya.

### Contoh 4
```powershell
PS C:\> Stop-AzSynapseLinkConnection -WorkspaceName ContosoWorkspace -Name ContosoLinkConnection
PS C:\> Get-AzSynapseLinkConnectionDetailedStatus -WorkspaceName ContosoWorkspace -Name ContosoLinkConnection
```

Menghentikan koneksi tautan bernama ContosoLinkConnection di ruang kerja ContosoWorkspace, akan dikenakan biaya beberapa saat untuk berhenti, lalu Anda dapat memanggil **Get-AzSynapseLinkConnectionDetailedStatus** untuk memantau statusnya.

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

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
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

### System.String

## OUTPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSLinkConnectionDetailedStatus

## NOTES

## RELATED LINKS
