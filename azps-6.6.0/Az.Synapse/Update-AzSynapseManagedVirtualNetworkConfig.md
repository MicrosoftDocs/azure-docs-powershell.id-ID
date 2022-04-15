---
external help file: Microsoft.Azure.PowerShell.Cmdlets.Synapse.dll-Help.xml
Module Name: Az.Synapse
online version: https://docs.microsoft.com/powershell/module/az.synapse/update-azsynapsemanagedvirtualnetworkconfig
schema: 2.0.0
content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Update-AzSynapseManagedVirtualNetworkConfig.md
original_content_git_url: https://github.com/Azure/azure-powershell/blob/main/src/Synapse/Synapse/help/Update-AzSynapseManagedVirtualNetworkConfig.md
ms.openlocfilehash: 3a2f9e0ddb5966dc67662f7470d19ea4375b5f6a
ms.sourcegitcommit: dcb33efdfc53ba0b2f271e883021de84878d1f31
ms.translationtype: MT
ms.contentlocale: id-ID
ms.lasthandoff: 04/14/2022
ms.locfileid: "142296215"
---
# Update-AzSynapseManagedVirtualNetworkConfig

## SYNOPSIS
Pembaruan konfigurasi jaringan maya terkelola ke ruang kerja.

> [!NOTE]
>Ini adalah versi dokumentasi kami sebelumnya. Silakan lihat [versi terbaru](/powershell/module/az.synapse/update-azsynapsemanagedvirtualnetworkconfig) untuk informasi terbaru.

## SYNTAX

```
Update-AzSynapseManagedVirtualNetworkConfig -WorkspaceObject <PSSynapseWorkspace>
 [-PreventDataExfiltration <Boolean>] [-AllowedAadTenantIdsForLinking <String[]>]
 [-DefaultProfile <IAzureContextContainer>] [<CommonParameters>]
```

## DESCRIPTION
**Cmdlet Update-AzSynapseManagedVirtualNetworkConfig** memperbarui konfigurasi jaringan virtual terkelola ke ruang kerja.

## EXAMPLES

### Contoh 1
```powershell
PS C:\> $ws = Get-AzSynapseWorkspace -ResourceGroupName ContosoResourceGroup -WorkspaceName ContosoWorkspace 
PS C:\> $ws = $ws | Update-AzSynapseManagedVirtualNetworkConfig -AllowedAadTenantIdsForLinking a96040c4-18dd-4dde-8181-f70daca04919 
PS C:\> $ws | Update-AzSynapseWorkspace
```

Perintah pertama mengambil objek ruang kerja. Perintah kedua memperbarui ID penyewa AAD yang diperbolehkan. Perintah ketiga memperbarui ruang kerja.

## PARAMETERS

### -AllowedAadTenantIdsForLinking
ID penyewa AAD yang diperbolehkan untuk penautan.

```yaml
Type: System.String[]
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

### -PreventDataExfiltration
Menunjukkan apakah akan mencegah eksfiltrasi data.

```yaml
Type: System.Boolean
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -WorkspaceObject
objek input ruang kerja, biasanya melewati saluran.

```yaml
Type: Microsoft.Azure.Commands.Synapse.Models.PSSynapseWorkspace
Parameter Sets: (All)
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### CommonParameters
Cmdlet ini mendukung parameter umum: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. Untuk informasi selengkapnya, lihat [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSSynapseWorkspace

## OUTPUTS

### Microsoft.Azure.Commands.Synapse.Models.PSSynapseWorkspace

## CATATAN

## RELATED LINKS
