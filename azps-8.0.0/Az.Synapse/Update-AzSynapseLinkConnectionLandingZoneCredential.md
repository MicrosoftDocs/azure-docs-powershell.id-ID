---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/set-azsynapselinkconnectionlandingzonecredential
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Update-AzSynapseLinkConnectionLandingZoneCredential.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Update-AzSynapseLinkConnectionLandingZoneCredential.md
ms.openlocfilehash: 79b461e2dbb354c720e458668e2aed81fd90ab68
ms.sourcegitcommit: cbc0e7ba6f2d138b46d0d72b6776e95cb040e6c8
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 05/24/2022
ms.locfileid: "145529827"
---
# Update-AzSynapseLinkConnectionLandingZoneCredential

## SYNOPSIS
Memperbarui kredensial zona pendaratan koneksi tautan.

## SYNTAX

### UpdateByName (Default)
```
Update-AzSynapseLinkConnectionLandingZoneCredential -WorkspaceName <String> -LinkConnectionName <String>
 -SasToken <SecureString> [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### UpdateByObject
```
Update-AzSynapseLinkConnectionLandingZoneCredential -WorkspaceObject <PSSynapseWorkspace>
 -LinkConnectionName <String> -SasToken <SecureString> [-DefaultProfile <IAzureContextContainer>] [-WhatIf]
 [-Confirm] [<CommonParameters>]
```

### UpdateByInputObject
```
Update-AzSynapseLinkConnectionLandingZoneCredential -InputObject <PSLinkConnectionResource>
 -SasToken <SecureString> [-DefaultProfile <IAzureContextContainer>] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Cmdlet **Update-AzSynapseLinkConnectionLandingZoneCredential** memperbarui kredensial zona pendaratan koneksi tautan.

## EXAMPLES

### Contoh 1
```powershell
Update-AzSynapseLinkConnectionLandingZoneCredential -WorkspaceName ContosoWorkspace -LinkConnectionName ContosoLinkConnection -SasToken "SampleSasToken"
```

Perintah ini memperbarui info masuk zona pendaratan dengan token sas "exampleSasToken" koneksi tautan ContosoLinkConnection di ruang kerja ContosoWorkspace.

### Contoh 2
```powershell
$ws = Get-AzSynapseWorkspace -Name ContosoWorkspace
$ws | Update-AzSynapseLinkConnectionLandingZoneCredential -LinkConnectionName ContosoLinkConnection -SasToken "SampleSasToken"
```

Perintah ini memperbarui info masuk zona pendaratan dengan token sas "exampleSasToken" koneksi tautan ContosoLinkConnection di ruang kerja ContosoWorkspace melalui alur.

### Contoh: 3
```powershell
$lc = Get-AzSynpaseLinkConnection -WorkspaceName ContosoWorkspace -Name ContosoLinkConnection
$lc | Update-AzSynapseLinkConnectionLandingZoneCredential -SasToken "SampleSasToken"
```

Perintah ini memperbarui info masuk zona pendaratan dengan token sas "exampleSasToken" dari koneksi tautan melalui alur.

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
Informasi tentang koneksi tautan.

```yaml
Type: Microsoft.Azure.Commands.Synapse.Models.PSLinkConnectionResource
Parameter Sets: UpdateByInputObject
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
Type: System.String
Parameter Sets: UpdateByName, UpdateByObject
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -SasToken
Token sas zona pendaratan.

```yaml
Type: Azure.Analytics.Synapse.Artifacts.Models.SecureString
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
Parameter Sets: UpdateByName
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
Parameter Sets: UpdateByObject
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

### Microsoft.Azure.Commands.Synapse.Models.PSLinkConnectionResource

## OUTPUTS

### System.Boolean

## NOTES

## RELATED LINKS
