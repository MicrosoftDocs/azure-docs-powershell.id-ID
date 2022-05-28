---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/start-azsynapselinkconnection
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Start-AzSynapseLinkConnection.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Start-AzSynapseLinkConnection.md
ms.openlocfilehash: 6cc0676d3021b04d67b6b2336db104035714d275
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145562854"
---
# Start-AzSynapseLinkConnection

## SYNOPSIS
Memulai koneksi tautan.

## SYNTAX

### StartByName (Default)
```
Start-AzSynapseLinkConnection -WorkspaceName <String> -Name <String> [-PassThru] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### StartByObject
```
Start-AzSynapseLinkConnection -WorkspaceObject <PSSynapseWorkspace> -Name <String> [-PassThru] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### StartByInputObject
```
Start-AzSynapseLinkConnection -InputObject <PSLinkConnectionResource> [-PassThru] [-AsJob]
 [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Start-AzSynapseLinkConnection** memulai koneksi tautan di ruang kerja. Akan dikenakan biaya beberapa saat sejak mulai berjalan, setelah memanggil cmdlet ini, Anda dapat memeriksa status detail dengan memanggil **Get-AzSynapseLinkConnectionDetailedStatus**.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> Start-AzSynapseLinkConnection -WorkspaceName ContosoWorkspace -Name ContosoLinkConnection
```

Perintah ini memulai koneksi tautan bernama ContosoLinkConnection di ruang kerja.

### Contoh 2
```powershell
PS C:\> $ws = Get-AzSynapseWorkspace -Workspacename ContosoWorkspace 
PS C:\> $ws | Start-AzSynapseLinkConnection -Name ContosoLinkConnection
```

Perintah ini memulai koneksi tautan bernama ContosoLinkConnection di ruang kerja melalui alur.

### Contoh: 3
```powershell
PS C:\> $linkConnection = Get-AzSynapseLinkConnection -Workspacename ContosoWorkspace -Name ContosoLinkConnection
PS C:\> $linkConnection | Start-AzSynapseLinkConnection
```

Perintah ini memulai koneksi tautan bernama ContosoLinkConnection di ruang kerja melalui alur.

### Contoh 4
```powershell
PS C:\> Start-AzSynapseLinkConnection -WorkspaceName ContosoWorkspace -Name ContosoLinkConnection
PS C:\> Get-AzSynapseLinkConnectionDetailedStatus -WorkspaceName ContosoWorkspace -Name ContosoLinkConnection

    WorkspaceName     : ContosoWorkspace
    Id                : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
    Name              : ContosoLinkConnection
    IsApplyingChanges :
    IsPartiallyFailed : False
    StartTime         : 2022-03-10T07:57:37.8730044Z
    StopTime          : 
    Status            : Starting
    ContinuousRunId   : xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
    Error             :
```

Perintah **Start-AzSynapseLinkConnection** memulai koneksi tautan bernama ContosoLinkConnection di ruang kerja, lalu Anda dapat memanggil **Get-AzSynapseLinkConnectionDetailedStatus** untuk mendapatkan status koneksi tautan.

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
Objek koneksi tautan Synapse untuk Azure Sql Database.

```yaml
Type: PSLinkConnectionResource
Parameter Sets: StartByInputObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Name
Nama koneksi tautan Synapse untuk Azure Sql Database.

```yaml
Type: String
Parameter Sets: StartByName, StartByObject
Aliases: LinkConnectionName

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -PassThru
Cmdlet ini tidak mengembalikan objek secara default.
Jika sakelar ini ditentukan, sakelar akan mengembalikan true jika berhasil.

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

### -WorkspaceName
Nama ruang kerja Synapse.

```yaml
Type: String
Parameter Sets: StartByName
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
Parameter Sets: StartByObject
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

### System.Boolean

## NOTES

## RELATED LINKS
