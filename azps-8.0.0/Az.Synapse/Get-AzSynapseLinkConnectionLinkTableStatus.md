---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/get-azsynapselinkconnectionlinktablestatus
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Get-AzSynapseLinkConnectionLinkTableStatus.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Get-AzSynapseLinkConnectionLinkTableStatus.md
ms.openlocfilehash: b5c415412f3e7867a4f903b217f24a825093ee21
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145536489"
---
# Get-AzSynapseLinkConnectionLinkTableStatus

## SYNOPSIS
Mendapatkan status tabel tautan di bawah koneksi tautan.

## SYNTAX

### GetByName (Default)
```
Get-AzSynapseLinkConnectionLinkTableStatus -WorkspaceName <String> -LinkConnectionName <String>
 -MaxSegmentCount <Int32> [-ContinuationToken <Object>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### GetByObject
```
Get-AzSynapseLinkConnectionLinkTableStatus -WorkspaceObject <PSSynapseWorkspace> -LinkConnectionName <String>
 -MaxSegmentCount <Int32> [-ContinuationToken <Object>] [-DefaultProfile <IAzureContextContainer>]
 [<CommonParameters>]
```

### GetByInputObject
```
Get-AzSynapseLinkConnectionLinkTableStatus -MaxSegmentCount <Int32> -InputObject <PSLinkConnectionResource>
 [-ContinuationToken <Object>] [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Get-AzSynapseLinkConnectionLinkTablesStatus** mendapatkan status tabel tautan di bawah koneksi tautan.

## EXAMPLES

### Contoh 1
```powershell
Get-AzSynapseLinkConnectionLinkTablesStatus -WorkspaceName ContosoWorkspace -LinkConnectionName ContosoLinkConnection -MaxSegmentCount 50
```

Perintah ini mendapatkan status tabel tautan dengan jumlah segmen maks 50 di bawah koneksi tautan ContosoLinkConnection di ruang kerja ContosoWorkspace.

### Contoh 2
```powershell
$ws = Get-AzSynapseWorkspace -Name ContosoWorkspace
$ws | Get-AzSynapseLinkConnectionLinkTablesStatus -LinkConnectionName ContosoLinkConnection -MaxSegmentCount 50
```

Perintah ini mendapatkan status tabel tautan dengan jumlah segmen maks 50 di bawah koneksi tautan ContosoLinkConnection di ruang kerja ContosoWorkspace melalui alur.

### Contoh: 3
```powershell
$lc = Get-AzSynpaseLinkConnection -WorkspaceName ContosoWorkspace -Name ContosoLinkConnection
$lc | Get-AzSynapseLinkConnectionLinkTablesStatus -MaxSegmentCount 50
```

Perintah ini mendapatkan status tabel tautan dengan jumlah segmen maks 50 di bawah koneksi tautan melalui alur.

## PARAMETERS

### -ContinuationToken
Token kelanjutan untuk mengkueri status tabel.

```yaml
Type: Object
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
Informasi tentang koneksi tautan.

```yaml
Type: PSLinkConnectionResource
Parameter Sets: GetByInputObject
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
Parameter Sets: GetByName, GetByObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -MaxSegmentCount
Jumlah segmen maksimum untuk mengkueri status tabel.

```yaml
Type: Int32
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

### Microsoft.Azure.Commands.Synapse.Models.PSLinkConnectionResource

## OUTPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSLinkConnectionQueryTableStatus

## NOTES

## RELATED LINKS
